<div align="center">
  <img src="docs/banner.png" alt="HackTools Chinese Edition" width="100%" />
</div>

<h1 align="center">HackTools — Simplified Chinese Edition</h1>

<p align="center"><em>A community Chinese localization of HackTools 0.5.0 — the all-in-one browser extension for offensive security professionals.</em></p>

<p align="center">
  <img alt="version" src="https://img.shields.io/badge/version-0.5.0--zh.1-blue?style=flat-square" />
  <img alt="manifest" src="https://img.shields.io/badge/Chrome-Manifest%20V3-4285F4?style=flat-square&logo=googlechrome&logoColor=white" />
  <img alt="edge" src="https://img.shields.io/badge/Edge-Chromium-0078D7?style=flat-square&logo=microsoftedge&logoColor=white" />
  <img alt="language" src="https://img.shields.io/badge/language-Chinese%20Simplified-critical?style=flat-square" />
</p>

<p align="center">
  <a href="README.md">简体中文</a> · <b>English</b>
</p>

> [!WARNING]
> This project is intended **only for authorized penetration testing, security assessments, and educational research**. Do not use it for any unauthorized activity. You are solely responsible for your actions.
>
> This is an **unofficial community localization** and is not affiliated with the original authors.

---

## Table of Contents

- [Introduction](#introduction)
- [Features](#features)
- [Screenshots](#screenshots)
- [Installation](#installation)
- [Localization Notes](#localization-notes)
- [Project Structure](#project-structure)
- [FAQ](#faq)
- [Changelog](#changelog)
- [Credits](#credits)
- [Disclaimer](#disclaimer)

## Introduction

[HackTools](https://github.com/LasCC/HackTools) is a browser extension that supports **web application penetration testing** and red teaming. It bundles cheat sheets and everyday tools in one place: XSS payloads, SQL injection, LFI, reverse shells, MSF Venom command generation, hashing, encoding, file transfer techniques, and more.

No more digging through different websites or local notes — most tools are one click away. The extension works as a toolbar popup or as a full tab inside the browser DevTools (<kbd>F12</kbd>).

This repository is a **Simplified Chinese localization** based on the official **HackTools 0.5.0** build. Functionality is identical to the original; only the interface, documentation, and built-in component strings are translated.

## Features

| Module | Description |
| --- | --- |
| Reverse Shell | Bash / Netcat / Socat / PowerShell payloads with one-click copy, Base64 / URL / double-URL encoding |
| PHP Reverse Shell | Pentestmonkey script generator, basic RCE, p0wny WebShell, obfuscated WebShell |
| TTY Shell | Steps to spawn and stabilize an interactive TTY |
| Linux Commands | SUID, enumeration, service/cron checks, port forwarding cheat sheet |
| PowerShell Commands | System enumeration, WLAN, Active Directory enumeration, ACL and local recon scripts |
| File Transfer | PowerShell, SMB, and FTP download/upload methods with live command generation |
| LFI | Directory traversal, `php://file` / `php://filter` wrappers, sensitive file lists |
| XSS | Data grabber, HTML/Markdown/SVG payloads, blacklist bypass techniques |
| SQL Injection | Column counting, database/table/column enumeration, error-based, time-based, auth bypass, ORDER BY / UNION payloads |
| Data Encoding | Base64 / URI / Hex encode & decode, quote escaping |
| Hashing | MD5, SHA1, SHA256, SHA512, SM3 |
| MSF Venom | Visual `msfvenom` command builder and listener handler |
| RSS / CVE | Exploit-DB, CXSecurity, Cisco advisories, and CVE lookup |
| About | Project information, contribution guide, and credits |
| Offline Notes | Click the hat icon to open a local Markdown notepad (stored in localStorage) |

## Screenshots

| Reverse Shell | Data Encoding |
| :---: | :---: |
| ![Reverse Shell](docs/screenshots/reverse-shell.png) | ![Data Encoding](docs/screenshots/encoding.png) |

| MSF Venom Builder | XSS Payloads |
| :---: | :---: |
| ![MSF Venom](docs/screenshots/msf.png) | ![XSS](docs/screenshots/xss.png) |

<details>
<summary>More screenshots</summary>

| About | File Transfer |
| :---: | :---: |
| ![About](docs/screenshots/about.png) | ![File Transfer](docs/screenshots/transfer.png) |

| Linux Commands | LFI |
| :---: | :---: |
| ![Linux](docs/screenshots/linux.png) | ![LFI](docs/screenshots/lfi.png) |

| SQL Injection | Hashing |
| :---: | :---: |
| ![SQLi](docs/screenshots/sqli.png) | ![Hash](docs/screenshots/hash.png) |

| PHP Reverse Shell | TTY Shell |
| :---: | :---: |
| ![PHP Reverse Shell](docs/screenshots/php.png) | ![TTY](docs/screenshots/tty.png) |

| RSS Feed |
| :---: |
| ![RSS](docs/screenshots/feed.png) |

</details>

## Installation

### Requirements

- Chrome 88+, Edge 88+, or any Chromium-based browser (Manifest V3)
- Node.js is **not** required — the build artifacts are included

### Steps

1. Click **Code → Download ZIP** at the top of this repository, or download the latest archive from **Releases**.
2. Extract it to any folder.
3. Open `chrome://extensions/` (or `edge://extensions/`).
4. Enable **Developer mode** in the top-right corner.
5. Click **Load unpacked** and select the folder containing `manifest.json`.
6. Pin the HackTools icon to the toolbar. Press <kbd>F12</kbd> and open the **HackTools** panel for the full-width layout.

### Tips

- The sidebar is collapsed by default and shows icons only — hover an icon to see its Chinese name.
- Use **Fullscreen mode** in the footer (or the DevTools panel) to get more horizontal space.
- The light/dark theme can be switched in the footer and is remembered.

## Localization Notes

### What is translated

- All 15 sidebar module names, page titles, descriptions, buttons, placeholders, and toast messages;
- About, RSS, CVE, and notes pages;
- **282 entries / 369 string literals** in the application bundle;
- **56 built-in component strings**: antd pagination, table filter menus, empty states, and 24 Markdown editor toolbar tooltips;
- `manifest.json` name/description/title, `index.html` (`lang="zh-CN"`), and the DevTools panel name.

### What stays in English

- Commands, payloads, SQL statements, and file paths — they must be copied verbatim;
- Product names and technical terms: `Payload`, `Shell`, `LHOST`, `LPORT`, `XSS`, `LFI`, `PowerShell`, `msfvenom`;
- Titles and severity values fetched from external RSS/CVE feeds.

### Implementation

The localization works directly on the Webpack bundles (`app.bundle.js` / `918.bundle.js`) and **does not modify any business logic**:

- Only string literals are replaced; code structure and identifiers are untouched;
- Strings that double as state keys or comparison values were handled context-sensitively (e.g. `label:"格式"` vs. `$("Format")`) to keep forms and filters working;
- Both bundles were fully parsed with Acorn and rendered page-by-page in a headless browser for verification.

### Changes compared to upstream

- Fixed the upstream `manifest.json` `devtools_page` path (`devtools.html` actually lives under `src/devtools/`), which is required for the <kbd>F12</kbd> HackTools panel to load;
- The extension is named “HackTools 汉化版” to distinguish it from the original.

## Project Structure

```text
.
├── manifest.json              # Extension manifest (MV3, localized)
├── index.html                 # Entry page (lang="zh-CN")
├── app.bundle.js              # Application bundle (localized strings)
├── 918.bundle.js              # Vendor bundle (antd locale, localized)
├── 918.bundle.js.LICENSE.txt  # Third-party license notices
├── iconfont.js                # Icon font script
├── src/
│   ├── assets/img/icons/      # Extension icons
│   └── devtools/              # DevTools panel entry
├── docs/
│   ├── banner.png
│   └── screenshots/
├── README.md                  # Simplified Chinese
├── README.en.md               # English
├── 汉化说明.txt                # Plain-text install & localization notes
└── .gitignore
```

## FAQ

<details>
<summary><b>Why does the sidebar only show icons?</b></summary>

That is the original design: the sidebar is collapsed to an 80px icon rail. Hovering an icon reveals its Chinese name.
</details>

<details>
<summary><b>Why is some text still in English?</b></summary>

Commands, payloads, SQL statements, and paths must stay verbatim to be usable. Product names and terms such as `Payload` and `LHOST` are conventionally kept in English. RSS/CVE titles come from external feeds and cannot be translated by the extension.
</details>

<details>
<summary><b>RSS/CVE pages show “获取数据失败” (failed to fetch data).</b></summary>

Those pages rely on third-party public APIs (rss2json, cve.circl.lu). Check your network connection or try again later; if the API is down, the extension cannot retrieve data.
</details>

<details>
<summary><b>Does the extension collect my data?</b></summary>

No. Inputs, hash/encoding results, MSF configuration, and notes stay in your browser's localStorage. Only the RSS and CVE pages make requests to the third-party APIs mentioned above.
</details>

<details>
<summary><b>Does it work on Firefox?</b></summary>

This localization is based on the Chrome build (Manifest V3 + `chrome.*` APIs) and has not been tested on Firefox. Firefox users should use the official extension.
</details>

## Changelog

### v0.5.0-zh.1 · 2026-10

- First Simplified Chinese release, based on HackTools 0.5.0;
- Localized 282 entries / 369 UI strings and 56 built-in component strings;
- Localized `manifest.json`, `index.html`, and the DevTools panel title;
- Fixed the upstream `devtools_page` path;
- Verified with Acorn parsing and headless-browser rendering of 13 pages.

## Credits

- Original project: [LasCC/HackTools](https://github.com/LasCC/HackTools) by **Ludovic COULON** and **Riadh BOUCHAHOUA**;
- Resources referenced by the original project: PentestMonkey, GTFOBins, PayloadsAllTheThings, MITRE ATT&CK, Iconfont, Ant Design;
- Thanks to all community contributors of the original project.

## Disclaimer

- HackTools is copyrighted by **Ludovic COULON** and **Riadh BOUCHAHOUA**. The upstream repository does not include an explicit open-source license file; this repository distributes a localized build for **learning and exchange** purposes only and does not modify the original functionality.
- This project is not affiliated with the original authors. If the authors object to this repository, it will be removed upon request.
- Use this tool **only** in environments where you have explicit authorization (authorized penetration tests, security assessments, CTF competitions, or local labs).
- Any unauthorized intrusion, scanning, disruption, or data theft is strictly prohibited. You must comply with the laws and regulations of your jurisdiction.
- The maintainers assume no liability for any consequences arising from the use of this tool.
