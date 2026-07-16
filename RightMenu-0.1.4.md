
### Added

- Added an optional standalone Refresh command to Finder background context menus.
- Clicking Refresh produces a brief nostalgic screen flash without changing files.
- Added a Settings toggle for showing or hiding the Refresh command.

### Fixed

- Fixed a crash caused by the initial animated flash-window cleanup.
- Removed separator items that Finder rendered as oversized blank gaps around Refresh.

### Notes

- Finder controls the placement of extension-provided commands, so RightMenu cannot guarantee that Refresh appears directly below the system New Folder command.

