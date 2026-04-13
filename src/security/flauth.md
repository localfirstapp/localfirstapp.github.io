# Flauth

> 一个隐私优先、跨平台的开源两步验证（2FA）工具，同时提供 GUI 应用和命令行工具。

- **官网**: [https://jiacai2050.github.io/flauth/](https://jiacai2050.github.io/flauth/)
- **源码仓库**: [https://github.com/jiacai2050/flauth](https://github.com/jiacai2050/flauth)
- **支持平台**: `Android` / `macOS` / `Windows` / `Linux`
- **许可证**: `MIT`

## 核心特性
- [x] **离线可用**: 核心生成验证码功能无需网络。
- [x] **端到端加密**: 本地数据加密存储。
- [x] **数据导出**: 支持数据导出与 WebDAV 备份。
- [x] **多端同步**: 通过 WebDAV 协议（如 Nextcloud）实现自托管同步。
- [x] **命令行工具**: 提供轻量级 CLI，可直接在终端中查看 TOTP 令牌，无需 GUI。

## 简介与推荐理由
Flauth 是一个构建在 Flutter 之上的现代化 2FA 验证器。它完美诠释了 Local-first 理念：用户拥有数据的完全控制权。

与许多将数据锁定在自家云服务的验证器不同，Flauth 允许用户选择自己的同步后端（任何支持 WebDAV 的服务）。这意味着你可以在享受多设备同步便利的同时，不必担心数据泄露给第三方。其界面清爽，跨平台支持良好，是 Google Authenticator 的优秀开源替代品。

除了 GUI 应用，Flauth 还提供了命令行工具 `flauth-cli`，适合在服务器环境或终端工作流中快速查看验证码，一行命令即可安装使用。

## 安装指南

### GUI 应用
请前往 [GitHub Releases](https://github.com/jiacai2050/flauth/releases) 下载最新版本。

- **Android**: 下载 `.apk` 文件，或通过 [F-Droid](https://f-droid.org/en/packages/net.liujiacai.flauth/) 安装。
- **macOS / Windows / Linux**: 下载对应平台的预编译包。

### 命令行工具
```bash
curl -fsSL https://raw.githubusercontent.com/jiacai2050/flauth/main/docs/install.sh | sh
```

中国用户加速：
```bash
curl -fsSL https://raw.githubusercontent.com/jiacai2050/flauth/main/docs/install.sh | sh -s -- --china
```

## 使用说明

### GUI 应用
1.  **添加密钥**：支持扫描二维码或手动输入 Secret Key。
2.  **WebDAV 备份**：进入设置 -> 备份，配置你的 WebDAV 服务器地址、账号和密码。
3.  **恢复数据**：在新设备上输入同样的 WebDAV 配置即可拉取数据。

### 命令行工具
```bash
# 设置备份文件路径
export FLAUTH_BACKUP_FILE=/path/to/backup.flauth

# 显示所有令牌
flauth-cli

# 按关键词过滤
flauth-cli github
```

## 技术栈
- **框架**: Flutter（GUI）、Dart（CLI）
- **同步**: WebDAV

## 截图
![Flauth Screenshot](https://raw.githubusercontent.com/jiacai2050/flauth/main/metadata/en-US/images/phoneScreenshots/1.png)
