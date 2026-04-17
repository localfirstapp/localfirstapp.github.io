# Restic

> 快速、安全、高效的开源备份工具，支持加密、去重与多种存储后端。

- **官网**: [https://restic.net/](https://restic.net/)
- **源码仓库**: [https://github.com/restic/restic](https://github.com/restic/restic)
- **支持平台**: `Windows` / `macOS` / `Linux` / `FreeBSD` / `OpenBSD`
- **许可证**: `BSD-2-Clause`

## 核心特性
- [x] **离线可用**: 支持备份到本地磁盘、移动硬盘等本地存储介质。
- [x] **端到端加密**: 所有备份数据默认使用 AES-256 加密，密钥由用户掌握。
- [x] **数据导出**: 备份仓库格式开放、有详细文档，可通过 `restic mount` 直接浏览和恢复任意文件。
- [x] **增量去重**: 基于内容定义的分块（CDC）去重，极大节省存储空间。

## 简介与推荐理由
Restic 是一个现代化的备份工具，完美体现了 Local-first 的核心原则：用户拥有数据的完全控制权。它默认对所有备份进行加密，即使备份存储在第三方服务上，数据安全也由用户自己掌握。

Restic 采用内容可寻址的存储设计，通过智能分块和去重技术，使增量备份既快速又节省空间。它支持丰富的存储后端——从本地目录、SFTP 到 S3、B2、Azure Blob 等云存储，用户可以灵活选择备份目标而不被锁定。通过 `restic mount` 命令，用户可以像浏览普通文件夹一样浏览任意历史快照中的文件，恢复操作直观便捷。

Restic 是单一的静态编译二进制文件，无外部依赖，部署极其简单。

## 安装指南
- **macOS**: `brew install restic`。
- **Linux**: 大多数发行版已收录，如 `sudo apt install restic` 或 `sudo dnf install restic`，也可从 [GitHub Releases](https://github.com/restic/restic/releases) 下载预编译二进制文件。
- **Windows**: `scoop install restic` 或从 [GitHub Releases](https://github.com/restic/restic/releases) 下载。

## 使用说明
1. **初始化仓库**: `restic init -r /path/to/backup` 创建一个新的加密备份仓库。
2. **执行备份**: `restic backup -r /path/to/backup ~/Documents` 备份指定目录。
3. **查看快照**: `restic snapshots -r /path/to/backup` 列出所有备份快照。
4. **恢复文件**: `restic restore latest -r /path/to/backup -t /tmp/restore` 恢复最新快照。
5. **浏览快照**: `restic mount -r /path/to/backup /mnt/restic` 将备份挂载为文件系统浏览。
6. **清理旧快照**: `restic forget --keep-last 10 --prune -r /path/to/backup` 保留最近 10 个快照并回收空间。

## 技术栈
- **语言**: Go
- **加密**: AES-256-CTR + Poly1305-AES
- **去重**: 基于 Rabin 指纹的内容定义分块（CDC）
- **存储后端**: 本地文件系统 / SFTP / S3 / B2 / Azure Blob / Google Cloud Storage / rclone
