# Changelog

## [2.2.0](https://github.com/lokalise/kustomize-service-base/compare/v2.1.0...v2.2.0) (2024-03-06)


### Features

* **PLAT-2789:** Allow connections from coroot ([1c2ed26](https://github.com/lokalise/kustomize-service-base/commit/1c2ed26a7ee6ed5861d2d3e830a60df633f19e3d))

## [2.1.0](https://github.com/lokalise/kustomize-service-base/compare/v2.0.0...v2.1.0) (2024-03-05)


### Features

* Remove slo group from collection ([205719d](https://github.com/lokalise/kustomize-service-base/commit/205719d461463e92f4413dcc19cb627c001f54f8))

## [2.0.0](https://github.com/lokalise/kustomize-service-base/compare/v2.0.0...v2.0.0) (2024-03-05)


### ⚠ BREAKING CHANGES

* Refactor
* Introduce collections, a way to reference multiple groups at once so users can include the base (collection) with a single 'resource' entry
* **PLAT-2734:** Remove the previous `autoscaling` group from the base.

### Features

* Add scheduling component ([2f09612](https://github.com/lokalise/kustomize-service-base/commit/2f09612a793e5ccdcb7285e4f8f0a6f224a1685e))
* Add topology spread constraint ([a921076](https://github.com/lokalise/kustomize-service-base/commit/a9210769d17d4cd4e334aca6eeec5ca4f00fea1c))
* Added scheduling component to rollout ([c8b38ce](https://github.com/lokalise/kustomize-service-base/commit/c8b38ce5becbd02c06577c37e2a89933f232774a))
* Introduce collections, a way to reference multiple groups at once so users can include the base (collection) with a single 'resource' entry ([fed9414](https://github.com/lokalise/kustomize-service-base/commit/fed9414acced23e39a0f66c2f0da8b5bee8e669e))
* Modified podAntiaffinity to be required during scheduling ([916fa6c](https://github.com/lokalise/kustomize-service-base/commit/916fa6cd2483a998d211e8173c0a4b52f6236001))
* Modified podAntiaffinity transforms ([b8108da](https://github.com/lokalise/kustomize-service-base/commit/b8108dad9df3e980a08a1a9b95e33fd99f0844f5))
* Modify topology spread constraing transform ([a307ac8](https://github.com/lokalise/kustomize-service-base/commit/a307ac8c77de03c7879be16b9d623fb7b110bfd1))
* **PLAT-2339:** Limit deny scope to current rollout only ([8b14f87](https://github.com/lokalise/kustomize-service-base/commit/8b14f870c42d613d2b8faf1ed1d0c51285c789b2))
* **PLAT-2734:** Make Pod autoscaling optional (and disabled) by default ([7f8563b](https://github.com/lokalise/kustomize-service-base/commit/7f8563b7c5012db590c596efa0c1fd1b710df248))
* Reduce ScaledObject replicas ([e841743](https://github.com/lokalise/kustomize-service-base/commit/e841743f82dca771b3297468924ab39fac34f0c1))
* Refactor ([4d9bc63](https://github.com/lokalise/kustomize-service-base/commit/4d9bc63d6a69f7b482c7a9f99d051cf9a14e176c))
* Switch to single version number; no granular, per-group releases anymore ([f33b10b](https://github.com/lokalise/kustomize-service-base/commit/f33b10b121072ec28c4a794b22e0be6ccd97de31))
* Use HTTP for health and readiness checks ([02f761e](https://github.com/lokalise/kustomize-service-base/commit/02f761eb3206c1cdc950ce92faf281b883f518d5))
* Use port names in network policies ([d223729](https://github.com/lokalise/kustomize-service-base/commit/d223729b9b3e8204074a0db8a5c4078c38b2d830))


### Bug Fixes

* Apply the no-tls component to all internal ingresses ([3570904](https://github.com/lokalise/kustomize-service-base/commit/3570904b0a5409b27a103aa2e07c2bc520ff360f))
* Correctly reference rollout referece in ScaledObjects ([68e902f](https://github.com/lokalise/kustomize-service-base/commit/68e902f82faacc9dd255243ccb37b1aed9740c11))
* fixed metadata ([416db1f](https://github.com/lokalise/kustomize-service-base/commit/416db1fd94133b8d071a58b3ec1233dc3dba380f))
* Fixed podAntiAffinity syntax ([9eb3dce](https://github.com/lokalise/kustomize-service-base/commit/9eb3dce6827b6164a9f56c2df482573fdac614da))
* Fixed wrong indentation ([b654286](https://github.com/lokalise/kustomize-service-base/commit/b6542860b1cd2daa563ffb795029195d3056f185))
* Modified podAntiAffinity to preferred ([6dc75a6](https://github.com/lokalise/kustomize-service-base/commit/6dc75a6aa278dbe9db91653b0eb135a99c96bef3))
* Modify create transform property ([0256eec](https://github.com/lokalise/kustomize-service-base/commit/0256eec9c53b428e4089c560ee86ed90dfbb02c4))


### Miscellaneous Chores

* release 1.12.0 ([7258eee](https://github.com/lokalise/kustomize-service-base/commit/7258eeef51394a2246872b5a8eec9440cc1d424c))
* release 1.13.0 ([e7f3643](https://github.com/lokalise/kustomize-service-base/commit/e7f3643d1d4a46880429154ce8597a2621f90363))
