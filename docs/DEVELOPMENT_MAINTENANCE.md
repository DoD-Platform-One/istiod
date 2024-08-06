# How to upgrade the Istiod Package chart


1. From the root of the repo run, `kpt pkg update chart@<v1.x.x> --strategy alpha-git-patch`. Use the version tag you got in the previous steps. You may be prompted to resolve some conflicts - choose what makes sense (if there are BB additions/changes keep them, if there are upstream additions/changes keep them).
1. Modify the `version` in [chart/Chart.yaml](../chart/Chart.yaml) - append `-bb.0` to the chart version from upstream.
1. Update [CHANGELOG.md](../CHANGELOG.md) adding an entry for the new version and noting all changes (at minimum this should include the line `Updated Istiod to x.x.x`).
1. Generate the [README.md](../README.md) using the [gluon library script](https://repo1.dso.mil/big-bang/apps/library-charts/gluon/-/blob/master/docs/bb-package-readme.md) guidelines noting any additional chart changes you make during development testing.

## Branch/Tag Config

## Cluster setup

## Deploy Bigbang

## Validation/Testing Steps

# Modifications made to upstream chart

## /chart/values.yaml
Changes to default values:
- defaults.global.hub set to `registry1.dso.mil/ironbank/opensource/istio` # <-- Global setting for Istiod and Gateway
- defaults.global.tag set to  `chart version`  # <-- Global setting for Istiod and Gateway
- defaults.global.imagePullSecrets add `registry-private` # <-- Global setting for Istiod and Gateway
