
### Fixed

- Re-registering the bundled Finder extension after an app update no longer
  relaunches Finder, preventing the desktop and its icons from briefly
  disappearing when RightMenu Settings opens after a cold start.

### Changed

- Added an optional Cloudflare R2 download mirror after the existing tagged
  GitHub publication. Immutable version objects are read back and verified by
  size and SHA-256 before the stable `latest` object is updated; GitHub Release
  remains the publication source and fallback, and the Sparkle feed is unchanged.
  A guarded manual workflow can backfill the current public release without
  rebuilding, resigning, retagging, or modifying the GitHub publication. A
  minimal read-only Cloudflare Worker exposes strict versioned and latest paths
  from the private R2 bucket with ranged-download support and no bucket listing;
  its stable public endpoint is `rightmenu.asticosmo.workers.dev/downloads/`.

