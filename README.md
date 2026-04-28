# WindowsClear (愚公移盘)
<img width="791" height="487" alt="img1" src="https://github.com/user-attachments/assets/6c10a5cd-d111-44a2-b355-dba91108de88" />
<br />
<table>
<tr>
   <td><img width="623" height="74" alt="image" src="https://github.com/user-attachments/assets/dae7fa41-dd2f-4a35-8ec4-a865896fd98d" />
</td>
</tr>
<tr>
<td>感谢 MuskAI 赞助了本项目！MuskAI 是一个集成了 Claude Code、Codex 最新模型的一站式平台，为你提供稳定、高效且高性价比的AI编程服务。本站提供灵活的订阅计划，零封号风险，国内直连，无需魔法，极速响应。通过<a href="https://muskpay.top/register?ref=2PHN9T34">此链接</a>注册！</td>
</tr>
</table>
<br />
<p align="center">
   
<p align="center">
  [<a href="https://github.com/tanaer/WindowsClear/releases">立即体验</a>] [<a href="./README_EN.md">English</a>]
</p>
<p align="center">
  <a href="https://t.me/TgTechMsgBot" target="_blank">
    <img alt="Telegram" src="https://img.shields.io/badge/Telegram-%235AA9E6?logo=telegram&labelColor=FFFFFF" />
  </a>
  <a href="https://deepwiki.com/tanaer/WindowsClear" target="_blank">
    <img alt="DeepWiki" src="https://deepwiki.com/badge.svg" />
  </a>
  <br>
  <img alt="GitHub commits since latest release" src="https://img.shields.io/github/commits-since/tanaer/WindowsClear/latest">
  <a href="https://github.com/tanaer/WindowsClear/releases" target="_blank">
    <img alt="GitHub Release" src="https://img.shields.io/github/v/release/tanaer/WindowsClear">
  </a>
</p>


## 简介

当 C 盘空间不足、C盘满了怎么办？WindowsClear 是一款面向 Windows 系统盘的 **C盘清理工具** / **c盘清理软件**，专注于释放 `AppData` 目录占用的巨量空间。它能扫描出占用空间大的软件数据文件夹，一键迁移到其他磁盘（如 D 盘），并自动创建目录联接，确保软件无缝运行，就像从未移动过一样，帮助实现 **c盘瘦身**，缓解 **C盘空间不足**。

## 适用场景（C盘满了怎么办）

*   C盘空间不足或提示 C盘满了，需要快速释放空间
*   想找可靠的 C盘清理工具 / c盘清理软件，避免误删系统文件
*   希望进行 c盘瘦身 或“类 c盘扩容”的空间腾挪，不改分区也能释放空间
*   需要清理 AppData 大文件夹，解决软件缓存/数据占用过大

## 核心功能

*   **智能扫描**: 自动分析 `%LOCALAPPDATA%` 和 `%APPDATA%`，快速定位占用超过 10% 空间的“大户”，更高效进行 C盘清理。
*   **无缝迁移**: 跨盘移动文件后，自动在原位创建 Junction 链接，软件无需重新配置。
*   **安全可靠**:
    *   **占用清理**: 自动检测文件占用，支持自动结束相关进程（使用 Windows Restart Manager 技术），非底层实现，有些不一定可以清理，但基本不影响空间释放效果。
    *   **失败回滚**: 迁移过程中若发生错误，自动尝试恢复，保障数据安全。
*   **人性化体验**:
    *   **极速性能**: 基于 Rust 开发，多线程并行扫描，速度飞快。
    *   **智能缓存**: 二次扫描无变动时秒出结果。
    *   **可视化进度**: 精确到字节的进度条，实时显示传输速度和剩余时间预估。
    *   **中英双语**: 界面支持中英文一键切换。
    *   **暂停/继续**: 大文件传输过程中可随时暂停。

## 使用方法

1.  **以管理员身份运行** `WindowsClear.exe` 。
2.  点击 **“扫描大文件夹”**。
3.  在列表中勾选你想要迁移的软件（建议先从不重要的软件开始尝试）。
4.  选择 **目标根目录**（例如 `D:\AppData`）。
5.  点击 **“执行迁移”**，等待完成即可。

## 常见问题

*   **C盘哪些文件可以删除？**
    *   WindowsClear 不建议直接删除系统文件，而是通过迁移 AppData 达到 c盘瘦身。若需要删除内容，建议优先使用系统自带“存储感知/磁盘清理”，重点清理临时文件（`%TEMP%`）、回收站、更新缓存等，避免删除 `Windows`、`Program Files` 等系统目录。
*   **为什么要管理员权限？**
    *   创建目录联接（mklink /J）和查询/结束其他进程通常需要管理员权限。
*   **迁移后软件还能打开吗？**
    *   是的。Windows 的目录联接对应用程序是透明的，软件会认为文件仍然在 C 盘。
*   **如何恢复？**
    *   只需删除 C 盘的快捷方式（带箭头图标的文件夹），然后把 D 盘的文件剪切回 C 盘原位即可。
*   **c盘扩容一定要改分区吗？**
    *   c盘扩容通常涉及分区调整。WindowsClear 提供不改分区的替代方案，通过迁移 AppData 来释放 C 盘空间。

## 构建指南

本项目使用 Rust 开发。

```bash
# 克隆仓库
git clone https://github.com/tanaer/WindowsClear.git
cd WindowsClear

# 编译 Release 版本
cargo build --release
```

## 打赏

### 爱发电

https://afdian.com/a/anyone168

### USDT-TRC20

`TREQQPsEVBMH6SqboRoVYh5Hk7fMSCGkAx`

### USDT-BEP20

`0xa37B47Ec4a6Ed783d39690c49CB1228C44068192`

## License

MIT License

## 🚀 Activity

[![Star History Chart](https://api.star-history.com/svg?repos=tanaer/WindowsClear&type=date&legend=top-left)](https://www.star-history.com/#tanaer/WindowsClear&type=date&legend=top-left)

## License
MIT License
