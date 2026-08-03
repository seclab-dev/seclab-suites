# 协议仿真 (seclab.protocol-simulation)

`seclab.protocol-simulation` 用于通过受控规则容器部署协议仿真实例，并查看实例状态与审计事件。

源码由 `seclab-suite-protocol-simulation` 独立维护，本目录只保存套件交付文件和固定版本镜像引用。

## 镜像

- `guowenju/seclab-protocol-simulation:0.1.0-alpha.1`
- `guowenju/seclab-protocol-simulation-engine:0.1.0-alpha.1`

API/UI 镜像和 engine workload 镜像分别由独立 crate 构建并单独发布版本。

## 打包

```bash
./scripts/package.sh suites/seclab.protocol-simulation
```

## 交付内容

- `suite.yaml`：套件清单。
- `compose.yaml`：套件 API/UI 服务部署规则。
- `.env.example`：本地打包校验使用的 Compose 变量示例。
- `assets/suite-icon.png`：256×256 透明 PNG 套件图标。

清单声明 `workloads.manage` 和 `captures.manage`，SecLab 安装器会为 API 服务生成实例隔离的 Agent 运行时挂载；交付 Compose 不包含节点模式判断。
