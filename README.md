<!-- Warning: Do not manually edit this file. See notes on gluon + helm-docs at the end of this file for more information. -->
# istiod

![Version: 1.22.2-bb.2](https://img.shields.io/badge/Version-1.22.2--bb.2-informational?style=flat-square) ![AppVersion: 1.22.2](https://img.shields.io/badge/AppVersion-1.22.2-informational?style=flat-square)

Helm chart for istio control plane

## Upstream References

* <https://github.com/istio/istio>

### Upstream Release Notes

- [Find upstream chart's release notes and CHANGELOG here](https://istio.io/latest/news/releases/1.22.x/announcing-1.22.2/)

## Learn More
* [Application Overview](docs/overview.md)
* [Other Documentation](docs/)

## Pre-Requisites

* Kubernetes Cluster deployed
* Kubernetes config installed in `~/.kube/config`
* Helm installed

Install Helm

https://helm.sh/docs/intro/install/

## Deployment

* Clone down the repository
* cd into directory
```bash
helm install istiod chart/
```

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| defaults.pilot.autoscaleEnabled | bool | `true` |  |
| defaults.pilot.autoscaleMin | int | `1` |  |
| defaults.pilot.autoscaleMax | int | `5` |  |
| defaults.pilot.autoscaleBehavior | object | `{}` |  |
| defaults.pilot.replicaCount | int | `1` |  |
| defaults.pilot.rollingMaxSurge | string | `"100%"` |  |
| defaults.pilot.rollingMaxUnavailable | string | `"25%"` |  |
| defaults.pilot.hub | string | `""` |  |
| defaults.pilot.tag | string | `""` |  |
| defaults.pilot.variant | string | `""` |  |
| defaults.pilot.image | string | `"pilot"` |  |
| defaults.pilot.traceSampling | float | `1` |  |
| defaults.pilot.resources.requests.cpu | string | `"500m"` |  |
| defaults.pilot.resources.requests.memory | string | `"2048Mi"` |  |
| defaults.pilot.seccompProfile | object | `{}` |  |
| defaults.pilot.cni.enabled | bool | `false` |  |
| defaults.pilot.cni.provider | string | `"default"` |  |
| defaults.pilot.extraContainerArgs | list | `[]` |  |
| defaults.pilot.env | object | `{}` |  |
| defaults.pilot.taint.enabled | bool | `false` |  |
| defaults.pilot.taint.namespace | string | `""` |  |
| defaults.pilot.affinity | object | `{}` |  |
| defaults.pilot.tolerations | list | `[]` |  |
| defaults.pilot.cpu.targetAverageUtilization | int | `80` |  |
| defaults.pilot.memory | object | `{}` |  |
| defaults.pilot.volumeMounts | list | `[]` |  |
| defaults.pilot.volumes | list | `[]` |  |
| defaults.pilot.nodeSelector | object | `{}` |  |
| defaults.pilot.podAnnotations | object | `{}` |  |
| defaults.pilot.serviceAnnotations | object | `{}` |  |
| defaults.pilot.serviceAccountAnnotations | object | `{}` |  |
| defaults.pilot.topologySpreadConstraints | list | `[]` |  |
| defaults.pilot.jwksResolverExtraRootCA | string | `""` |  |
| defaults.pilot.configSource.subscribedResources | list | `[]` |  |
| defaults.pilot.keepaliveMaxServerConnectionAge | string | `"30m"` |  |
| defaults.pilot.deploymentLabels | object | `{}` |  |
| defaults.pilot.configMap | bool | `true` |  |
| defaults.pilot.podLabels | object | `{}` |  |
| defaults.pilot.ipFamilyPolicy | string | `""` |  |
| defaults.pilot.ipFamilies | list | `[]` |  |
| defaults.sidecarInjectorWebhook.neverInjectSelector | list | `[]` |  |
| defaults.sidecarInjectorWebhook.alwaysInjectSelector | list | `[]` |  |
| defaults.sidecarInjectorWebhook.injectedAnnotations | object | `{}` |  |
| defaults.sidecarInjectorWebhook.enableNamespacesByDefault | bool | `false` |  |
| defaults.sidecarInjectorWebhook.reinvocationPolicy | string | `"Never"` |  |
| defaults.sidecarInjectorWebhook.rewriteAppHTTPProbe | bool | `true` |  |
| defaults.sidecarInjectorWebhook.templates | object | `{}` |  |
| defaults.sidecarInjectorWebhook.defaultTemplates | list | `[]` |  |
| defaults.istiodRemote.injectionURL | string | `""` |  |
| defaults.istiodRemote.injectionPath | string | `"/inject"` |  |
| defaults.istiodRemote.injectionCABundle | string | `""` |  |
| defaults.telemetry.enabled | bool | `true` |  |
| defaults.telemetry.v2.enabled | bool | `true` |  |
| defaults.telemetry.v2.prometheus.enabled | bool | `true` |  |
| defaults.telemetry.v2.stackdriver.enabled | bool | `false` |  |
| defaults.revision | string | `""` |  |
| defaults.revisionTags | list | `[]` |  |
| defaults.ownerName | string | `""` |  |
| defaults.meshConfig.enablePrometheusMerge | bool | `true` |  |
| defaults.experimental.stableValidationPolicy | bool | `false` |  |
| defaults.global.istioNamespace | string | `"istio-system"` |  |
| defaults.global.certSigners | list | `[]` |  |
| defaults.global.defaultPodDisruptionBudget.enabled | bool | `true` |  |
| defaults.global.defaultResources.requests.cpu | string | `"10m"` |  |
| defaults.global.hub | string | `"registry1.dso.mil/ironbank/opensource/istio"` |  |
| defaults.global.tag | string | `"1.22.2"` |  |
| defaults.global.variant | string | `""` |  |
| defaults.global.imagePullPolicy | string | `""` |  |
| defaults.global.imagePullSecrets[0] | string | `"private-registry"` |  |
| defaults.global.istiod.enableAnalysis | bool | `false` |  |
| defaults.global.logAsJson | bool | `false` |  |
| defaults.global.logging.level | string | `"default:info"` |  |
| defaults.global.omitSidecarInjectorConfigMap | bool | `false` |  |
| defaults.global.operatorManageWebhooks | bool | `false` |  |
| defaults.global.priorityClassName | string | `""` |  |
| defaults.global.proxy.image | string | `"proxyv2"` |  |
| defaults.global.proxy.autoInject | string | `"enabled"` |  |
| defaults.global.proxy.clusterDomain | string | `"cluster.local"` |  |
| defaults.global.proxy.componentLogLevel | string | `"misc:error"` |  |
| defaults.global.proxy.enableCoreDump | bool | `false` |  |
| defaults.global.proxy.excludeInboundPorts | string | `""` |  |
| defaults.global.proxy.includeInboundPorts | string | `"*"` |  |
| defaults.global.proxy.includeIPRanges | string | `"*"` |  |
| defaults.global.proxy.excludeIPRanges | string | `""` |  |
| defaults.global.proxy.includeOutboundPorts | string | `""` |  |
| defaults.global.proxy.excludeOutboundPorts | string | `""` |  |
| defaults.global.proxy.logLevel | string | `"warning"` |  |
| defaults.global.proxy.privileged | bool | `false` |  |
| defaults.global.proxy.readinessFailureThreshold | int | `4` |  |
| defaults.global.proxy.readinessInitialDelaySeconds | int | `0` |  |
| defaults.global.proxy.readinessPeriodSeconds | int | `15` |  |
| defaults.global.proxy.startupProbe.enabled | bool | `true` |  |
| defaults.global.proxy.startupProbe.failureThreshold | int | `600` |  |
| defaults.global.proxy.resources.requests.cpu | string | `"100m"` |  |
| defaults.global.proxy.resources.requests.memory | string | `"128Mi"` |  |
| defaults.global.proxy.resources.limits.cpu | string | `"2000m"` |  |
| defaults.global.proxy.resources.limits.memory | string | `"1024Mi"` |  |
| defaults.global.proxy.statusPort | int | `15020` |  |
| defaults.global.proxy.tracer | string | `"none"` |  |
| defaults.global.proxy_init.image | string | `"proxyv2"` |  |
| defaults.global.remotePilotAddress | string | `""` |  |
| defaults.global.caAddress | string | `""` |  |
| defaults.global.externalIstiod | bool | `false` |  |
| defaults.global.configCluster | bool | `false` |  |
| defaults.global.configValidation | bool | `true` |  |
| defaults.global.meshID | string | `""` |  |
| defaults.global.meshNetworks | object | `{}` |  |
| defaults.global.mountMtlsCerts | bool | `false` |  |
| defaults.global.multiCluster.enabled | bool | `false` |  |
| defaults.global.multiCluster.clusterName | string | `""` |  |
| defaults.global.network | string | `""` |  |
| defaults.global.pilotCertProvider | string | `"istiod"` |  |
| defaults.global.sds.token.aud | string | `"istio-ca"` |  |
| defaults.global.sts.servicePort | int | `0` |  |
| defaults.global.caName | string | `""` |  |
| defaults.global.autoscalingv2API | bool | `true` |  |
| defaults.base.enableIstioConfigCRDs | bool | `true` |  |
| defaults.istio_cni.chained | bool | `true` |  |
| defaults.istio_cni.provider | string | `"default"` |  |
| defaults.gateways.securityContext | object | `{}` |  |

## Contributing

Please see the [contributing guide](./CONTRIBUTING.md) if you are interested in contributing.

---

_This file is programatically generated using `helm-docs` and some BigBang-specific templates. The `gluon` repository has [instructions for regenerating package READMEs](https://repo1.dso.mil/big-bang/product/packages/gluon/-/blob/master/docs/bb-package-readme.md)._

