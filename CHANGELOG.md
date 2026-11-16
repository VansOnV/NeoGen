# Changelog

All notable changes to this project are documented here.
The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

## [2.0] - Unreleased

### Added
- Windows GUI (PySide6 + QFluentWidgets) with pages for RPF Tools, RSC Files Converter, PC To PS4 DLC Patcher, Add-On Ped Builder, Add-On PC Vehicle Merger, Extra Features and Settings.
- Import and drag-and-drop on every tool.
- RPF extraction offers a popup to extract nested `.rpf` files found inside the extracted archive.
- Optional texture config when converting `.ytd` files, and when building `.ytd` / `.otd` from DDS folders.
- Per-ped gender selection in the Add-On Ped Builder.
- Dark, light or automatic theme.
- Windows installer with update detection, and an uninstaller reachable from Settings.
- NeoGen logo as the app and installer icon.
- Discord and GitHub buttons on the home page.

### Changed
- Version bumped from T1.5.1 to 2.0.
- RSC conversion and the DLC patcher write their output next to the source (DLC add-ons go to a sibling `_ps4` folder); original files are never overwritten.
- Add-On Ped Builder and Vehicle Merging go back to plain AES-encrypted RPF output built with ragebuilder (the open-RPF change was reverted).

### Removed
- ArchiveFix.

### Fixed
- vcWXML was not detected inside GUI jobs, which broke embedded-texture handling.
- GUI jobs were slower than the terminal version because of per-line log writes.
- Resizing the window could make it disappear.
