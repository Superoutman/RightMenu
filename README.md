# RightMenu

A clean, native context-menu extension for macOS Finder.

[Download the latest release](https://github.com/Superoutman/RightMenu-Releases/releases/latest)

## Features

- Create new files directly from the background context menu of any Finder
  folder or the desktop.
- Create TXT, Markdown, RTF, Word, Excel, and PowerPoint files.
- Copy the full path of selected files and folders from their context menu.
- Choose which file formats appear in the **New File** submenu.
- Independently show or hide the menu bar icon and Dock icon.
- Launch automatically at login.
- Receive in-app update notifications through Sparkle.
- Follow the macOS system language automatically, with English and Simplified
  Chinese included.

RightMenu uses the native Finder Sync extension mechanism. **New File** appears
when you right-click an empty area, while **Copy File Path** appears when you
right-click a file or folder.

## Installation

1. Download the latest ZIP from
   [GitHub Releases](https://github.com/Superoutman/RightMenu-Releases/releases/latest).
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
- Open RightMenu Settings from its menu bar icon, Dock icon, Launchpad, or the
  Applications folder.
- Use Settings to configure file formats, launch at login, and icon visibility.

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
