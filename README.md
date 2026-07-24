# RightMenu

**English** | [简体中文](README.zh-CN.md)

[![Swift 6](https://img.shields.io/badge/Swift-6-F05138?logo=swift&logoColor=white)](https://www.swift.org/)
[![SwiftUI](https://img.shields.io/badge/UI-SwiftUI-0D96F6?logo=swift&logoColor=white)](https://developer.apple.com/xcode/swiftui/)
[![AppKit](https://img.shields.io/badge/macOS-AppKit-111111?logo=apple&logoColor=white)](https://developer.apple.com/documentation/appkit)
[![Finder Sync](https://img.shields.io/badge/Extension-Finder%20Sync-147EFB?logo=apple&logoColor=white)](https://developer.apple.com/documentation/findersync)
[![Sparkle](https://img.shields.io/badge/Updates-Sparkle-5E5CE6)](https://sparkle-project.org/)

**A clean, native right-click menu for macOS.**

[Download the latest release](https://github.com/Superoutman/RightMenu/releases/latest)

[Official website](https://superoutman.sol.build/rightmenu/)

![RightMenu Finder context menu](Assets/README/RightMenu.png)

## Features

- Cleaner and more natural, while preserving the native macOS experience.
- Create new files directly from the background context menu of any Finder
  folder or the desktop.
- Create TXT, Markdown, RTF, Word, Excel, PowerPoint, Pages, Numbers, and Keynote
  files.
- Copy the full path of selected files and folders from their context menu.
- View and copy the size of a selected file. Images additionally show pixel
  dimensions and available DPI metadata.
- Choose which file formats appear in the **New File** submenu.
- Independently show or hide the menu bar icon and Dock icon.
- No complicated setup—everything is clear at a glance and ready to use out of the box.
- Follow the macOS system language automatically, with English, Simplified and
  Traditional Chinese, Japanese, Korean, French, and German included.

RightMenu integrates with Finder through a native Finder Sync extension.
Right-click an empty area to create a new file; on the desktop or in the Desktop
folder, you can also hide or show desktop items. Right-click a file or folder to
copy its path. When a single file is selected, RightMenu also displays available
file and image details.

## Installation

1. Download the latest ZIP from
   [GitHub Releases](https://github.com/Superoutman/RightMenu/releases/latest).
2. Extract `RightMenu.app` and move it to the **Applications** folder.
3. Open RightMenu once.
4. If macOS blocks the app because it cannot verify the developer, close the
   warning. Open **System Settings > Privacy & Security**, scroll down to the
   Security section, click **Open Anyway**, then confirm **Open**.
5. If macOS asks for approval, enable RightMenu under **System Settings >
   General > Login Items & Extensions > Finder Extensions**.
6. Relaunch Finder if the context menu does not appear immediately.

> Only use **Open Anyway** when RightMenu was downloaded from this official
> GitHub Release page. To keep early development and distribution costs low,
> current builds are not signed and notarized with paid Apple Developer
> distribution credentials. This is why macOS shows the first-launch security
> warning; it does not indicate that RightMenu has detected a problem on your
> Mac.

## Usage

- Right-click an empty area in a Finder folder or on the desktop, then choose
  **New File** and a file type.
- Right-click one or more files or folders, then choose **Copy File Path**.
- Right-click a single file to view and copy its size. For images, dimensions
  and available DPI appear before the file size, separated by `｜`, for example:
  `2,056 × 1,722 px (300 dpi) ｜ 905 KB`.
- Open RightMenu Settings from its menu bar icon, Dock icon, Launchpad, or the
  Applications folder.
- Use Settings to configure file formats, launch at login, and icon visibility.

## Security & Privacy

- **Native, sandboxed Finder extension:** the context menu is provided through
  Apple's Finder Sync framework, and the extension runs with App Sandbox
  enabled.
- **No Accessibility or Finder-control permission:** RightMenu does not request
  Accessibility access or permission to automate and control Finder.
- **Local file handling:** new files are created and file metadata is inspected
  on your Mac. RightMenu does not upload file contents, filenames, selected
  paths, metadata, or clipboard data.
- **No tracking:** the app contains no analytics, advertising, telemetry,
  account system, or device identifier.
- **Signed update verification:** update archives are verified by Sparkle using
  the public EdDSA key embedded in the app before installation.
- **Minimal network activity:** automatic update checks read only the public
  RightMenu update feed. Normal Finder menu actions work locally.

These application-level protections are separate from Apple's Developer ID and
notarization checks. Current builds use ad-hoc code signing to keep early
development costs low, so macOS displays the first-launch warning described
above.

## Compatibility

- **Minimum system:** macOS 15.0 or later.
- **Processor:** Apple Silicon (`arm64`) only. Intel-based Macs are not
  supported.
- Release candidates use the native macOS 26 presentation and are also
  launched and lifecycle-tested on macOS 15 before publication.

## Updates

RightMenu checks this repository's Sparkle feed for updates. When a new version
is available, an update action appears in both the menu bar menu and the
Settings window.

Every published version is available as a GitHub Release with its update
archive and English release notes.

## Repository contents

- `appcast.xml`: the Sparkle update feed.
- `RightMenu-<version>.zip`: the downloadable application archive.
- `RightMenu-<version>.md`: the release notes for that version.

The application source is maintained in a private repository. Release artifacts
are published here automatically only when a matching version tag is pushed.
