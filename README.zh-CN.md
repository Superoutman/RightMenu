# RightMenu

[English](README.md) | **简体中文**

**RightMenu 是一款原生 macOS 右键菜单工具，让你在 Finder 中快速新建文件、复制路径和查看文件信息，还可以通过可选插件扩展功能。**

[下载 RightMenu](https://github.com/Superoutman/RightMenu/releases/latest) ·
[官方网站](https://rightmenu.0x01.build/)

macOS 15 及以上 · Apple 芯片 · 支持 7 种语言

![RightMenu Finder 右键菜单](Assets/README/RightMenu.png)

## 内置核心功能

以下功能在 Mac 本地运行，无需安装插件。

- 在 Finder 文件夹或桌面中直接新建 TXT、Markdown、RTF，以及兼容且内容为空的
  Word、Excel、PowerPoint、Pages、Numbers 和 Keynote 文件。
- 复制一个或多个文件、文件夹的完整路径。
- 在支持的 macOS 版本上查看并复制文件大小；图片还会显示像素尺寸和可用的 DPI 元数据。
- 在原生设置中管理登录时启动、菜单栏图标、程序坞图标和启用的文件格式。
- 自动跟随 macOS 系统语言，内置英文、简体中文、繁体中文、日语、韩语、法语和德语。

## 官方插件

按需安装插件；每个插件都可以独立更新或卸载。

| 插件 | 提供的功能 | 当前状态 | 链接 |
| --- | --- | --- | --- |
| [Refresh](https://github.com/Superoutman/RightMenu-Refresh) | 在 Finder 背景菜单中添加“刷新”。它仅显示短暂的怀旧闪屏效果，不会实际刷新目录，也不会更改任何文件。 | v1.0.4 | [下载](https://github.com/Superoutman/RightMenu-Refresh/releases/latest/download/RightMenu-Refresh.zip) · [发布说明](https://github.com/Superoutman/RightMenu-Refresh/releases/latest) |
| [Desktop Items](https://github.com/Superoutman/RightMenu-DesktopItems) | 在桌面或 Finder 的桌面文件夹中，一键隐藏或显示桌面文件。 | v1.0.2 | [下载](https://github.com/Superoutman/RightMenu-DesktopItems/releases/latest/download/RightMenu-DesktopItems.zip) · [发布说明](https://github.com/Superoutman/RightMenu-DesktopItems/releases/latest) |
| [AI Rename](https://github.com/Superoutman/RightMenu-AIRename) | 根据图片和文档内容生成文件名，支持审阅及撤销。需要 RightMenu 0.1.70+，建议 0.1.71+。 | v0.2.30 **Beta** | [下载](https://github.com/Superoutman/RightMenu-AIRename/releases/download/v0.2.30/RightMenu-AIRename.zip) · [发布说明](https://github.com/Superoutman/RightMenu-AIRename/releases/tag/v0.2.30) |

标记为 **Beta** 的插件仍处于测试阶段。

## 安装 RightMenu

1. 从 [GitHub Releases](https://github.com/Superoutman/RightMenu/releases/latest)
   下载最新 DMG。
2. 打开 DMG，将 `RightMenu.app` 拖入 **应用程序** 文件夹。
3. 启动一次 RightMenu。
4. 如果 macOS 要求批准扩展，请前往 **系统设置 > 通用 > 登录项与扩展 >
   Finder 扩展**，启用 RightMenu。
5. 如果右键菜单没有立即出现，请重新启动 Finder。

RightMenu 已完成开发者签名和 Apple 公证。

## 安装和管理插件

从上方列表下载插件并解压，然后打开 **RightMenu 设置 > 插件**，导入 `.rightmenuplugin` 文件。也可以在 Finder 中双击插件文件安装。

安装时，请查看发布者信息和所需权限。你可以随时在插件设置中管理权限、停用或卸载插件。

使用 AI 功能时，按插件设置中的提示登录 ChatGPT 或填写 OpenAI API Key，并确认允许发送给 AI 服务的数据。

## 信任与安全

- 内置的新建文件和文件信息查看功能在本地运行。
- 安装插件时会验证其来源，插件使用文件或 AI 服务前需要你的授权。
- AI 功能可能将你授权的数据发送给所选服务；插件无法读取你的登录凭据。
- 无广告，无使用行为追踪。
- 无需辅助功能或 Finder 自动化权限。

## 兼容性与当前限制

- **系统：** macOS 15.0 或更高版本。
- **处理器：** 仅支持 Apple 芯片（`arm64`）。
- **Finder 范围：** 启动磁盘中的普通文件夹和桌面。
- 暂不支持外置硬盘和 U 盘；部分由 iCloud Drive、OneDrive、Dropbox 等管理的位置
  可能不会显示菜单。

## 开发插件

想为 RightMenu 添加自己的功能？请查看[插件开发指南](https://rightmenu.0x01.build/plugins/)，了解如何创建、打包和发布插件。

## 更新与分发

RightMenu 支持应用内检查更新。你也可以从 [GitHub Releases](https://github.com/Superoutman/RightMenu/releases/latest) 下载最新安装包，或查看[发布说明](https://github.com/Superoutman/RightMenu/releases)。
