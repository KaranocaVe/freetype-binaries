# freetype-binaries

![GitHub Actions Status](https://github.com/<your-username>/freetype-binaries/workflows/FreeType%20Submodule%20Auto-Updater/badge.svg)
![GitHub Actions Status](https://github.com/<your-username>/freetype-binaries/workflows/Build%20FreeType%20Multi-Platform/badge.svg)
![GitHub Release](https://img.shields.io/github/v/release/<your-username>/freetype-binaries?include_prereleases)

This repository provides pre-compiled binaries of the FreeType library for multiple platforms.

Using an automated CI/CD workflow, this repository ensures that when the official FreeType repository is updated, new binaries are generated and released promptly for Windows, macOS, and Linux, saving developers from the hassle of configuring and compiling it themselves.

### Features

- **Fully Automated Builds**: Automatically checks the official FreeType repository for version updates on a daily basis.
- **Precise Versioning**: Builds and releases are only triggered when the version number in the `README.md` file changes.
- **Multi-Platform Support**: A single build process generates binaries for Windows (.dll), macOS (.dylib), and Linux (.so).
- **Complete Releases**: Each release includes all platform-specific binaries and the corresponding license documentation.

### How to Use

You can download the latest pre-compiled binaries from the [GitHub Releases](https://github.com/<your-username>/freetype-binaries/releases) page.

Simply download the `Source code (zip)` from the latest Release page, or directly download the specific `.dll`, `.dylib`, or `.so` files you need.

### Project Structure

This repository is powered by two core GitHub Actions workflows:

1.  `FreeType Submodule Auto-Updater` (`update-submodule.yml`):
    - Runs on a daily schedule.
    - Checks for a version change in the official FreeType repository.
    - If an update is detected, it automatically updates the `freetype` submodule reference and pushes a new commit to this repository.
    
2.  `Build FreeType Multi-Platform` (`build-freetype.yml`):
    - Listens for `push` events on this repository.
    - This workflow is automatically triggered when the `Auto-Updater` commits a change.
    - It handles building FreeType in parallel on Windows, macOS, and Linux, and publishes the resulting binaries as a new Release.

### License

This repository and its distributed binaries are subject to the FreeType library's licensing. Every release includes the `FTL.TXT` and `GPLv2.TXT` files for users to choose from.

Please refer to the `LICENSE.TXT` file for more details.

---
**Note**: Be sure to replace `<your-username>` with your GitHub username.