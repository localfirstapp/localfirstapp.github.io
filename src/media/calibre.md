# Calibre

> 功能全面的开源电子书管理工具，支持格式转换、元数据编辑与本地书库管理。

- **官网**: [https://calibre-ebook.com/](https://calibre-ebook.com/)
- **源码仓库**: [https://github.com/kovidgoyal/calibre](https://github.com/kovidgoyal/calibre)
- **支持平台**: `Windows` / `macOS` / `Linux`
- **许可证**: `GPL-3.0`

## 核心特性
- [x] **离线可用**: 所有功能完全在本地运行，无需网络连接。
- [x] **数据导出**: 书库以开放的文件夹结构存储，支持导出为 EPUB、MOBI、PDF、AZW3 等多种格式。
- [x] **格式转换**: 内置强大的电子书格式转换引擎，支持数十种输入输出格式。
- [x] **无需注册**: 无账户体系，无云依赖，数据完全归用户所有。

## 简介与推荐理由
Calibre 是电子书爱好者的必备工具，也是 Local-first 精神在电子书领域的最佳实践。它将用户的所有电子书以清晰的文件夹结构存储在本地磁盘上，每本书都有独立的目录，元数据保存在本地 SQLite 数据库中。用户可以随时复制、迁移整个书库，不存在任何锁定。

Calibre 的格式转换能力极为出色，可以在 EPUB、MOBI、AZW3、PDF、TXT、HTML 等数十种格式之间自由转换，并在转换过程中调整排版样式。此外，它还内置了电子书阅读器、元数据编辑器、新闻抓取器（可将网页/RSS 转为电子书）以及内容服务器（可在局域网内共享书库）。

## 安装指南
- **Windows**: [官网下载](https://calibre-ebook.com/download_windows)。
- **macOS**: [官网下载](https://calibre-ebook.com/download_osx) 或 `brew install --cask calibre`。
- **Linux**: [官网下载](https://calibre-ebook.com/download_linux) 或通过系统包管理器安装，如 `sudo apt install calibre`。

## 使用说明
1. **导入书籍**: 点击"添加书籍"按钮或直接拖拽电子书文件到主窗口。
2. **格式转换**: 选中书籍后点击"转换书籍"，选择目标格式并调整转换参数。
3. **编辑元数据**: 双击书籍条目可编辑标题、作者、封面、标签等元数据。
4. **发送到设备**: 连接 Kindle 等电子书阅读器后，点击"发送到设备"即可传输。
5. **内容服务器**: 通过"连接/共享 > 启动内容服务器"可在局域网内通过浏览器访问书库。

## 技术栈
- **语言**: Python / C
- **GUI 框架**: Qt
- **数据存储**: SQLite（元数据）+ 本地文件系统（电子书文件）
