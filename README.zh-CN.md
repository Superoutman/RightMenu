# RightMenu

[English](README.md) | **简体中文**

[![Swift 6](https://img.shields.io/badge/Swift-6-F05138?logo=swift&logoColor=white)](https://www.swift.org/)
[![SwiftUI](https://img.shields.io/badge/UI-SwiftUI-0D96F6?logo=swift&logoColor=white)](https://developer.apple.com/xcode/swiftui/)
[![AppKit](https://img.shields.io/badge/macOS-AppKit-111111?logo=apple&logoColor=white)](https://developer.apple.com/documentation/appkit)
[![Finder Sync](https://img.shields.io/badge/Extension-Finder%20Sync-147EFB?logo=apple&logoColor=white)](https://developer.apple.com/documentation/findersync)
[![Sparkle](https://img.shields.io/badge/Updates-Sparkle-5E5CE6)](https://sparkle-project.org/)

**干净、原生的 macOS 右键菜单。**

[下载最新版本](https://github.com/Superoutman/RightMenu/releases/latest)

[官方网站](https://superoutman.sol.build/rightmenu/)

![RightMenu Finder 右键菜单](Assets/README/RightMenu.png)

## 理念

RightMenu 通过 macOS 原生 Finder Sync 扩展与 Finder 集成。更干净、更自然，尽量保持原生系统体验，只嵌入那些真正需要的功能。

## 功能特色

- 在任意 Finder 文件夹或桌面的空白处，通过右键菜单直接新建文件。
- 支持新建 TXT、Markdown、RTF、Word、Excel、PowerPoint、Pages、Numbers
  和 Keynote 文件。
- 在文件或文件夹的右键菜单中复制完整路径。
- 查看并复制单个文件的大小；图片还会显示像素尺寸和可用的 DPI 元数据。
- 可分别显示或隐藏菜单栏图标和程序坞图标。
- 没有复杂的设置，配置一目了然，开箱即用。
- 自动跟随 macOS 系统语言，内置英文、简体中文、繁体中文、日语、韩语、法语和德语。

## 安装

1. 从 [GitHub Releases](https://github.com/Superoutman/RightMenu/releases/latest)
   下载最新 ZIP 文件。
2. 解压 `RightMenu.app`，并将其移动到 **应用程序** 文件夹。
3. 启动一次 RightMenu。
4. 如果 macOS 因无法验证开发者而阻止应用运行，请关闭警告，然后打开
   **系统设置 > 隐私与安全性**，向下滚动到“安全性”区域，点击 **仍要打开**，
   再确认 **打开**。
5. 如果 macOS 要求批准扩展，请前往 **系统设置 > 通用 > 登录项与扩展 >
   Finder 扩展**，启用 RightMenu。
6. 如果右键菜单没有立即出现，请重新启动 Finder。

> 仅当 RightMenu 来自此官方 GitHub Release 页面时，才应使用 **仍要打开**。
> 为降低早期开发与分发成本，当前版本没有使用付费 Apple Developer 分发凭据进行
> 签名和公证。因此 macOS 会显示首次启动安全警告；这并不表示 RightMenu 在你的
> Mac 上检测到了问题。

## 使用方法

- 在 Finder 文件夹或桌面空白处点击右键，然后选择 **新建文件** 和所需格式。
- 选中一个或多个文件或文件夹，点击右键并选择 **复制文件路径**。
- 选中单个文件并点击右键，可以查看和复制文件大小。图片还会在文件大小前显示
  像素尺寸和可用的 DPI 信息，并以 `｜` 分隔，例如：
  `2,056 × 1,722 px (300 dpi) ｜ 905 KB`。
- 可以从菜单栏图标、程序坞图标、启动台或“应用程序”文件夹打开 RightMenu 设置。
- 在设置中配置文件格式、登录时启动以及图标显示状态。

## 安全与隐私

- **原生沙盒化 Finder 扩展：** 右键菜单通过 Apple Finder Sync 框架提供，扩展在
  启用 App Sandbox 的环境中运行。
- **无需辅助功能或 Finder 控制权限：** RightMenu 不会申请辅助功能权限，也不会
  申请自动化控制 Finder 的权限。
- **本地文件处理：** 新文件创建和文件元数据读取均在你的 Mac 本地完成。RightMenu
  不会上传文件内容、文件名、所选路径、元数据或剪贴板数据。
- **无追踪：** 应用不包含分析、广告、遥测、账号系统或设备标识符。
- **更新签名验证：** 安装更新前，Sparkle 会使用应用内置的 EdDSA 公钥验证更新包。
- **最少的网络活动：** 自动更新检查只会读取公开的 RightMenu 更新源；常规 Finder
  菜单操作均在本地完成。

这些应用层保护与 Apple 的 Developer ID 和公证检查相互独立。为降低早期开发成本，
当前版本采用 ad-hoc 代码签名，因此 macOS 会显示上文所述的首次启动安全警告。

## 兼容性

- **最低系统版本：** macOS 15.0 或更高版本。
- **处理器：** 仅支持 Apple 芯片（`arm64`），不支持 Intel Mac。
- 发布候选版本使用 macOS 26 的原生界面，并会在发布前于 macOS 15 上完成启动和
  生命周期测试。

## 更新

RightMenu 会通过本仓库的 Sparkle 更新源检查新版本。发现新版本后，菜单栏菜单和
设置窗口中都会出现更新操作。

每个已发布版本都会在 GitHub Release 中提供更新包和英文更新说明。

## 仓库内容

- `appcast.xml`：Sparkle 更新源。
- `RightMenu-<version>.zip`：可下载的应用压缩包。
- `RightMenu-<version>.md`：对应版本的更新说明。

应用源代码在私有仓库中维护。只有推送与版本号匹配的标签后，发布产物才会自动同步
到此仓库。
