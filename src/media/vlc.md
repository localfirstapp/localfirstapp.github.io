# VLC media player

> 自由、开源、跨平台的多媒体播放器，支持几乎所有音视频格式。

- **官网**: [https://www.videolan.org/vlc/](https://www.videolan.org/vlc/)
- **源码仓库**: [https://code.videolan.org/videolan/vlc](https://code.videolan.org/videolan/vlc)
- **支持平台**: `Windows` / `macOS` / `Linux` / `Android` / `iOS`
- **许可证**: `GPL-2.0`

## 核心特性
- [x] **离线可用**: 完全本地运行，无需任何网络连接。
- [x] **数据导出**: 播放列表支持 M3U/XSPF 等标准格式导出。
- [x] **格式全面**: 内置解码器，支持几乎所有已知的音视频编码格式，无需额外安装解码包。
- [x] **无需注册**: 无账户体系，无遥测，安装即用。

## 简介与推荐理由
VLC 是由 VideoLAN 社区开发的老牌开源媒体播放器，自 2001 年首次发布以来已成为全球最广泛使用的播放器之一。它是 Local-first 理念的典范：所有功能完全在本地运行，不依赖任何云服务，不收集用户数据，也没有广告或付费升级。

VLC 内置了大量编解码器（H.264、H.265/HEVC、VP9、AV1、FLAC、Opus 等），这意味着用户无需手动寻找并安装第三方解码包。除了播放媒体文件外，VLC 还支持流媒体播放、格式转换、视频滤镜、字幕加载等高级功能，是一个真正的"瑞士军刀"级多媒体工具。

## 安装指南
### 桌面端
- **Windows**: [官网下载](https://www.videolan.org/vlc/download-windows.html) 或 `scoop install vlc`。
- **macOS**: [官网下载](https://www.videolan.org/vlc/download-macosx.html) 或 `brew install --cask vlc`。
- **Linux**: 大多数发行版的软件源均已收录，如 `sudo apt install vlc` 或 `sudo dnf install vlc`。

### 移动端
- **Android**: [Google Play](https://play.google.com/store/apps/details?id=org.videolan.vlc) 或 [F-Droid](https://f-droid.org/packages/org.videolan.vlc/)。
- **iOS**: [App Store](https://apps.apple.com/app/vlc-media-player/id650377962)。

## 使用说明
1. **播放文件**: 直接拖拽文件到 VLC 窗口，或通过菜单"媒体 > 打开文件"选择。
2. **播放列表**: 通过"视图 > 播放列表"管理和保存播放队列。
3. **格式转换**: 通过"媒体 > 转换/保存"可将媒体文件转码为其他格式。
4. **字幕加载**: 播放视频时，通过"字幕 > 添加字幕文件"加载外挂字幕。

## 技术栈
- **语言**: C / C++
- **多媒体框架**: libVLC（自研核心引擎）
- **跨平台 UI**: Qt（桌面端）
