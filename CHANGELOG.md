# Changelog

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/), and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---
## [1.26.3-bb.0] (2025-08-01)
### Changed
- istiod updated from 1.26.2 to 1.26.3

## [1.26.2-bb.1] (2025-07-30)
### Added
- Added istio grafana dashboards

## [1.26.2-bb.0] (2025-07-11)
### Changed
- ironbank/opensource/istio/pilot updated from 1.26.1 to 1.26.2
- ironbank/opensource/istio/proxyv2 updated from 1.26.1 to 1.26.2

## [1.26.1-bb.0] (2025-06-12)

### Changed

- ironbank/opensource/istio/pilot updated from 1.25.3 to 1.26.1
- ironbank/opensource/istio/proxyv2 updated from 1.25.3 to 1.26.1

## [1.25.3-bb.3] - 2025-06-06

### Added

- Fix helm rendering when when adding additional envoy filters

## [1.25.3-bb.2] - 2025-06-05

### Added

- Added hardened configuration to support hardened service mesh deployment

## [1.25.3-bb.1] - 2025-06-04

### Added

- Added JSON schema for values.yaml

## [1.25.3-bb.0] - 2025-05-28

### Changed

- ironbank/opensource/istio/pilot updated from 1.25.2 to 1.25.3
- ironbank/opensource/istio/proxyv2 updated from 1.25.2 to 1.25.3

## [1.25.2-bb.4] - 2025-05-15

### Changed

- Added missing network policy for SSO

## [1.25.2-bb.3] - 2025-05-01

### Changed

- Stopped overriding upstream CPU limits for proxies and waypoints

## [1.25.2-bb.2] - 2025-04-30

### Added

- Added a `NetworkPolicy` that allows istiod access to the Kubernetes API

## [1.25.2-bb.1] - 2025-04-29

### Added

- Added option for passing in `EnvoyFilter` resources via `additionalEnvoyFilters`

### Changed

- Renamed `network-policies/additional-network-policies.yaml` to `network-policies/additional.yaml` for consistency

## [1.25.2-bb.0] - 2025-04-17

### Changed

- Updated for upstream 1.25.2

## [1.25.1-bb.0] - 2025-04-14

### Changed

- Migrated to passthrough chart pattern

## [1.22.2-bb.3] - 2024-09-30

### Added

- Added Tetrate TID image support
- adds defaults.global.enterprise boolean
- Adds defaults.global.tidHub key
- Adds defaults.global.tidHub key

## [1.22.2-bb.2] - 2024-07-25

### Added

- Added global values for registry, tag, and imagePullSecrets.
- Sets defaults.global.hub to `registry1.dso.mil/ironbank/opensource/istio`.
- Sets defaults.global.tag set to `<chart version>`.
- Sets defaults.global.imagePullSecrets to `registry-private`.

## [1.22.2-bb.1] - 2024-07-24

### Added

- Added the `registry1.dso.mil` image registry in chart/values.yaml.
- Set `private-registry` as the imagePullSecret in chart/values.yaml.

## [1.22.2-bb.0] - 2024-07-16

### Added

- Added Istio/istiod v1.22.2 chart files.
- Generated README.md
