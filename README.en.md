> Language / 语言：**English** | [简体中文](./README.md)

# DeepSeek Harness Installer (Offline Edition)

Note: the official DeepSeek Harness client is now available ([https://www.deepseek.com/harness/](https://www.deepseek.com/harness/)). This repository will therefore receive reduced updates and maintenance — if you need it, please move to the official client. Thank you for your support.

One-click installer for DeepSeek Harness with Node.js and all plugins, dependencies and skills bundled in — **fully offline**. No Node.js installation, no network required. Intended for users on **restricted networks who cannot install DeepSeek Harness through a terminal**.

> Version: **0.2.0-rc.2** ｜ Bundled Node.js **v24.20.0** ｜ 64-bit Windows 10 / 11 (x64 / ARM64) and **macOS (Apple Silicon)**

## Highlights

- **DSH and all plugins updated to the latest versions**: DSH core **0.2.0-rc.2**, with all 7 plugins refreshed (dshmarket 1.66.6, dsh-better-sidebar 0.24.1, dsh-cost-meter 1.7.45, dsh-univer-office 0.3.5, dsh-find-plugin 0.4.0, @liustack/modsearch 5.10.5, dsh-update-checker 1.6.4).
- **The chat UI now supports the DeepSeek V4.1 model** (`deepseek-flash` / DeepSeek-V41-Flash): enabled by default, with text + image input and a 1M-token context window.
- **User data now lives outside the install directory**: sessions, API key and UI settings are stored in `%LOCALAPPDATA%\DeepSeekHarness`, so **changing the install location or reinstalling loses nothing**.
- **Fixed: browser auto-translate broke typing in the chat box (Windows)** — the UI now declares itself non-translatable, so Chrome / Edge no longer translate the page or interfere with typing.

## Download

| File | Size | Platform | Notes |
| --- | --- | --- | --- |
| [DeepSeekHarness-Setup-0.2.0-rc.2.exe](https://github.com/Echan1208/DeepSeek-Harness-Setup/releases/latest/download/DeepSeekHarness-Setup-0.2.0-rc.2.exe) | ~228 MB | Windows | Latest installer |
| [DeepSeek-Harness-Setup-0.2.0-rc.2-macOS.pkg](https://github.com/Echan1208/DeepSeek-Harness-Setup/releases/latest/download/DeepSeek-Harness-Setup-0.2.0-rc.2-macOS.pkg) | ~342 MB | macOS (Apple Silicon) | Latest installer |

> See [Releases](https://github.com/Echan1208/DeepSeek-Harness-Setup/releases) for older versions.

## Installation

### System Requirements

**Windows**
- OS: 64-bit Windows 10 / Windows 11 (x64 / ARM64)
- Browser: Microsoft Edge or Google Chrome (to open the GUI; Win10/11 ship with Edge)
- No Node.js needed, no network needed (runtime and all dependencies are bundled)
- Disk space: ~1.8 GB (install dir ~1.1 GB + user data ~0.7 GB)

**macOS (Apple Silicon)**
- OS: **macOS 14 or later, Apple Silicon (M-series) only** — Intel Macs are not supported
- No Node.js needed, no network needed (runtime and all dependencies are bundled)
- Disk space: ~1.2 GB (install dir `/usr/local/lib/deepseek-harness` ~1.1 GB + user data ~0.1 GB)
- Administrator rights are required to install (writes to `/usr/local` and `/Applications`)

### Install Steps (Windows)
1. Download and double-click `DeepSeekHarness-Setup-0.2.0-rc.2.exe`
2. Choose an install location (default `%LOCALAPPDATA%\Programs\DeepSeekHarness`, **no administrator rights required**)
3. Click "Install" and wait for it to finish
4. A "DeepSeek Harness" shortcut is created on the desktop and in the Start menu

### Install Steps (macOS)
1. Download `DeepSeek-Harness-Setup-0.2.0-rc.2-macOS.pkg`
2. Double-click it, or run:
   ```bash
   sudo installer -pkg DeepSeek-Harness-Setup-0.2.0-rc.2-macOS.pkg -target /
   ```
3. Open **DeepSeek Harness** from Launchpad or Applications and keep its icon in the Dock
4. The GUI is rendered by the app's own window — **no separate Chrome install or launch is needed**. Closing the window stops the service; clicking the Dock icon starts it again

### First Use
1. Double-click the "DeepSeek Harness" desktop shortcut
2. The first launch takes 1–2 minutes to initialize (it copies the plugin dependencies into your user data directory; later launches are fast)
3. Enter your own DeepSeek API Key in the UI — the installer contains **no keys**; each user uses their own
4. You're ready to go

> macOS user data lives in `~/.dsh` (sessions, API key, settings) — the equivalent of `%LOCALAPPDATA%\DeepSeekHarness` on Windows.

### Uninstall
- Option 1: Settings → Apps → DeepSeek Harness → Uninstall
- Option 2: Run `uninstall.exe` in the install directory
- Uninstall asks whether to delete your user data too; choose "No" to **keep your API key, settings and sessions** (stored in `%LOCALAPPDATA%\DeepSeekHarness`) so a reinstall continues where you left off.

### Uninstall (macOS)

**Option 1: Finder (simple)**
1. Open Finder → Applications and drag **DeepSeek Harness** to the Trash
2. The app is removed; **the service, bundled runtime and plugins remain in `/usr/local/lib/deepseek-harness`**, and your data stays in `~/.dsh`
3. To remove those too, use option 2

**Option 2: Terminal (thorough)**
```bash
# remove the app
rm -rf "/Applications/DeepSeek Harness.app"

# remove the service, bundled runtime and all plugins
rm -rf /usr/local/lib/deepseek-harness

# remove the CLI entry points
rm -f /usr/local/bin/dsh /usr/local/bin/pnpm

# remove the profile symlink in your home directory (a symlink only)
rm -f ~/.dsh/profiles

# optional: also delete sessions, API key and UI settings
rm -rf ~/.dsh
```

## Included Plugins

### Core & UI
| Plugin | Version | Purpose |
| --- | --- | --- |
| @deepseek-ai/dsh-base | 0.2.0-rc.2 | Core runtime: agent, tools, sessions, subagents, goals, workflow orchestration |
| @deepseek-ai/dsh-web-app | 0.2.0-rc.2 | The web GUI itself |

### Office (Univer suite)
| Plugin / Skill | Version | Purpose |
| --- | --- | --- |
| dsh-univer-office | 0.3.5 | Embedded Univer office engine: spreadsheet / document / slide / database / board editing, inline preview, floating windows, import & export |
| · univer-sheet | — | Spreadsheet (Excel-like): read/write, formulas, charts; .xlsx / .csv import/export |
| · univer-doc | — | Document (Word-like): editing, layout, pagination; .docx import/export |
| · univer-slide | — | Slides (PPT-like): generate, edit, layout; .pptx import/export |
| · univer-base | — | Database (tabular data, fields, views) |
| · univer-board | — | Whiteboard / canvas (shapes, charts, diagrams) |
| · univer-embed / univer-cross-unit-formula | — | Cross-document embedding, cross-unit formula references |
| ppt-master (skill) | — | AI-driven PPT creation: one-click editable decks, templates / styles / layouts, beautify, animation & narration |

### Search & Information
| Plugin | Version | Purpose |
| --- | --- | --- |
| @liustack/modsearch | 5.10.5 | Web search: web search, X (Twitter) post search, page fetching (no signup / no key) |

### Plugin Management
| Plugin | Version | Purpose |
| --- | --- | --- |
| dshmarket | 1.66.6 | Visual plugin marketplace: browse, search and one-click install community plugins (needs network) |
| dsh-find-plugin | 0.4.0 | Search DSH plugins on GitHub from inside the agent (star-ranked, needs network) |

### Enhancements & Stats
| Plugin | Version | Purpose |
| --- | --- | --- |
| dsh-better-sidebar | 0.24.1 | VSCode-like right sidebar: explorer / editor / terminal / Git / browser, isolated per session |
| dsh-cost-meter | 1.7.45 | Session cost tracking: per-session & daily cost, history, official price sync, 90+ model pricing |

## Notes

1. **Fully offline**: Node.js and all dependencies are bundled; no Node.js install or network needed.
2. **Self-update available**: the built-in update-checker plugin (dsh-update-checker) lets you check for and one-click update DSH and its plugins when online.
3. **No API key included**: each user enters their own key on first use.
4. Network features (web search, installing new plugins, price sync) only work with network; core chat and office features work offline.
5. **Upgrades keep your data**: re-running a newer installer refreshes the plugins while keeping your UI settings, session history and API key.

## Open-Source Credits

All bundled plugins come from open-source creators on GitHub — credit and links:

| Plugin / Skill | Repository |
| --- | --- |
| DeepSeek Harness (core) | [deepseek-ai/deepseek-harness](https://github.com/deepseek-ai/deepseek-harness) |
| dshmarket | [dsh-market/dsh-market](https://github.com/dsh-market/dsh-market) |
| dsh-find-plugin | [awesome-dsh-plugin/dsh-find-plugin](https://github.com/awesome-dsh-plugin/dsh-find-plugin) |
| dsh-better-sidebar | [omdsh-dev/DSH-better-sidebar](https://github.com/omdsh-dev/DSH-better-sidebar) |
| dsh-univer-office (incl. univer skills) | [dream-num/dsh-univer-office](https://github.com/dream-num/dsh-univer-office) |
| dsh-cost-meter | [Han-1413141/dsh-cost-meter](https://github.com/Han-1413141/dsh-cost-meter) |
| @liustack/modsearch | [liustack/modsearch](https://github.com/liustack/modsearch) |
| ppt-master (skill) | [hugohe3/ppt-master](https://github.com/hugohe3/ppt-master) |
| dsh-update-checker | [Airmetro/dsh-update-checker](https://github.com/Airmetro/dsh-update-checker) |

> This repo only repackages for offline distribution (for intranet / restricted networks). Plugins remain the property of their authors; please respect each repository's license (mostly MIT).
