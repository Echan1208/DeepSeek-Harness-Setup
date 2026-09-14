> Language / 语言：**English** | [简体中文](./README.md)

# DeepSeek Harness Installer (Offline Edition)

One-click installer for DeepSeek Harness with Node.js and all plugins, dependencies and skills bundled in — **fully offline**. No Node.js installation, no network required. Intended for users on **restricted networks who cannot install DeepSeek Harness through a terminal**.

> Version: **0.1.5-rc.2** ｜ Bundled Node.js **v24.20.0** ｜ 64-bit Windows 10 / 11 (x86 / arm)

## Highlights

- **The chat UI now supports the DeepSeek V4.1 model** (`deepseek-flash` / DeepSeek-V41-Flash): enabled by default, with text + image input and a 1M-token context window.
- **User data now lives outside the install directory**: sessions, API key and UI settings are stored in `%LOCALAPPDATA%\DeepSeekHarness`, so **changing the install location or reinstalling loses nothing**.

## Download

| File | Size | Notes |
| --- | --- | --- |
| [DeepSeekHarness-Setup-0.1.5-rc.2.exe](https://github.com/Echan1208/DeepSeek-Harness-Setup/releases/latest/download/DeepSeekHarness-Setup-0.1.5-rc.2.exe) | ~170 MB | Latest installer |

> See [Releases](https://github.com/Echan1208/DeepSeek-Harness-Setup/releases) for older versions.

## Installation

### System Requirements
- OS: 64-bit Windows 10 / Windows 11 (x86 / arm)
- Browser: Microsoft Edge or Google Chrome (to open the GUI; Win10/11 ship with Edge)
- No Node.js needed, no network needed (runtime and all dependencies are bundled)
- Disk space: ~1.7 GB (install dir ~1 GB + user data ~0.7 GB)

### Install Steps
1. Download and double-click `DeepSeekHarness-Setup-0.1.5-rc.2.exe`
2. Choose an install location (default `%LOCALAPPDATA%\Programs\DeepSeekHarness`, **no administrator rights required**)
3. Click "Install" and wait for it to finish
4. A "DeepSeek Harness" shortcut is created on the desktop and in the Start menu

### First Use
1. Double-click the "DeepSeek Harness" desktop shortcut
2. The first launch takes 1–2 minutes to initialize (it copies the plugin dependencies into your user data directory; later launches are fast)
3. Enter your own DeepSeek API Key in the UI — the installer contains **no keys**; each user uses their own
4. You're ready to go

### Uninstall
- Option 1: Settings → Apps → DeepSeek Harness → Uninstall
- Option 2: Run `uninstall.exe` in the install directory
- Uninstall asks whether to delete your user data too; choose "No" to **keep your API key, settings and sessions** (stored in `%LOCALAPPDATA%\DeepSeekHarness`) so a reinstall continues where you left off.

## Included Plugins

### Core & UI
| Plugin | Version | Purpose |
| --- | --- | --- |
| @deepseek-ai/dsh-base | 0.1.5-rc.2 | Core runtime: agent, tools, sessions, subagents, goals, workflow orchestration |
| @deepseek-ai/dsh-web-app | 0.1.5-rc.2 | The web GUI itself |

### Office (Univer suite)
| Plugin / Skill | Version | Purpose |
| --- | --- | --- |
| dsh-univer-office | 0.2.14 | Embedded Univer office engine: spreadsheet / document / slide / database / board editing, inline preview, floating windows, import & export |
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
| @liustack/modsearch | 5.10.2 | Web search: web search, X (Twitter) post search, page fetching (no signup / no key) |

### Plugin Management
| Plugin | Version | Purpose |
| --- | --- | --- |
| dshmarket | 1.46.1 | Visual plugin marketplace: browse, search and one-click install community plugins (needs network) |
| dsh-find-plugin | 0.3.7 | Search DSH plugins on GitHub from inside the agent (star-ranked, needs network) |

### Enhancements & Stats
| Plugin | Version | Purpose |
| --- | --- | --- |
| dsh-better-sidebar | 0.19.1 | VSCode-like right sidebar: explorer / editor / terminal / Git / browser, isolated per session |
| dsh-cost-meter | 1.7.22 | Session cost tracking: per-session & daily cost, history, official price sync, 90+ model pricing |

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
