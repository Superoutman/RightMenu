
### Changed

- Added a required preflight check before release archives are created. It
  verifies file-creation behavior, builds the complete app bundle, and checks
  the working tree for whitespace errors.

### Fixed

- Regenerated the macOS application icon with transparent corners and safer
  visual padding, preventing the white square background and oversized icon
  appearance in Finder, Dock, and Launchpad on macOS 15.

