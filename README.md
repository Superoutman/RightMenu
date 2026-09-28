# RightMenu

**English** | [简体中文](README.zh-CN.md)

**RightMenu adds useful tools to your macOS right-click menu. Create files, copy paths, and inspect file information in Finder, with optional plugins for more features.**

[Download RightMenu](https://github.com/Superoutman/RightMenu/releases/latest) ·
[Official website](https://rightmenu.0x01.build/)

macOS 15 or later · Apple silicon · 7 languages

![RightMenu Finder context menu](Assets/README/RightMenu.png)

## Built-in essentials

These features work locally on your Mac without installing any plugins.

- Create TXT, Markdown, RTF, and valid empty Word, Excel, PowerPoint, Pages,
  Numbers, and Keynote files directly in a Finder folder or on the desktop.
- Copy the full path of one or more selected files and folders.
- View and copy file size across supported macOS releases. Images also show
  pixel dimensions and available DPI metadata.
- Control launch at login, the menu bar icon, the Dock icon, and enabled file
  formats from native Settings.
- Follow the macOS system language automatically in English, Simplified Chinese,
  Traditional Chinese, Japanese, Korean, French, and German.

## Official plugins

Install only the plugins you need. Plugins can be updated or removed independently.

| Plugin | What it adds | Status | Links |
| --- | --- | --- | --- |
| [Refresh](https://github.com/Superoutman/RightMenu-Refresh) | Adds Refresh to Finder background menus. It shows a brief nostalgic flash without actually refreshing the folder or changing files. | v1.0.4 | [Download](https://github.com/Superoutman/RightMenu-Refresh/releases/latest/download/RightMenu-Refresh.zip) · [Release notes](https://github.com/Superoutman/RightMenu-Refresh/releases/latest) |
| [Desktop Items](https://github.com/Superoutman/RightMenu-DesktopItems) | Hide or show desktop items from the desktop or Finder's Desktop folder. | v1.0.2 | [Download](https://github.com/Superoutman/RightMenu-DesktopItems/releases/latest/download/RightMenu-DesktopItems.zip) · [Release notes](https://github.com/Superoutman/RightMenu-DesktopItems/releases/latest) |
| [AI Rename](https://github.com/Superoutman/RightMenu-AIRename) | AI-assisted image and document renaming with review and undo. Requires RightMenu 0.1.70+; 0.1.71+ is recommended. | v0.2.30 **Beta** | [Download](https://github.com/Superoutman/RightMenu-AIRename/releases/download/v0.2.30/RightMenu-AIRename.zip) · [Release notes](https://github.com/Superoutman/RightMenu-AIRename/releases/tag/v0.2.30) |

Plugins marked **Beta** are still being tested.

## Install RightMenu

1. Download the latest DMG from
   [GitHub Releases](https://github.com/Superoutman/RightMenu/releases/latest).
2. Open the DMG and drag `RightMenu.app` to **Applications**.
3. Open RightMenu once.
4. If macOS asks for approval, enable RightMenu under **System Settings >
   General > Login Items & Extensions > Finder Extensions**.
5. Relaunch Finder if the context menu does not appear immediately.

RightMenu is developer-signed and notarized by Apple.

## Install and manage plugins

Download and unzip a plugin from the list above, then open **RightMenu Settings > Plugins** to import the `.rightmenuplugin` file. You can also double-click the plugin file in Finder to install it.

Review the publisher and requested permissions during installation. You can manage permissions, disable, or uninstall a plugin at any time in its settings.

For AI features, follow the prompts in the plugin settings to sign in with ChatGPT or enter an OpenAI API key, and review which data you allow the AI service to receive.

## Trust and security

- Built-in file creation and file information tools work locally on your Mac.
- RightMenu verifies plugin sources during installation and asks for permission before plugins access files or use AI services.
- AI features may send data you authorize to your chosen service; plugins cannot read your sign-in credentials.
- No ads or usage tracking.
- No Accessibility or Finder automation permissions required.

## Compatibility and current limits

- **System:** macOS 15.0 or later.
- **Processor:** Apple silicon (`arm64`) only.
- **Finder scope:** regular folders on the startup disk and the desktop.
- External drives and USB drives are not currently supported. Menus may not
  appear in some locations managed by iCloud Drive, OneDrive, Dropbox, and
  similar services.

## Develop a plugin

Want to add your own features? See the [plugin development guide](https://rightmenu.0x01.build/plugins/) to learn how to create, package, and publish a plugin.

## Updates and distribution

RightMenu supports checking for updates in the app. You can also download the latest installer from [GitHub Releases](https://github.com/Superoutman/RightMenu/releases/latest) or read the [release notes](https://github.com/Superoutman/RightMenu/releases).
