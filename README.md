<div align="center">
  <img src="docs/banner.png" alt="HackTools 汉化版" width="100%" />
</div>

<h1 align="center">HackTools 汉化版</h1>

<p align="center"><em>HackTools 0.5.0 简体中文汉化版 —— 面向 Web 渗透测试人员的全能红队浏览器扩展</em></p>

<p align="center">
  <img alt="version" src="https://img.shields.io/badge/version-0.5.0--zh.1-blue?style=flat-square" />
  <img alt="manifest" src="https://img.shields.io/badge/Chrome-Manifest%20V3-4285F4?style=flat-square&logo=googlechrome&logoColor=white" />
  <img alt="edge" src="https://img.shields.io/badge/Edge-Chromium-0078D7?style=flat-square&logo=microsoftedge&logoColor=white" />
  <img alt="language" src="https://img.shields.io/badge/language-Chinese%20Simplified-critical?style=flat-square" />
</p>

<p align="center">
  <b>简体中文</b> · <a href="README.en.md">English</a>
</p>

> [!WARNING]
> 本项目仅供**合法的授权渗透测试、安全评估与学习研究**使用。请勿用于任何未经授权的攻击行为，由此产生的一切后果由使用者自行承担。
>
> 本项目为社区**非官方汉化版**，与 HackTools 原作者无关。

---

## 目录

- [简介](#简介)
- [功能](#功能)
- [截图](#截图)
- [安装](#安装)
- [汉化说明](#汉化说明)
- [项目结构](#项目结构)
- [常见问题](#常见问题)
- [更新日志](#更新日志)
- [致谢](#致谢)
- [版权与免责声明](#版权与免责声明)

## 简介

[HackTools](https://github.com/LasCC/HackTools) 是一款面向 **Web 渗透测试与红队工作**的浏览器扩展，内置速查表与各类常用工具：XSS Payload、SQL 注入、LFI、反弹 Shell、MSF Venom 命令生成、哈希计算、编码转换、文件传输技巧等。

有了它，你不再需要到不同网站或本地笔记里翻找 Payload —— 大多数工具只需一次点击即可复制使用。扩展既可以在工具栏弹窗中打开，也可以在浏览器开发者工具（<kbd>F12</kbd>）中以整页形式使用。

本仓库基于官方 **HackTools 0.5.0** 的打包产物进行界面汉化，**功能与原版保持一致**，仅将界面文字、说明文档与组件内置文案翻译为简体中文。

## 功能

| 模块 | 说明 |
| --- | --- |
| 反弹 Shell | Bash / Netcat / Socat / PowerShell 等各类反弹 Shell，一键复制，支持 Base64、URL、双重 URL 编码 |
| PHP 反弹 Shell | Pentestmonkey 脚本在线生成、基础 RCE、p0wny WebShell、混淆 WebShell |
| TTY Shell | 获取 TTY 与稳定交互式 Shell 的完整步骤 |
| Linux 命令 | SUID 提权、系统信息收集、服务与定时任务排查、端口转发等速查表 |
| PowerShell 命令 | 系统枚举、WLAN、Active Directory 枚举、ACL 与本地侦察脚本 |
| 文件传输 | Windows 下的 PowerShell、SMB、FTP 下载与上传方法，支持参数实时生成命令 |
| LFI | 目录遍历、`php://file` / `php://filter` 伪协议、Linux/Windows 敏感文件清单 |
| XSS | 数据窃取、HTML/应用、Markdown、SVG 场景 Payload 与黑名单绕过技巧 |
| SQL 注入 | 列数判断、库/表/列枚举、报错注入、时间盲注、认证绕过、ORDER BY / UNION Payload |
| 数据编码 | Base64 / URI / 十六进制 编码与解码，以及引号转义 |
| 哈希计算 | MD5、SHA1、SHA256、SHA512、SM3 |
| MSF Venom | 可视化生成 `msfvenom` 命令与监听 Handler |
| RSS / CVE | Exploit-DB、CXSecurity、Cisco 安全公告订阅与 CVE 查询 |
| 关于我们 | 项目介绍、贡献指南与致谢 |
| 离线笔记 | 点击左上角帽子图标，打开本地 Markdown 记事本（数据保存在 localStorage） |

## 截图

| 反弹 Shell | 数据编码 |
| :---: | :---: |
| ![反弹 Shell](docs/screenshots/reverse-shell.png) | ![数据编码](docs/screenshots/encoding.png) |

| MSF Venom 生成器 | XSS Payload |
| :---: | :---: |
| ![MSF Venom](docs/screenshots/msf.png) | ![XSS](docs/screenshots/xss.png) |

<details>
<summary>查看更多截图</summary>

| 关于我们 | 文件传输 |
| :---: | :---: |
| ![关于我们](docs/screenshots/about.png) | ![文件传输](docs/screenshots/transfer.png) |

| Linux 命令 | LFI |
| :---: | :---: |
| ![Linux 命令](docs/screenshots/linux.png) | ![LFI](docs/screenshots/lfi.png) |

| SQL 注入 | 哈希计算 |
| :---: | :---: |
| ![SQL 注入](docs/screenshots/sqli.png) | ![哈希](docs/screenshots/hash.png) |

| PHP 反弹 Shell | TTY Shell |
| :---: | :---: |
| ![PHP 反弹 Shell](docs/screenshots/php.png) | ![TTY](docs/screenshots/tty.png) |

| RSS 订阅 |
| :---: |
| ![RSS](docs/screenshots/feed.png) |

</details>

> 截图使用无头浏览器实际渲染，除“Paypal 捐赠按钮”等外链图片外均为真实界面。

## 安装

### 环境要求

- Chrome 88+、Edge 88+ 或其他 Chromium 内核浏览器（Manifest V3）
- 无需 Node.js，仓库中已包含打包好的扩展文件

### 方式一：下载即用（推荐）

1. 点击仓库右上角 **Code → Download ZIP**，或在 **Releases** 中下载最新压缩包。
2. 解压到任意目录（路径中尽量不要包含特殊字符）。
3. 打开 `chrome://extensions/`（Edge 为 `edge://extensions/`）。
4. 打开右上角的 **开发者模式**。
5. 点击 **加载已解压的扩展程序**，选择包含 `manifest.json` 的目录。
6. 在工具栏固定 HackTools 图标；按 <kbd>F12</kbd> 打开开发者工具，可在 **HackTools** 面板中全屏使用。

### 方式二：克隆仓库

```bash
git clone <本仓库地址>
```

然后在第 5 步中选择克隆下来的仓库根目录即可（`manifest.json` 位于根目录）。

### 使用提示

- 左侧导航栏默认折叠，只显示图标；**鼠标悬停**可看到中文名称。
- 弹窗模式下建议点击底部「全屏模式」，或在 DevTools 面板中使用，以获得完整宽度。
- 主题可在页脚切换「浅色 / 深色」，选择会被记住。

## 汉化说明

### 已汉化内容

- 侧边栏 15 个模块名称、页面标题、说明段落、按钮、输入框占位符、提示消息；
- About（关于我们）、RSS 订阅、CVE 查询、笔记等页面的界面文字；
- 应用主包共 **282 条词条 / 369 处字符串**；
- 组件内置文案共 **56 处**：antd 分页、表格筛选菜单、空数据提示、Markdown 编辑器 24 个工具栏提示；
- `manifest.json` 的名称、描述、默认标题，`index.html` 的 `lang="zh-CN"` 与标题，DevTools 面板名称。

### 刻意保留英文的内容

以下内容如果翻译，反而会影响复制粘贴或搜索结果，因此保持原样：

- 命令、Payload、SQL 语句、文件路径；
- 产品名与技术术语：`Payload`、`Shell`、`LHOST`、`LPORT`、`XSS`、`LFI`、`PowerShell`、`msfvenom` 等；
- RSS / CVE 页面中来自外部数据源的新闻标题、风险等级等（数据本身即为英文）。

### 技术细节

汉化直接作用于 Webpack 打包产物（`app.bundle.js` / `918.bundle.js`）中的界面字符串，**未改动任何业务逻辑**：

- 只替换字符串字面量，代码结构与标识符完全不变；
- 对同时用作状态键/比较值的字符串做了上下文限定（例如 `label:"格式"` 与 `$("Format")` 分离处理），避免破坏表单与筛选逻辑；
- 两个 bundle 均通过 Acorn 全量语法解析，并用无头浏览器逐页渲染验证。

### 相对原版的改动

- 修复原版 `manifest.json` 中 `devtools_page` 指向错误路径的问题（`devtools.html` 实际位于 `src/devtools/` 下），修复后 <kbd>F12</kbd> 的 HackTools 面板才能正常加载；
- 扩展名称显示为「HackTools 汉化版」，便于与原版区分。

## 项目结构

```text
.
├── manifest.json              # 扩展清单（MV3，中文名称与描述）
├── index.html                 # 主界面入口（lang="zh-CN"）
├── app.bundle.js              # 应用主包（界面文案已汉化）
├── 918.bundle.js              # 依赖包（antd 等，语言包已汉化）
├── 918.bundle.js.LICENSE.txt  # 第三方依赖许可信息
├── iconfont.js                # 图标字体脚本
├── src/
│   ├── assets/img/icons/      # 扩展图标
│   └── devtools/              # DevTools 面板入口
├── docs/
│   ├── banner.png             # README 横幅
│   └── screenshots/           # 各页面截图
├── README.md
├── README.en.md
├── 汉化说明.txt               # 安装与汉化范围说明（纯文本版）
└── .gitignore
```

## 常见问题

<details>
<summary><b>侧边栏为什么只有图标，看不到中文名称？</b></summary>

这是原版的设计：侧边栏默认折叠为 80px 宽的图标栏。将鼠标悬停在图标上会显示对应的中文名称；如需完整名称，可在页面中查看标题。
</details>

<details>
<summary><b>为什么还有一部分内容是英文？</b></summary>

命令、Payload、SQL 语句与路径需要原样复制到终端执行，翻译会破坏可用性；产品名与技术术语（如 `Payload`、`LHOST`）也按惯例保留英文。RSS/CVE 页面的标题来自外部数据源，扩展本身无法翻译。
</details>

<details>
<summary><b>RSS / CVE 页面提示“获取数据失败”？</b></summary>

这两个页面依赖第三方公开接口（rss2json、cve.circl.lu 等）。请检查网络连通性，或稍后重试；接口本身不可用时扩展无法获取数据。
</details>

<details>
<summary><b>扩展会收集我的数据吗？</b></summary>

不会。所有输入内容、哈希/编码结果、MSF 配置与笔记均只保存在浏览器本地（localStorage）。仅 RSS 与 CVE 页面会向上述第三方公开接口发起请求。
</details>

<details>
<summary><b>支持 Firefox 吗？</b></summary>

本汉化版基于原版的 Chrome 打包产物（Manifest V3 + `chrome.*` API），未在 Firefox 上测试。Firefox 用户建议使用官方原版扩展。
</details>

<details>
<summary><b>如何自行调整翻译？</b></summary>

直接用文本编辑器打开 `app.bundle.js`，搜索需要修改的中文文案并替换即可；`918.bundle.js` 中集中存放了 antd 语言包与编辑器提示。修改后重新加载扩展（`chrome://extensions/` 页面点击刷新按钮）即可生效。
</details>

## 更新日志

### v0.5.0-zh.1 · 2026-10

- 首个简体中文汉化版本，基于 HackTools 0.5.0；
- 汉化 282 条词条 / 369 处界面字符串，以及 56 处组件内置文案；
- 汉化 `manifest.json`、`index.html`、DevTools 面板名称；
- 修复原版 `devtools_page` 路径错误；
- 通过 Acorn 语法解析与 13 个页面无头浏览器渲染验证。

## 致谢

- 原项目：[LasCC/HackTools](https://github.com/LasCC/HackTools)，作者 **Ludovic COULON** 与 **Riadh BOUCHAHOUA**；
- 原项目引用的资源与工具：PentestMonkey、GTFOBins、PayloadsAllTheThings、MITRE ATT&CK、Iconfont、Ant Design 等；
- 感谢所有为原项目提交 Issue 与 PR 的社区贡献者。

## 版权与免责声明

- HackTools 的著作权归原作者 **Ludovic COULON** 与 **Riadh BOUCHAHOUA** 所有；原项目仓库未附带明确的开源许可证文件，本仓库仅以**学习与交流**为目的分发汉化产物，未对原程序进行功能性修改。
- 本项目与原作者无任何关联，不代表原作者立场；如原作者认为本项目不妥，请联系删除。
- 本工具仅可用于**已获得明确授权**的渗透测试、安全评估、CTF 比赛或本地学习环境。
- 严禁将本工具用于任何未经授权的入侵、扫描、破坏或数据窃取行为；使用者应自行遵守所在国家或地区的法律法规。
- 使用本工具所产生的一切后果由使用者自行承担，项目维护者不承担任何责任。
