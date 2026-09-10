
### Fixed

- Replaced the hand-written minimal Office packages with validated blank Word,
  Excel, and PowerPoint templates. Newly created Office files now open without
  repair warnings and contain no visible starter content.
- Strengthened core verification so it checks required OOXML parts at the ZIP
  root instead of accepting any file with a ZIP header.

### Highlights from 0.1.43

If you missed the recent major update, RightMenu now includes:

- An independently versioned, signed plugin platform with secure importing,
  publisher verification, access review, updates, and isolated execution.
- Refresh and Desktop Items as separately downloadable official plugins.
- Developer ID signing, Apple notarization, stapling, and Gatekeeper
  verification for public releases.
- New File, Copy File Path, and file information kept built into RightMenu and
  independent from optional plugins.

Users upgrading from an earlier version can open **Settings > Plugins** and
select **Download Plugins** to install Refresh or Desktop Items if they want
those optional Finder actions.

