
### Fixed

- Desktop Items can now hide and restore user-owned read-only files without
  changing their permissions or other file flags. A read-only item no longer
  causes the guarded desktop visibility transaction to roll back.
- Restored the copyable file information line on macOS 27, including image
  dimensions and available DPI metadata, after validating the existing bounded
  metadata lookup and recovery path on the new system version.

