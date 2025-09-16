# How to upgrade the Istiod Package chart

1. From the root of the repo run, `helm dependencies update`.
1. Modify the `version` in [chart/Chart.yaml](../chart/Chart.yaml) - append `-bb.0` to the chart version from upstream.
1. Update [CHANGELOG.md](../CHANGELOG.md) adding an entry for the new version and noting all changes (at minimum this should include the line `Updated istiod to x.x.x`).
1. Generate the [README.md](../README.md) using the [gluon library script](https://repo1.dso.mil/big-bang/apps/library-charts/gluon/-/blob/master/docs/bb-package-readme.md) guidelines noting any additional chart changes you make during development testing.

## Branch/Tag Config

## Cluster setup

⚠️ Always make sure your local bigbang repo is current before deploying.

1. Export your Ironbank/Harbor credentials:
    ```
    export REGISTRY_USERNAME='<your_username>'
    export REGISTRY_PASSWORD='<your_password>'
    ```
1. Export the path to your local bigbang repo (without a trailing `/`):
    ```
    export BIGBANG_REPO_DIR=<absolute_path_to_local_bigbang_repo>
    ```
1. Run the [k3d_dev.sh](https://repo1.dso.mil/big-bang/bigbang/-/blob/master/docs/assets/scripts/developer/k3d-dev.sh) script to deploy a dev cluster (`-a` flag required if deploying a local Keycloak):

    For `login.dso.mil` Keycloak:

    ```
    "${BIGBANG_REPO_DIR}/docs/assets/scripts/developer/k3d-dev.sh"
    ```

    For local `keycloak.dev.bigbang.mil` Keycloak (`-a` deploys instance with a second public IP):

    ```
    "${BIGBANG_REPO_DIR}/docs/assets/scripts/developer/k3d-dev.sh -a"
    ```
1. Export your kubeconfig:

    ```
    export KUBECONFIG=~/.kube/<your_kubeconfig_file>
    ```
    e.g.
    ```
    export KUBECONFIG=~/.kube/Sam.Sarnowski-dev-config
    ```
1. [Deploy flux to your cluster](https://repo1.dso.mil/big-bang/bigbang/-/blob/master/scripts/install_flux.sh):
    ```
    "${BIGBANG_REPO_DIR}/scripts/install_flux.sh -u ${REGISTRY_USERNAME} -p ${REGISTRY_PASSWORD}"
    ```


## Deploy Bigbang
From the root of this repo, run one of the following deploy commands depending on which Keycloak you wish to reference:

For `login.dso.mil` Keycloak:
⚠️ To tests Istio-cni package uncomment the IstioCNI block in `docs/dev-overrides/istio-testing.yaml`
  ```
  helm upgrade -i bigbang ${BIGBANG_REPO_DIR}/chart/ -n bigbang --create-namespace \
  --set registryCredentials.username=${REGISTRY_USERNAME} --set registryCredentials.password=${REGISTRY_PASSWORD} \
  -f https://repo1.dso.mil/big-bang/bigbang/-/raw/master/tests/test-values.yaml \
  -f https://repo1.dso.mil/big-bang/bigbang/-/raw/master/chart/ingress-certs.yaml \
  -f https://repo1.dso.mil/big-bang/bigbang/-/raw/master/docs/assets/configs/example/dev-sso-values.yaml \
  -f docs/dev-overrides/minimal.yaml \
  -f docs/dev-overrides/istio-testing.yaml
  ```

For local `keycloak.dev.bigbang.mil` Keycloak:
  ```
  helm upgrade -i bigbang ${BIGBANG_REPO_DIR}/chart/ -n bigbang --create-namespace \
  --set registryCredentials.username=${REGISTRY_USERNAME} --set registryCredentials.password=${REGISTRY_PASSWORD} \
  -f https://repo1.dso.mil/big-bang/bigbang/-/raw/master/tests/test-values.yaml \
  -f https://repo1.dso.mil/big-bang/bigbang/-/raw/master/chart/ingress-certs.yaml \
  -f docs/dev-overrides/minimal.yaml \
  -f docs/dev-overrides/istio-testing-local-keycloak.yaml
  ```

This will deploy the following apps for testing:

- IstioCRDs, Istiod and Istio-gatway
- Kiali, Tempo and Monitoring (including Grafana), all with SSO enabled
- Optionally Keycloak

## Validation/Testing Steps
⚠️ For testing with a local Keycloak instance, you will need to manually register or create an account as an admin before proceeding with the below tests. For more info please reference the Keycloak [DEVELOPMENT_MAINTENANCE.md](https://repo1.dso.mil/big-bang/product/packages/keycloak/-/blob/main/docs/DEVELOPMENT_MAINTENANCE.md).

1. Navigate to Grafana (https://grafana.dev.bigbang.mil/) and validate that the Istio dashboards are present and show some data. You may need to alter filters to pick a workload that has information showing.
1. Since Kiali (https://kiali.dev.bigbang.mil/) interfaces with Istio for most of its information it is a good idea to validate its functionality. To do this, perform the test steps [here](https://repo1.dso.mil/big-bang/product/packages/kiali/-/blob/main/docs/DEVELOPMENT_MAINTENANCE.md?ref_type=heads#manual-testing-steps).
1. Navigate to promethues to validate authservice login
1. Once you've confirmed that the package tests above pass, also test your branches against Big Bang per the steps in [this document](https://repo1.dso.mil/big-bang/bigbang/-/blob/master/docs/developer/test-package-against-bb.md).


## Big Bang MR Guidance

Once the upgrade MR has been approved a new version will be cut and an MR will be opened on the Big Bang repository.  Since this package follows the same versioning as `istio-cni`, `istio-crds`, and `istio-gateway`, it is recommended to close all but one of the Big Bang MR's and use the consolidated MR to update all versions.
