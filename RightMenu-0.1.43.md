
### Highlights

- RightMenu releases are now signed with a Developer ID Application identity,
  notarized by Apple, stapled, and accepted by Gatekeeper before publication.
- Added a production-ready, independently versioned plugin platform with signed
  package installation, Finder actions, isolated execution, access review,
  updates, and optional paid entitlements.
- Refresh and Desktop Items now ship as independent official plugins. Their
  repositories, release notes, and stable downloads are listed in the RightMenu
  README.

### Added

- Registered `.rightmenuplugin` as a branded macOS package document. Double-clicking
  a package or importing it from Settings opens the same host-owned verification
  and installation review.
- Added Ed25519 publisher identity verification. Official publishers are recognized
  by RightMenu, while other valid publishers require an explicit full-fingerprint
  Trust and Install review. Updates cannot silently replace an installed plugin's
  signing identity.
- Added host-owned capability controls with explicit, revocable grants and
  per-action or per-UI minimum access. Partially authorized plugins keep their
  permitted actions available while other actions remain hidden from Finder.
- Added publisher-signed HTTPS update discovery. New packages must still pass
  identity continuity, integrity, compatibility, and access review.
- Added business-neutral paid entitlements with separately authorized offline
  license signatures. Plugin code never receives payment credentials, receipts,
  transactions, or license material.
- Bundled `rightmenu-pluginctl` with commands to create, diagnose, sign, inspect,
  pack, and prepare independently released plugins and licenses. The public
  [development guide](https://superoutman.sol.build/rightmenu/plugins/)
  documents the supported workflow.
- Added versioned Plugin API capabilities for opaque selection access, local
  Vision OCR, structured AI, host-confirmed rename transactions, bounded plugin
  windows, Finder container actions, visual feedback, and recoverable desktop
  visibility changes.

### Changed

- Refresh and Hide or Show Desktop Items are no longer built into the host.
  Install the official Refresh and Desktop Items plugins to restore those
  optional actions. New File, Copy File Path, and file information remain
  built-in and independent from the plugin system.
- Reworked Plugins Settings around import, Developer Mode, installed plugins,
  authenticated publisher sources, enablement, access review, update status,
  entitlement status, and removal. Plugin-specific descriptions and icons now
  remain owned by each package.
- Ordinary plugin capabilities now use host-owned localized titles and safety
  explanations instead of being presented as macOS permissions. The Permissions
  section is reserved for real system authorizations recognized by the host.
- Consolidated third-party notices into the About page and simplified the plugin
  list and detail templates while preserving the established native Settings
  appearance.
- macOS 26 now uses the native Icon Composer application icon stack. macOS 15
  continues to use the compatible legacy icon.

### Fixed

- Fixed declarative Finder plugin actions that could appear in the menu but fail
  to invoke. Commands now use stable opaque tags and are revalidated against the
  current Finder projection before execution.
- Hardened plugin window, bridge, timeout, cancellation, and terminal-result
  teardown so one plugin session cannot crash or close RightMenu Settings.
- Corrected lossless JavaScript boolean and number handling across the bounded UI
  bridge and improved stable error reporting without exposing paths, credentials,
  selected content, provider output, or raw logs.

### Security

- Plugin actions travel through a fail-closed App Group transport. The App
  atomically consumes short-lived requests, revalidates the package, action,
  signing identity, grants, selection identity, and scope, then gives the plugin
  opaque tokens instead of file paths or Finder objects.
- Plugin business code runs in an isolated bundled process without ambient
  filesystem, network, Finder, AppKit, shell, credential, or App Group access.
  Protected mutations and off-device disclosures retain native host confirmation.
- Production publication now imports signing and notarization credentials into an
  ephemeral CI keychain, validates the app and Finder provisioning profiles, and
  removes all credentials before updating the public repository or download mirror.

