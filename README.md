<!-- Warning: Do not manually edit this file. See notes on gluon + helm-docs at the end of this file for more information. -->
# istiod

![Version: 1.26.2-bb.1](https://img.shields.io/badge/Version-1.26.2--bb.1-informational?style=flat-square) ![AppVersion: 1.26.2](https://img.shields.io/badge/AppVersion-1.26.2-informational?style=flat-square) ![Maintenance Track: bb_integrated](https://img.shields.io/badge/Maintenance_Track-bb_integrated-green?style=flat-square)

Helm chart for istio control plane

## Upstream References

- <https://github.com/istio/istio>

## Upstream Release Notes

- [Find upstream chart's release notes and CHANGELOG here](https://istio.io/latest/news/releases)

## Learn More

- [Application Overview](docs/overview.md)
- [Other Documentation](docs/)

## Pre-Requisites

- Kubernetes Cluster deployed
- Kubernetes config installed in `~/.kube/config`
- Helm installed

Install Helm

https://helm.sh/docs/intro/install/

## Deployment

- Clone down the repository
- cd into directory

```bash
helm install istiod chart/
```

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| networkPolicies.enabled | bool | `false` | Enable or disable the bundled network policies |
| networkPolicies.controlPlaneCIDRs | list | `[]` | Configure which CIDRs istiod will be allowed to connect to when accessing the kube-apiserver; if none are specified, the chart will look up the default kubernetes EndpointSlice and use the addresses found there |
| networkPolicies.additionalPolicies | list | `[]` | A list of additional network policies to create in the release namespace |
| additionalEnvoyFilters | list | `[]` | A list of additional EnvoyFilters to create in the release namespace |
| monitoring.enabled | bool | `true` | Enable or disable the bundled monitoring components and network policies |
| authservice.enabled | bool | `false` |  |
| mtls.mode | string | `"STRICT"` | Set the mTLS mode for the istio-system namespace |
| defaultSecurityHeaders.enabled | bool | `true` | Enable or disable the default security headers |
| hardened.enabled | bool | `false` | Enable or disable the hardened Istio configuration |
| hardened.customAuthorizationPolicies | list | `[]` |  |
| upstream | object | Upstream chart values | Values to pass to [the upstream istiod chart](https://github.com/istio/istio/blob/master/manifests/charts/istio-control/istio-discovery/values.yaml) |

## Contributing

Please see the [contributing guide](./CONTRIBUTING.md) if you are interested in contributing.

---

_This file is programatically generated using `helm-docs` and some BigBang-specific templates. The `gluon` repository has [instructions for regenerating package READMEs](https://repo1.dso.mil/big-bang/product/packages/gluon/-/blob/master/docs/bb-package-readme.md)._

