# Changelog

格式遵循 [Keep a Changelog](https://keepachangelog.com/zh-CN/1.1.0/)，并遵循 [Semantic Versioning](https://semver.org/lang/zh-CN/)。

## [Unreleased]

### Added

- 首次发布主机扫描套件镜像。
- 支持扫描 `/24` 至 `/32` IPv4 CIDR 网段。
- 支持 TCP 端口探测、Banner 服务指纹识别和 ICMP 存活探测。
- 提供实时扫描状态、任务历史、开放端口和服务指纹报告。
- 提供 Vue 3 套件前端，并接入 SecLab UI、SDL Token 和套件 SDK 语言同步能力。
- 支持取消正在运行的主机扫描，并在前端展示取消中及已取消状态。
- 新增 Bug、功能和任务 Issue 模板，范围字段支持多选。
- 接入 SecLab 套件语义操作日志，记录扫描提交、终态和删除操作。

### Changed

- SQLite 改用 WAL 模式、单连接池和写入批处理，降低扫描期间的数据库锁竞争。
- 前端统一使用 ESLint 与 Oxfmt 进行代码检查和格式化，并更新相关依赖与脚本。
- 扩展 Git 忽略规则，覆盖 SQLite 数据库的附属文件。

### Fixed

- 修复页面刷新后无法恢复运行中扫描任务状态、进度和实时事件的问题。
- 服务重启时将中断的扫描任务标记为失败，避免任务长期停留在等待或扫描状态。
