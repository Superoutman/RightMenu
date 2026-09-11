# RightMenu

**English** | [简体中文](README.zh-CN.md)

[![Swift 6](https://img.shields.io/badge/Swift-6-F05138?logo=swift&logoColor=white)](https://www.swift.org/)
[![SwiftUI](https://img.shields.io/badge/UI-SwiftUI-0D96F6?logo=swift&logoColor=white)](https://developer.apple.com/xcode/swiftui/)
[![AppKit](https://img.shields.io/badge/macOS-AppKit-111111?logo=apple&logoColor=white)](https://developer.apple.com/documentation/appkit)
[![Finder Sync](https://img.shields.io/badge/Extension-Finder%20Sync-147EFB?logo=apple&logoColor=white)](https://developer.apple.com/documentation/findersync)
[![Sparkle](https://img.shields.io/badge/Updates-Sparkle-5E5CE6)](https://sparkle-project.org/)

**RightMenu is a clean, native right-click menu for macOS that enhances Finder with useful built-in tools and an extensible plugin system. Create files, copy paths, inspect file information, install optional plugins, or build your own extensions with its public Plugin API—all while keeping the experience lightweight, local, and native to macOS.**

[Download RightMenu](https://github.com/Superoutman/RightMenu/releases/latest) ·
[Official website](https://superoutman.sol.build/rightmenu/)

macOS 15 or later · Apple silicon · 7 languages

![RightMenu Finder context menu](Assets/README/RightMenu.png)

## Built-in essentials

RightMenu extends Finder through the native Finder Sync framework and keeps its
core actions local, focused, and independent from optional plugins.

- Create TXT, Markdown, RTF, and valid empty Word, Excel, PowerPoint, Pages,
  Numbers, and Keynote files directly in a Finder folder or on the desktop.
- Copy the full path of one or more selected files and folders.
- View and copy file size. Images also show pixel dimensions and available DPI
  metadata.
- Control launch at login, the menu bar icon, the Dock icon, and enabled file
  formats from native Settings.
- Follow the macOS system language automatically in English, Simplified Chinese,
  Traditional Chinese, Japanese, Korean, French, and German.

## Official plugins

Optional features are delivered as independently versioned and signed plugins.
A plugin can evolve, update, fail, or be removed without rebuilding RightMenu or
interrupting its built-in Finder actions.

| Plugin | What it adds | Status | Links |
| --- | --- | --- | --- |
| [Refresh](https://github.com/Superoutman/RightMenu-Refresh) | Adds Refresh to Finder background menus. It shows a brief nostalgic flash without actually refreshing the folder or changing files. | v1.0.4 | [Download](https://github.com/Superoutman/RightMenu-Refresh/releases/latest/download/RightMenu-Refresh.zip) · [Release notes](https://github.com/Superoutman/RightMenu-Refresh/releases/latest) |
| [Desktop Items](https://github.com/Superoutman/RightMenu-DesktopItems) | Adds Hide or Show Desktop Items to the desktop background and Finder's Desktop folder through a guarded, recoverable host action. | v1.0.2 | [Download](https://github.com/Superoutman/RightMenu-DesktopItems/releases/latest/download/RightMenu-DesktopItems.zip) · [Release notes](https://github.com/Superoutman/RightMenu-DesktopItems/releases/latest) |
| AI Rename | Provides reviewable AI-assisted file renaming using opaque selection access. | In development | Not available |

The Download links always resolve to the latest public release of each plugin.

## Install RightMenu

1. Download the latest DMG from
   [GitHub Releases](https://github.com/Superoutman/RightMenu/releases/latest).
2. Open the DMG and drag `RightMenu.app` to **Applications**.
3. Open RightMenu once.
4. If macOS asks for approval, enable RightMenu under **System Settings >
   General > Login Items & Extensions > Finder Extensions**.
5. Relaunch Finder if the context menu does not appear immediately.

Public releases are signed with the RightMenu Developer ID Application identity,
notarized by Apple, and distributed only after the app and DMG notarization
tickets are stapled and Gatekeeper validation passes. Do not bypass Gatekeeper
if validation fails; download the DMG again from the official Release page.

## Install and manage plugins

Open **RightMenu Settings > Plugins** to import a signed `.rightmenuplugin`
package. The same row links directly to the official plugin downloads in this
repository. You can also double-click a package in Finder to open the same
host-owned review flow.

RightMenu verifies the package before installation, shows its authenticated
publisher source, and opens newly imported plugins directly into access review.
Each supported access group can be granted or revoked independently. Disabling
or removing a plugin removes its actions from Finder without affecting built-in
actions or other plugins.

Production plugins can declare a signed HTTPS update feed. RightMenu may show an
available update, but the downloaded replacement must still pass package
integrity, signing-identity continuity, compatibility, and access review.

## Trust and security

RightMenu separates four different trust decisions instead of treating them as
one broad authorization:

1. **App authenticity** — macOS verifies RightMenu's Developer ID signature,
   Apple notarization, and stapled ticket.
2. **Plugin publisher identity** — every production plugin is signed with an
   Ed25519 publisher key. Official publishers are recognized by RightMenu;
   unknown valid publishers require an explicit full-fingerprint review before
   installation.
3. **Capability access** — a trusted signature does not grant runtime authority.
   A plugin can use only capabilities declared in its package, supported by the
   host, and granted by the user. Every invocation is checked again.
4. **Commercial entitlement** — optional paid features use separately authorized
   license-signing keys. Plugin code never receives license material, receipts,
   transactions, or payment credentials.

Additional protections:

- The Finder extension is sandboxed and uses a fail-closed App Group transport.
- Plugins receive opaque, short-lived selection tokens instead of file paths,
  Finder objects, AppKit objects, credentials, or ambient filesystem access.
- Native confirmation remains mandatory for protected file mutations and
  off-device disclosure.
- Built-in file creation and metadata inspection stay on the Mac.
- RightMenu contains no analytics, advertising, account system, or device
  identifier.
- Accessibility and Finder automation permissions are not required.
- Normal Finder actions work locally. Network access is limited to the RightMenu
  update feed and bounded HTTPS feeds declared by installed production plugins.

## Compatibility and current limits

- **System:** macOS 15.0 or later.
- **Processor:** Apple silicon (`arm64`) only.
- **Finder scope:** regular folders on the startup disk and the desktop.
- External drives and USB drives are not currently supported. Menus may not
  appear in some locations managed by iCloud Drive, OneDrive, Dropbox, and
  similar services.

## Develop a plugin

The installed App bundles `rightmenu-pluginctl`, which can create, diagnose,
sign, inspect, and pack a plugin without cloning the private host source. Plugin
business code runs in an isolated process and interacts with RightMenu only
through the public, versioned Plugin API.

Read the [RightMenu plugin development guide](https://superoutman.sol.build/rightmenu/plugins/)
for the current package format, API contract, capability model, signing flow,
validation commands, and release guidance.

## Updates and distribution

RightMenu checks the public Sparkle feed for application updates. Every published
version has a matching `v<version>` GitHub Release with a manual-install DMG and
release notes. GitHub Release is the publication source; the optional Cloudflare
R2 endpoint mirrors the background Sparkle ZIP.

This public repository contains release-facing material:

- `appcast.xml` — the Sparkle update feed.
- `RightMenu-<version>.zip` — the background Sparkle update archive; it is not
  offered as the manual-install asset on GitHub Releases.
- `RightMenu-<version>.dmg` — the signed, notarized manual installer shown on
  GitHub Releases.
- `RightMenu-<version>.md` — release notes for that version.
- English and Simplified Chinese product documentation.

The application source is maintained privately. Release artifacts and matching
documentation are published here only through an authorized version tag.

Developer ID builds bind both the host app and Finder extension to their
embedded provisioning profiles, so their private App Group transport does not
request access to data belonging to other apps.
