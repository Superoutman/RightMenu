# RightMenu

[English](README.md) | **简体中文**

[![Swift 6](https://img.shields.io/badge/Swift-6-F05138?logo=swift&logoColor=white)](https://www.swift.org/)
[![SwiftUI](https://img.shields.io/badge/UI-SwiftUI-0D96F6?logo=swift&logoColor=white)](https://developer.apple.com/xcode/swiftui/)
[![AppKit](https://img.shields.io/badge/macOS-AppKit-111111?logo=apple&logoColor=white)](https://developer.apple.com/documentation/appkit)
[![Finder Sync](https://img.shields.io/badge/Extension-Finder%20Sync-147EFB?logo=apple&logoColor=white)](https://developer.apple.com/documentation/findersync)
[![Sparkle](https://img.shields.io/badge/Updates-Sparkle-5E5CE6)](https://sparkle-project.org/)

**一个原生、干净自然的 macOS 右键菜单。**

[下载 RightMenu](https://github.com/Superoutman/RightMenu/releases/latest) ·
[官方网站](https://superoutman.sol.build/rightmenu/)

macOS 15 及以上 · Apple 芯片 · 支持 7 种语言

![RightMenu Finder 右键菜单](Assets/README/RightMenu.png)

## 内置核心功能

RightMenu 通过 macOS 原生 Finder Sync 框架扩展 Finder。核心操作始终在本地运行，
保持精简，并且不依赖任何可选插件。

- 在 Finder 文件夹或桌面中直接新建 TXT、Markdown、RTF，以及兼容且内容为空的
  Word、Excel、PowerPoint、Pages、Numbers 和 Keynote 文件。
- 复制一个或多个文件、文件夹的完整路径。
- 查看并复制文件大小；图片还会显示像素尺寸和可用的 DPI 元数据。
- 在原生设置中管理登录时启动、菜单栏图标、程序坞图标和启用的文件格式。
- 自动跟随 macOS 系统语言，内置英文、简体中文、繁体中文、日语、韩语、法语和德语。

## 官方插件

可选功能以独立版本、独立签名的插件交付。插件可以独立演进、更新、失败或卸载，
无需重新构建 RightMenu，也不会中断宿主的内置 Finder 操作。

| 插件 | 提供的功能 | 当前状态 | 链接 |
| --- | --- | --- | --- |
| [Refresh](https://github.com/Superoutman/RightMenu-Refresh) | 在 Finder 背景菜单中添加“刷新”。它仅显示短暂的怀旧闪屏效果，不会实际刷新目录，也不会更改任何文件。 | v1.0.4 | [下载](https://github.com/Superoutman/RightMenu-Refresh/releases/latest/download/RightMenu-Refresh.zip) · [发布说明](https://github.com/Superoutman/RightMenu-Refresh/releases/latest) |
| [Desktop Items](https://github.com/Superoutman/RightMenu-DesktopItems) | 在桌面空白处和 Finder 的桌面文件夹中添加隐藏或显示桌面文件的菜单，并通过宿主受保护的可恢复操作执行。 | v1.0.2 | [下载](https://github.com/Superoutman/RightMenu-DesktopItems/releases/latest/download/RightMenu-DesktopItems.zip) · [发布说明](https://github.com/Superoutman/RightMenu-DesktopItems/releases/latest) |
| AI Rename | 使用不透明选择权限提供可审核的 AI 文件重命名。 | 开发中 | 暂未提供 |

“下载”链接始终指向各插件最新的公开版本。

## 安装 RightMenu

1. 从 [GitHub Releases](https://github.com/Superoutman/RightMenu/releases/latest)
   下载最新 ZIP。
2. 解压 `RightMenu.app` 并移动到 **应用程序** 文件夹。
3. 启动一次 RightMenu。
4. 如果 macOS 要求批准扩展，请前往 **系统设置 > 通用 > 登录项与扩展 >
   Finder 扩展**，启用 RightMenu。
5. 如果右键菜单没有立即出现，请重新启动 Finder。

公开版本使用 RightMenu 的 Developer ID Application 身份签名并提交 Apple 公证，
只有在装订公证票据并通过 Gatekeeper 验收后才会分发。如果验证失败，请勿绕过
Gatekeeper；请从官方 Release 页面重新下载安装包。

## 安装和管理插件

打开 **RightMenu 设置 > 插件**，导入签名的 `.rightmenuplugin` 包。同一行的
“下载插件”链接可直接打开本仓库的官方插件下载区。也可以在 Finder 中双击
插件包，进入同一个由宿主管理的审核流程。

RightMenu 会在安装前校验插件包、显示经过认证的发布来源，并让新导入插件直接进入
访问审核。每组受支持的访问权限都可以独立授予或撤销。停用或删除插件会立即移除它在
Finder 中的操作，不影响内置功能或其他插件。

正式插件可以声明经过签名的 HTTPS 更新源。RightMenu 可以提示可用更新，但下载后的
替换包仍必须通过完整性、签名身份连续性、兼容性和访问权限审核。

## 信任与安全

RightMenu 将四种不同的信任关系明确分开，不把它们混为一个笼统的“认证”：

1. **宿主身份**：macOS 验证 RightMenu 的 Developer ID 签名、Apple 公证和已装订票据。
2. **插件发布者身份**：每个正式插件都使用 Ed25519 发布者密钥签名。RightMenu 可以
   识别官方发布者；首次安装其他有效发布者的插件时，用户必须审核完整公钥指纹。
3. **能力授权**：可信签名不等于运行权限。插件只能调用包内声明、宿主支持并由用户
   授权的能力，而且每次调用都会重新校验。
4. **商业授权**：可选付费功能使用独立授权的许可证签名密钥。插件代码无法读取
   许可证材料、收据、交易或支付凭据。

其他保护措施：

- Finder 扩展运行在沙盒中，并使用失败关闭的 App Group 传输链路。
- 插件只能获得短期、不透明的选择 token，不能获得文件路径、Finder 或 AppKit 对象、
  凭据，也没有环境级文件系统权限。
- 受保护的文件修改和向设备外披露数据仍必须经过宿主原生确认。
- 内置的新建文件和元数据读取始终在 Mac 本地完成。
- RightMenu 不包含分析、广告、账号系统或设备标识符。
- 不需要辅助功能权限，也不需要自动化控制 Finder。
- 常规 Finder 操作在本地运行；网络访问仅限 RightMenu 更新源和已安装正式插件声明的
  受限 HTTPS 更新源。

## 兼容性与当前限制

- **系统：** macOS 15.0 或更高版本。
- **处理器：** 仅支持 Apple 芯片（`arm64`）。
- **Finder 范围：** 启动磁盘中的普通文件夹和桌面。
- 暂不支持外置硬盘和 U 盘；部分由 iCloud Drive、OneDrive、Dropbox 等管理的位置
  可能不会显示菜单。

## 开发插件

安装后的 App 内置 `rightmenu-pluginctl`，无需克隆私有宿主源码即可创建、诊断、签名、
检查和打包插件。插件业务代码在隔离进程中运行，只通过公开、版本化的 Plugin API 与
RightMenu 交互。

请阅读 [RightMenu 插件开发指南](https://superoutman.sol.build/rightmenu/plugins/)，了解
当前插件包格式、API 契约、能力模型、签名流程、验证命令和发布规范。

## 更新与分发

RightMenu 通过公开的 Sparkle 更新源检查应用更新。每个正式版本都有匹配的
`v<version>` GitHub Release、更新包和发布说明。GitHub Release 是发布真源；可选的
Cloudflare R2 地址是经过校验的下载镜像。

这个公开仓库只保存面向发布的内容：

- `appcast.xml`：Sparkle 更新源。
- `RightMenu-<version>.zip`：可下载的应用安装包。
- `RightMenu-<version>.md`：对应版本的发布说明。
- 英文和简体中文产品文档。

应用源码在私有仓库中维护。只有经过授权的版本标签才会向这里发布匹配的产物和文档。
