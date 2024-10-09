# Changelog

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/), and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---

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
- Sets defaults.global.tag set to  `<chart version>`. 
- Sets defaults.global.imagePullSecrets to `registry-private`.

## [1.22.2-bb.1] - 2024-07-24

### Added

- Added the `registry1.dso.mil` image registry in chart/values.yaml.
- Set `private-registry` as the imagePullSecret in chart/values.yaml.

## [1.22.2-bb.0] - 2024-07-16

### Added

- Added Istio/istiod v1.22.2 chart files.
- Generated README.md
