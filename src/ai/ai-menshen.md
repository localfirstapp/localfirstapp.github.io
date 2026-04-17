# ai-menshen

> 一个轻量级、本地优先的 AI 网关，代理任何 OpenAI 兼容 API，提供密钥注入、模型覆盖、故障转移、用量审计和响应缓存——所有 API 密钥和日志都严格保留在本地。

- **源码仓库**: [https://github.com/jiacai2050/ai-menshen](https://github.com/jiacai2050/ai-menshen)
- **支持平台**: `Linux` / `macOS`
- **许可证**: `MIT`

## 核心特性
- [x] **离线可用**: 单个 Go 二进制文件，除 SQLite 外零外部依赖。
- [x] **密钥注入 (BYOK)**: 真实 API 密钥保存在本地 TOML 配置文件中，客户端无需感知。
- [x] **多提供商加权负载均衡**: 通过 `weight` 字段控制请求分配比例。
- [x] **自动故障转移**: 网络错误、5xx、429 等自动切换到下一个提供商。
- [x] **用量审计**: 自动提取 token 用量并存储到 SQLite，支持流式和非流式请求。
- [x] **响应缓存**: 可选缓存非流式 200 响应，加速重复请求。
- [x] **模型覆盖**: 可按提供商强制替换客户端请求中的模型名称。
- [x] **内置仪表盘**: 自带轻量 Web 仪表盘，所有 JS/CSS 内嵌，适合离线环境。

## 简介与推荐理由
ai-menshen（门神）是一个为个人和小团队设计的 AI API 网关。它完美诠释了 Local-first 理念：你的 API 密钥永远不会离开本地配置文件，所有请求和响应日志都存储在本地 SQLite 中。

与商业 API 网关不同，ai-menshen 不依赖任何云服务。它作为一个透明代理运行在你的机器上，客户端只需将 API 地址指向 `localhost:8080` 即可使用。多提供商加权路由和自动故障转移确保了高可用性，而内置的用量审计帮助你追踪每一次 API 调用的 token 消耗。

## 安装指南

### 一键安装（Linux & macOS）
```bash
curl -fsSL https://raw.githubusercontent.com/jiacai2050/ai-menshen/main/install.sh | sh
```

中国用户加速：
```bash
curl -fsSL https://raw.githubusercontent.com/jiacai2050/ai-menshen/main/install.sh | sh -s -- --china
```

### 通过 Go Install
```bash
go install github.com/jiacai2050/ai-menshen@latest
```

## 使用说明

1. **生成配置文件**：
   ```bash
   mkdir -p ~/.config/ai-menshen
   ai-menshen -gen-config > ~/.config/ai-menshen/config.toml
   ```

2. **编辑配置**，填入你的上游 API 密钥：
   ```bash
   vi ~/.config/ai-menshen/config.toml
   ```

3. **启动网关**：
   ```bash
   ai-menshen -config ~/.config/ai-menshen/config.toml
   ```

4. **连接使用**，将 OpenAI 客户端指向 `http://localhost:8080`：
   ```python
   from openai import OpenAI

   client = OpenAI(
       base_url="http://localhost:8080",
       api_key="your-auth-token"
   )

   response = client.chat.completions.create(
       model="gpt-4o",
       messages=[{"role": "user", "content": "Hello!"}],
       stream=True
   )
   for chunk in response:
       print(chunk.choices[0].delta.content or "", end="")
   ```

## 技术栈
- **语言**: Go
- **存储**: SQLite
- **配置**: TOML

## 截图

| 概览与趋势 | 审计日志 |
| :---: | :---: |
| ![Overview](https://raw.githubusercontent.com/jiacai2050/ai-menshen/main/docs/screenshot-overview.webp) | ![Logs](https://raw.githubusercontent.com/jiacai2050/ai-menshen/main/docs/screenshot-logs.webp) |
