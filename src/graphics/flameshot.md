# Flameshot

> 一款功能强大、易于使用的屏幕截图工具，具有高度可定制的外观和内置的截图编辑功能。

- **官网**: [https://flameshot.org](https://flameshot.org)
- **源码仓库**: [https://github.com/flameshot-org/flameshot](https://github.com/flameshot-org/flameshot)
- **支持平台**: `Linux` / `Windows` / `macOS`
- **许可证**: `GPLv3`

## 核心特性
- [x] **离线可用**: 核心截图与编辑功能完全运行在本地。
- [x] **数据导出**: 支持保存为 PNG/JPG 等本地文件，或复制到系统剪贴板。
- [x] **隐私友好**: 程序不会未经用户请求向外部网络系统传输任何信息。
- [ ] **多端同步**: 无内置同步功能，需配合其他工具（如 Syncthing）同步截图文件夹。

## 简介与推荐理由

Flameshot 是一款备受开发者和极客喜爱的截图工具，尤其在 Linux 平台上拥有极高的人气。

它不仅仅是一个截图工具，更是一个高效的“截图即标注”的工作流中心。你可以在截图选框出现的那一刻，直接使用内置的画笔、箭头、文字、马赛克等工具进行标注，然后直接复制到剪贴板或保存。

**推荐理由：**
*   **极致的键盘操作**：支持丰富的快捷键，手不离键盘即可完成截图、编辑、保存全流程。
*   **高度可配置**：从界面颜色、按钮布局到文件名格式，几乎所有细节都可以通过配置文件或 GUI 自定义。
*   **CLI 支持**：强大的命令行接口，方便集成到脚本或系统自动化任务中。

## 安装指南

- **Linux**: 大多数发行版已收录。
  - Debian/Ubuntu: `sudo apt install flameshot`
  - Arch Linux: `sudo pacman -S flameshot`
  - Fedora: `sudo dnf install flameshot`
- **macOS**:
  - Homebrew: `brew install --cask flameshot`
  - MacPorts: `sudo port install flameshot`
- **Windows**:
  - Chocolatey: `choco install flameshot`
  - 也可以在 [GitHub Releases](https://github.com/flameshot-org/flameshot/releases) 下载最新安装包。

## 使用说明

**1. 启动截图**
- **GUI 模式**: 运行 `flameshot gui` 启动交互式截图界面。你可以在屏幕上拖拽选择区域，然后使用底部的工具栏进行标注。
- **命令行模式**:
  - `flameshot full -c`: 截取全屏并复制到剪贴板。
  - `flameshot screen -n 1 -p ~/Desktop`: 截取第一个屏幕并保存到桌面。

**2. 快捷键配置**
- **Windows**: 默认绑定 `PrtSc` (Print Screen) 键。
- **macOS**: 默认无全局快捷键，建议在系统设置中绑定 `Cmd + Shift + X` 到 `flameshot gui`。
- **Linux**: 需要在桌面环境（GNOME/KDE/i3等）中手动设置快捷键绑定到 `flameshot gui` 命令。

**3. 配置文件**
配置文件通常位于 `~/.config/flameshot/flameshot.ini`，你可以通过编辑此文件或右键托盘图标选择“配置”来修改界面颜色、文件名格式等。

## 技术栈
- **语言**: C++
- **框架**: Qt
- **构建**: CMake
