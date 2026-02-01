# Actual Budget

> 一个超快、隐私优先的本地个人理财工具。

- **官网**: [https://actualbudget.com/](https://actualbudget.com/)
- **源码仓库**: [https://github.com/actualbudget/actual](https://github.com/actualbudget/actual)
- **支持平台**: `Web` / `macOS` / `Windows` / `Linux` / `iOS` (PWA) / `Android` (PWA)
- **许可证**: `MIT`

## 核心特性
- [x] **离线可用**: 无论是桌面端还是网页版，断网时依然可以流畅记账。
- [x] **端到端加密**: 数据在同步到服务器前会在本地加密。
- [x] **数据导出**: 支持导出为 JSON 或 CSV 格式。
- [x] **零封包法**: 采用 Envelope Budgeting（信封预算）理念，帮你精细规划每一分钱。

## 简介与推荐理由
Actual 最初是一个商业软件，后由开发者完全开源并转交给社区维护。它采用了先进的 Local-first 架构（基于 SQLite 和 CRDTs），使得多端同步异常顺滑，且 UI 响应极快。

它不仅仅是记录流水，更强调“预算”的作用。它强制你为每一笔收入分配用途（放入信封），从而帮你摆脱月光，实现财务目标。你可以选择自托管服务端，彻底掌控敏感的财务数据。

## 安装指南
### 桌面端
从 GitHub Releases 下载客户端：
[https://github.com/actualbudget/actual/releases](https://github.com/actualbudget/actual/releases)

### 自托管服务端 (推荐)
使用 Docker 快速部署服务端以启用多端同步：

```bash
docker run -d --name actual-server -p 5006:5006 -v ./actual-data:/data actualbudget/actual-server:latest
```

部署后，在客户端设置中输入你的服务器地址即可。

## 使用说明
1.  **制定预算**: 在月初为各类支出（如房租、餐饮）分配金额。
2.  **记录交易**: 每一笔消费都从对应的预算分类中扣除。
3.  **银行同步**: 支持通过 GoCardless (欧洲) 或 SimpleFIN (北美) 自动同步银行流水（需额外配置）。

## 技术栈
- **前端**: React
- **数据库**: SQLite (WASM)
- **同步**: Custom CRDT implementation

## 截图
![Actual Budget Screenshot](https://actualbudget.com/img/budget.png)
