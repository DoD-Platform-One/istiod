<!-- Warning: Do not manually edit this file. See notes on gluon + helm-docs at the end of this file for more information. -->
# istiod

![Version: 1.25.2-bb.0](https://img.shields.io/badge/Version-1.25.2--bb.0-informational?style=flat-square) ![AppVersion: 1.25.2](https://img.shields.io/badge/AppVersion-1.25.2-informational?style=flat-square) ![Maintenance Track: bb_integrated](https://img.shields.io/badge/Maintenance_Track-bb_integrated-green?style=flat-square)

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
| networkPolicies.enabled | bool | `false` |  |
| networkPolicies.additionalPolicies | list | `[]` |  |
| monitoring.enabled | bool | `true` |  |
| mtls.mode | string | `"STRICT"` |  |
| defaultSecurityHeaders.enabled | bool | `true` |  |
| upstream.autoscaleEnabled | bool | `true` |  |
| upstream.autoscaleMin | int | `1` |  |
| upstream.autoscaleMax | int | `5` |  |
| upstream.autoscaleBehavior | object | `{}` |  |
| upstream.replicaCount | int | `1` |  |
| upstream.rollingMaxSurge | string | `"100%"` |  |
| upstream.rollingMaxUnavailable | string | `"25%"` |  |
| upstream.hub | string | `""` |  |
| upstream.tag | string | `""` |  |
| upstream.variant | string | `""` |  |
| upstream.image | string | `"pilot"` |  |
| upstream.traceSampling | float | `1` |  |
| upstream.resources.requests.cpu | string | `"500m"` |  |
| upstream.resources.requests.memory | string | `"2048Mi"` |  |
| upstream.seccompProfile | object | `{}` |  |
| upstream.cni.enabled | bool | `false` |  |
| upstream.cni.provider | string | `"default"` |  |
| upstream.extraContainerArgs | list | `[]` |  |
| upstream.env.ENABLE_NATIVE_SIDECARS | string | `"true"` |  |
| upstream.taint.enabled | bool | `false` |  |
| upstream.taint.namespace | string | `""` |  |
| upstream.affinity | object | `{}` |  |
| upstream.tolerations | list | `[]` |  |
| upstream.cpu.targetAverageUtilization | int | `80` |  |
| upstream.memory | object | `{}` |  |
| upstream.volumeMounts | list | `[]` |  |
| upstream.volumes | list | `[]` |  |
| upstream.initContainers | list | `[]` |  |
| upstream.nodeSelector | object | `{}` |  |
| upstream.podAnnotations | object | `{}` |  |
| upstream.serviceAnnotations | object | `{}` |  |
| upstream.serviceAccountAnnotations | object | `{}` |  |
| upstream.sidecarInjectorWebhookAnnotations | object | `{}` |  |
| upstream.topologySpreadConstraints | list | `[]` |  |
| upstream.jwksResolverExtraRootCA | string | `""` |  |
| upstream.keepaliveMaxServerConnectionAge | string | `"30m"` |  |
| upstream.deploymentLabels | object | `{}` |  |
| upstream.configMap | bool | `true` |  |
| upstream.podLabels | object | `{}` |  |
| upstream.ipFamilyPolicy | string | `""` |  |
| upstream.ipFamilies | list | `[]` |  |
| upstream.trustedZtunnelNamespace | string | `""` |  |
| upstream.sidecarInjectorWebhook.neverInjectSelector | list | `[]` |  |
| upstream.sidecarInjectorWebhook.alwaysInjectSelector | list | `[]` |  |
| upstream.sidecarInjectorWebhook.injectedAnnotations | object | `{}` |  |
| upstream.sidecarInjectorWebhook.enableNamespacesByDefault | bool | `false` |  |
| upstream.sidecarInjectorWebhook.reinvocationPolicy | string | `"Never"` |  |
| upstream.sidecarInjectorWebhook.rewriteAppHTTPProbe | bool | `true` |  |
| upstream.sidecarInjectorWebhook.templates | object | `{}` |  |
| upstream.sidecarInjectorWebhook.defaultTemplates | list | `[]` |  |
| upstream.istiodRemote.enabled | bool | `false` |  |
| upstream.istiodRemote.injectionURL | string | `""` |  |
| upstream.istiodRemote.injectionPath | string | `"/inject"` |  |
| upstream.istiodRemote.injectionCABundle | string | `""` |  |
| upstream.telemetry.enabled | bool | `true` |  |
| upstream.telemetry.v2.enabled | bool | `true` |  |
| upstream.telemetry.v2.prometheus.enabled | bool | `true` |  |
| upstream.telemetry.v2.stackdriver.enabled | bool | `false` |  |
| upstream.revision | string | `""` |  |
| upstream.revisionTags | list | `[]` |  |
| upstream.ownerName | string | `""` |  |
| upstream.meshConfig.enablePrometheusMerge | bool | `true` |  |
| upstream.meshConfig.accessLogFile | string | `"/dev/stdout"` |  |
| upstream.meshConfig.meshMTLS.minProtocolVersion | string | `"TLSV1_2"` |  |
| upstream.experimental.stableValidationPolicy | bool | `false` |  |
| upstream.global.istioNamespace | string | `"istio-system"` |  |
| upstream.global.certSigners | list | `[]` |  |
| upstream.global.defaultPodDisruptionBudget.enabled | bool | `true` |  |
| upstream.global.defaultResources.requests.cpu | string | `"10m"` |  |
| upstream.global.hub | string | `"registry1.dso.mil/ironbank/opensource/istio"` |  |
| upstream.global.tag | string | `"1.25.2"` |  |
| upstream.global.variant | string | `""` |  |
| upstream.global.imagePullPolicy | string | `""` |  |
| upstream.global.imagePullSecrets | list | `[]` |  |
| upstream.global.istiod.enableAnalysis | bool | `false` |  |
| upstream.global.logAsJson | bool | `false` |  |
| upstream.global.logging.level | string | `"default:info"` |  |
| upstream.global.omitSidecarInjectorConfigMap | bool | `false` |  |
| upstream.global.operatorManageWebhooks | bool | `false` |  |
| upstream.global.priorityClassName | string | `""` |  |
| upstream.global.proxy.image | string | `"proxyv2"` |  |
| upstream.global.proxy.autoInject | string | `"enabled"` |  |
| upstream.global.proxy.clusterDomain | string | `"cluster.local"` |  |
| upstream.global.proxy.componentLogLevel | string | `"misc:error"` |  |
| upstream.global.proxy.excludeInboundPorts | string | `""` |  |
| upstream.global.proxy.includeInboundPorts | string | `"*"` |  |
| upstream.global.proxy.includeIPRanges | string | `"*"` |  |
| upstream.global.proxy.excludeIPRanges | string | `""` |  |
| upstream.global.proxy.includeOutboundPorts | string | `""` |  |
| upstream.global.proxy.excludeOutboundPorts | string | `""` |  |
| upstream.global.proxy.logLevel | string | `"warning"` |  |
| upstream.global.proxy.outlierLogPath | string | `""` |  |
| upstream.global.proxy.privileged | bool | `false` |  |
| upstream.global.proxy.readinessFailureThreshold | int | `4` |  |
| upstream.global.proxy.readinessInitialDelaySeconds | int | `0` |  |
| upstream.global.proxy.readinessPeriodSeconds | int | `15` |  |
| upstream.global.proxy.startupProbe.enabled | bool | `true` |  |
| upstream.global.proxy.startupProbe.failureThreshold | int | `600` |  |
| upstream.global.proxy.resources.requests.cpu | string | `"100m"` |  |
| upstream.global.proxy.resources.requests.memory | string | `"128Mi"` |  |
| upstream.global.proxy.resources.limits.memory | string | `"512Mi"` |  |
| upstream.global.proxy.statusPort | int | `15020` |  |
| upstream.global.proxy.tracer | string | `"none"` |  |
| upstream.global.proxy_init.image | string | `"proxyv2"` |  |
| upstream.global.proxy_init.forceApplyIptables | bool | `false` |  |
| upstream.global.remotePilotAddress | string | `""` |  |
| upstream.global.caAddress | string | `""` |  |
| upstream.global.externalIstiod | bool | `false` |  |
| upstream.global.configCluster | bool | `false` |  |
| upstream.global.configValidation | bool | `true` |  |
| upstream.global.meshID | string | `""` |  |
| upstream.global.meshNetworks | object | `{}` |  |
| upstream.global.mountMtlsCerts | bool | `false` |  |
| upstream.global.multiCluster.enabled | bool | `false` |  |
| upstream.global.multiCluster.clusterName | string | `""` |  |
| upstream.global.network | string | `""` |  |
| upstream.global.pilotCertProvider | string | `"istiod"` |  |
| upstream.global.sds.token.aud | string | `"istio-ca"` |  |
| upstream.global.sts.servicePort | int | `0` |  |
| upstream.global.caName | string | `""` |  |
| upstream.global.waypoint.resources.requests.cpu | string | `"100m"` |  |
| upstream.global.waypoint.resources.requests.memory | string | `"128Mi"` |  |
| upstream.global.waypoint.resources.limits.memory | string | `"256Mi"` |  |
| upstream.global.waypoint.affinity | object | `{}` |  |
| upstream.global.waypoint.topologySpreadConstraints | list | `[]` |  |
| upstream.global.waypoint.nodeSelector | object | `{}` |  |
| upstream.global.waypoint.tolerations | list | `[]` |  |
| upstream.base.enableIstioConfigCRDs | bool | `true` |  |
| upstream.gateways.securityContext | object | `{}` |  |
| upstream.gateways.seccompProfile | object | `{}` |  |

## Contributing

Please see the [contributing guide](./CONTRIBUTING.md) if you are interested in contributing.

---

_This file is programatically generated using `helm-docs` and some BigBang-specific templates. The `gluon` repository has [instructions for regenerating package READMEs](https://repo1.dso.mil/big-bang/product/packages/gluon/-/blob/master/docs/bb-package-readme.md)._

