# Changelog

格式遵循 [Keep a Changelog](https://keepachangelog.com/zh-CN/1.1.0/)，并遵循 [Semantic Versioning](https://semver.org/lang/zh-CN/)。

## [Unreleased]

### Added

- 增加 Telnet、MySQL、PostgreSQL、SMB、LDAP 仿真，并保持 alpha v1 契约。
- 增加 DNS TCP/UDP 双端点仿真，默认以同一主机端口 1053 同时发布 TCP 与 UDP。
- 支持具名多端点工作负载、整实例抓包和结构化幂等审计事件。

### Changed

- 规则包导入改为实际验证 Ed25519/minisign 签名，并校验 v1 schema、端点与协议行为。
- 诱捕审计改为从运行实例操作菜单进入，按实例分页展示并在实例下线后自动销毁，单实例默认保留最新 10,000 条记录。
- 仿真引擎启动信息仅写入对应工作负载容器日志，不再作为诱捕审计事件展示。
- “规则整编”列表根据可用视口高度自动调整每页显示数量，减少大窗口下的空白区域。
- 实例监听端点统一显示为 `端口/协议`，隐藏内部端点 ID。

### Fixed

- 修复新增协议的规则详情错误回退到 HTTP，导致显示 Nginx Server Header 和首屏 HTML 的问题。
- 部署规则实例时仅在确认按钮展示加载状态，避免全页面遮罩造成表格表头异常高亮。

## [0.1.0-alpha.1] - 2026-08-09

### Added

- 首次发布协议仿真套件 API/UI 镜像和 engine workload 镜像。
- 支持导入协议仿真规则包并部署仿真实例。
- 支持 HTTP、Redis、SMTP、POP3、IMAP、SSH、FTP、RDP 协议仿真。
- 支持通过 Agent suite workload API 拉起和销毁规则容器。
- 支持实例审计、PCAP 取证、空包通知和浏览器预览能力。
- 前端接入 SecLab UI、SDL Token 和套件 SDK 的主题、语言、导航能力。
- 接入 SecLab 套件语义操作日志，记录规则、仿真实例和抓包生命周期。

### Changed

- 声明工作负载管理与抓包能力，由 SecLab 自动注入实例隔离的 Agent 运行时配置。
- 移除套件 Compose 中针对本地 UDS 和节点 HTTPS 的手工环境变量与挂载。
- HTTP 仿真规则的首屏 HTML 改为在套件内安全预览，不再依赖主控内置浏览器应用。

### Fixed

- 修复部署确认按钮可重复提交，导致同一端口创建重复实例的问题。
- 部署前检查实例端口与目标节点宿主机端口，冲突时显示本地化通知且不保留失败实例。
