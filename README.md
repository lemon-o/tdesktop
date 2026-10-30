# 64Gram (Enhanced with Download Speed & Video Streaming Boost)

[![Preview of 64Gram][preview_image]][preview_image_url]

本项目基于 [64Gram (TDesktop-x64)](https://github.com/TDesktop-x64/tdesktop) 与官方 [Telegram Desktop](https://github.com/telegramdesktop/tdesktop) 构建，在其丰富增强特性的基础上，**重构并引入了多线程 MTProto 大文件下载加速**与**视频流媒体大窗口连续顺序预缓存加速**功能。

The source code is published under GPLv3 with OpenSSL exception, the license is available [here][license].

---

## ⚡ 核心增强特性 (Core Enhancements)

### 1. MTProto 多线程大文件下载加速 (Download Speed Boost)
- **多通道高并发**：突破官方默认 4 并发的限制，提供 **8 线程 (Medium) / 16 线程 (High) / 32 线程 (Extreme)** 多并发通道，并利用多个 MTProto Session 均摊拉取流量。
- **底层架构安全**：严格保持官方 128KB 分片结构与上游协议 100% 对齐兼容，彻底杜绝历史版本因暴力魔改底层分片大小而导致的切片索引错位、本地缓存损坏与崩溃问题。
- **下载速度翻倍**：大文件、压缩包、离线资源下载轻松跑满宽带与代理带宽上限。
- **配置入口**：`设置 (Settings)` -> `64Gram 增强设置 (Enhanced Settings)` -> `下载加速 (Download speed boost)`。

### 2. 视频流媒体大窗口顺序连续预缓存 (Video Preload Buffer Boost)
- **告别频繁转圈**：针对官方播放器仅预取 1MB (8 个分片) 导致跨国代理/高延迟网络 (RTT 150ms~250ms+) 下极易断流缓冲转圈的元凶进行专项重构。
- **大窗口顺序连续预取**：支持 **16MB (Enhanced) / 32MB (Extreme)** 顺序预取余量，播放时始终在后台保持 30~60 秒的音视频储备。
- **流畅秒开秒播**：高码率 1080P/4K 视频秒开秒播，随意拖拽进度条无需等待缓冲。
- **配置入口**：`设置 (Settings)` -> `64Gram 增强设置 (Enhanced Settings)` -> `视频预取缓冲区 (Video preload buffer)`。

---

## 📦 客户端下载 (Downloads & Releases)

最新打包构建可前往 [GitHub Releases](https://github.com/lemon-o/tdesktop/releases) 页面下载：

- **macOS**: `Telegram-macOS.dmg`
  - 原生 Apple 磁盘映像（DMG 格式），下载挂载后将 `Telegram.app` 拖入“应用程序”文件夹即可使用。
- **Windows x64**: `Telegram-Windows-x64.zip`
  - Windows 64 位原生绿色便携包，解压后双击 `Telegram.exe` 即可运行。

---

## [原项目增强功能一览 (Features)](features.md)

除了上述新增的下载与流媒体加速特性外，完整继承了 64Gram 备受好评的实用功能：
- 消息防撤回与已删除消息提示
- 自定义群组与私聊双向彻底删除
- 多账号登录支持（最多支持 10 个账号同时在线）
- 显示聊天 ID (Chat ID) 与消息 ID (Message ID)
- 无引用转发 (Forward without quote)
- 解锁全部群组权限限制
- 更多功能详见 [features.md](features.md)

## 支持的操作系统 (Supported Systems)

- **Windows**: Windows 7 及更高版本（64 位原生构建）
- **macOS**: macOS 10.12 及更高版本
- **Linux**: Linux 64-bit

## 界面语言与本地化 (Localization)

如果需要翻译或更新多语言包，欢迎提交 Pull Request：
- [Localization 语言仓库](https://github.com/TDesktop-x64/Localization)
- [语言翻译模板](https://github.com/TDesktop-x64/Localization/blob/master/en.json)

## 源码构建指南 (Build Instructions)

- [Windows (32-bit and 64-bit)][win]
- [macOS][mac]
- [GNU/Linux using Docker][linux]

## 相关链接 (Links)

- [本项目 GitHub Releases](https://github.com/lemon-o/tdesktop/releases)
- [64Gram 官方频道](https://t.me/tg_x64)
- [64Gram 官方讨论群](https://t.me/tg_x64_chat)

[//]: # (LINKS)
[license]: LICENSE
[win]: docs/building-win.md
[mac]: docs/building-mac.md
[linux]: docs/building-linux.md
[preview_image]: https://github.com/TDesktop-x64/tdesktop/blob/dev/docs/assets/preview.png "Preview of 64Gram Desktop"
[preview_image_url]: https://raw.githubusercontent.com/TDesktop-x64/tdesktop/dev/docs/assets/preview.png
