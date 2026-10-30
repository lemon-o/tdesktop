# 64Gram v1.2.10 (with Download Acceleration & Streaming Preload)

基于 **64Gram (Telegram Desktop)** 深度重构与优化的下载加速与视频流媒体预缓存版本。

## 🌟 核心增强特性 (Core Enhancements)

### 1. MTProto 多线程大文件下载加速 (Download Speed Boost)
- **多通道高并发**：突破官方默认 4 并发的限制，提供 **8 线程 (Medium) / 16 线程 (High) / 32 线程 (Extreme)** 多并发通道，并利用多个 MTProto Session 均摊拉取流量。
- **底层架构安全**：严格保持官方 128KB 分片结构与上游协议 100% 严格对齐兼容，彻底解决历史版本魔改全局分片大小导致的切片索引错位与崩溃问题。
- **配置入口**：可在 `设置 (Settings) -> 64Gram 增强设置 (Enhanced Settings) -> 下载加速 (Download speed boost)` 中自由配置。

### 2. 视频流媒体大窗口顺序连续预缓存 (Video Preload Buffer Boost)
- **消灭频繁转圈卡顿**：官方客户端仅向前预取 1 MB（8 个分片），在跨国高延迟（RTT 150ms~250ms+）网络下极易断流缓冲。
- **大窗口顺序连续预取**：支持 **16 MB (Enhanced) / 32 MB (Extreme)** 顺序预取余量，始终保持 30~60 秒的播放储备，高码率视频实现秒开秒播、快速拖拽快进无卡顿。
- **配置入口**：可在 `设置 (Settings) -> 64Gram 增强设置 (Enhanced Settings) -> 视频预取缓冲区 (Video preload buffer)` 中自由配置。

---

## 📦 资产下载 (Downloads)

| 平台 | 文件名 | 说明 |
| :--- | :--- | :--- |
| **macOS** | **`Telegram-macOS.dmg`** | 原生 Apple 磁盘映像，挂载后拖入“应用程序”文件夹即可使用 |
| **Windows x64** | **`Telegram-Windows-x64.zip`** | Windows 64位绿色便携包，解压后直接运行 `Telegram.exe` |

---

*Credits: Based on [64Gram](https://github.com/TDesktop-x64/tdesktop) and [Telegram Desktop](https://github.com/telegramdesktop/tdesktop).*
