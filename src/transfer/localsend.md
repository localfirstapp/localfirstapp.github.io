# LocalSend

> 局域网内的“空投”（AirDrop），开源、跨平台且无需互联网。

- **官网**: [https://localsend.org/](https://localsend.org/)
- **源码仓库**: [https://github.com/localsend/localsend](https://github.com/localsend/localsend)
- **支持平台**: `Windows` / `macOS` / `Linux` / `Android` / `iOS`
- **许可证**: `Apache-2.0`

## 核心特性
- [x] **离线可用**: 仅需连接同一局域网（Wi-Fi 或热点），无需外部互联网。
- [x] **端到端加密**: 文件传输过程经过安全加密。
- [x] **无需注册**: 没有任何云端账户系统，安装即用。
- [x] **多端支持**: 完美覆盖主流桌面与移动操作系统。

## 简介与推荐理由
LocalSend 是目前体验最好的跨平台局域网文件传输工具。它解决了不同操作系统（如 Android 到 macOS，或 Windows 到 iOS）之间传输文件的一大痛点，且完全不依赖中心化服务器。

它会自动发现局域网内的其他 LocalSend 客户端，并为其分配一个可爱的临时名称。由于它是在本地网络内直连传输，速度仅受限于你的 Wi-Fi 硬件，通常远快于通过云端中转。对于注重隐私和效率的用户来说，它是 AirDrop 的完美全平台替代方案。

## 安装指南
### 桌面端
- **Windows**: [GitHub 下载](https://github.com/localsend/localsend/releases) 或使用 `scoop install localsend`。
- **macOS**: [App Store](https://apps.apple.com/app/localsend/id1661733215) 或 `brew install localsend`。
- **Linux**: 提供 `AppImage`, `deb`, `rpm` 等多种格式。

### 移动端
- **Android**: [Google Play](https://play.google.com/store/apps/details?id=org.localsend.localsend_app) 或 [F-Droid](https://f-droid.org/packages/org.localsend.localsend_app/)。
- **iOS**: [App Store](https://apps.apple.com/app/localsend/id1661733215)。

## 使用说明
1.  **发送**: 在“发送”页面选择文件、媒体或文本。
2.  **接收**: 确保接收设备也打开了 LocalSend，并在发送端点击出现的接收者。
3.  **设置**: 你可以在设置中修改设备名称、更改保存目录或开启“快速保存”以跳过确认。

## 技术栈
- **框架**: Flutter
- **核心逻辑**: Dart & Rust (用于提升传输性能)

## 截图
![LocalSend Screenshot](https://localsend.org/img/hero-image-desktop.webp)
