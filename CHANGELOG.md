# Changelog

格式遵循 [Keep a Changelog](https://keepachangelog.com/zh-CN/1.1.0/)，并遵循 [Semantic Versioning](https://semver.org/lang/zh-CN/)。

## [Unreleased]

### Added

- 提供 `.slsp` 套件包目录规范、打包脚本和 GitHub Release 发布 workflow。
- 支持从 `suite.yaml.metadata.version` 读取套件版本并生成 `<suiteId>-<version>.slsp` 交付包。
- 支持将每个套件目录下的 `CHANGELOG.md` 作为交付快照随 `.slsp` 包发布。

### Fixed

- 协议仿真服务启用容器 init，避免健康检查产生的 `curl` 子进程成为僵尸进程。
