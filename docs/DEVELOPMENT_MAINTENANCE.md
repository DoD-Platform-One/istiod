# How to upgrade the Istiod Package chart

1. From the root of the repo run, `helm dependencies update`.
1. Modify the `version` in [chart/Chart.yaml](../chart/Chart.yaml) - append `-bb.0` to the chart version from upstream.
1. Update [CHANGELOG.md](../CHANGELOG.md) adding an entry for the new version and noting all changes (at minimum this should include the line `Updated istiod to x.x.x`).
1. Generate the [README.md](../README.md) using the [gluon library script](https://repo1.dso.mil/big-bang/apps/library-charts/gluon/-/blob/master/docs/bb-package-readme.md) guidelines noting any additional chart changes you make during development testing.

## Branch/Tag Config

## Cluster setup

## Deploy Bigbang

## Validation/Testing Steps
