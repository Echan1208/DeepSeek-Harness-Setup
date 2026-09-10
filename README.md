# DeepSeek Harness 安装包（Windows 离线版）

一键安装 DeepSeek Harness，内置 Node.js 与全部插件、依赖、技能，**完全离线可用**——同事无需安装 Node.js、无需联网拉取任何依赖。

> 版本：**0.1.5-alpha.1** ｜ 内置 Node.js **v24.20.0** ｜ 适用 64 位 Windows 10 / 11

## 下载

| 文件 | 大小 | 说明 |
| --- | --- | --- |
| [DeepSeekHarness-Setup-0.1.5-alpha.1.exe](https://github.com/Echan1208/DeepSeek-Harness-Setup/releases/latest/download/DeepSeekHarness-Setup-0.1.5-alpha.1.exe) | 约 181 MB | 最新版安装包 |

> 历史版本见 [Releases](https://github.com/Echan1208/DeepSeek-Harness-Setup/releases) 页面。

## 安装说明

### 系统要求
- 操作系统：64 位 Windows 10 / Windows 11
- 浏览器：Microsoft Edge 或 Google Chrome（用于打开图形界面，Win10/11 自带 Edge）
- 无需安装 Node.js、无需联网（运行时和全部依赖已内置）
- 磁盘空间：约 1 GB

### 安装步骤
1. 下载并双击 `DeepSeekHarness-Setup-0.1.5-alpha.1.exe`
2. 选择安装位置（默认 `%LOCALAPPDATA%\Programs\DeepSeekHarness`，全程**无需管理员权限**）
3. 点击「安装」，等待进度条完成
4. 安装完成后，桌面和开始菜单会自动生成「DeepSeek Harness」快捷方式

### 首次使用
1. 双击桌面上的「DeepSeek Harness」快捷方式
2. 首次启动需 30–60 秒初始化（自动在本地补齐插件依赖，之后启动会更快）
3. 在界面中填入你自己的 DeepSeek API Key —— 安装包**不含任何密钥**，每位同事需使用自己的 Key
4. 填入后即可开始使用

### 卸载
- 路径一：设置 → 应用 → DeepSeek Harness → 卸载
- 路径二：运行安装目录下的 `uninstall.exe`
- 卸载会**保留你的 API Key、设置和会话记录**（安装目录下的 `home` 文件夹），重装后数据仍在；如需彻底清除，请手动删除整个安装目录

## 包含的插件及用途

### 核心与界面
| 插件 | 版本 | 用途 |
| --- | --- | --- |
| @deepseek-ai/dsh-base | 0.1.5-alpha.1 | DSH 核心运行时：智能体、工具集、会话管理、子智能体、目标管理、工作流编排等基础能力 |
| @deepseek-ai/dsh-web-app | 0.1.5-alpha.1 | 网页图形界面本体 |

### 办公文档（Univer 套件）
| 插件 / 技能 | 版本 | 用途 |
| --- | --- | --- |
| dsh-univer-office | 0.2.14 | 内嵌 Univer 办公引擎：电子表格 / 文档 / 幻灯片 / 数据库 / 白板的编辑、内联预览、浮动窗口与导入导出 |
| · univer-sheet | — | 电子表格（类 Excel）：读写、公式、图表，支持 .xlsx / .csv 导入导出 |
| · univer-doc | — | 文档（类 Word）：编辑、排版、分页，支持 .docx 导入导出 |
| · univer-slide | — | 幻灯片（类 PPT）：生成、编辑、布局，支持 .pptx 导入导出 |
| · univer-base | — | 数据库（表格化数据管理、字段、视图） |
| · univer-board | — | 白板 / 画布（图形、图表、流程图、示意图） |
| · univer-embed / univer-cross-unit-formula | — | 跨文档嵌入、跨单元公式引用 |
| ppt-master（技能） | — | AI 驱动 PPT 制作：一键生成可编辑 PPT、套用模板 / 风格 / 版式、美化、加动画与旁白 |

### 搜索与信息
| 插件 | 版本 | 用途 |
| --- | --- | --- |
| @liustack/modsearch | 5.10.2 | 联网搜索能力：网页搜索、X（推特）帖子搜索、网页内容抓取（免注册、免 Key） |

### 插件管理
| 插件 | 版本 | 用途 |
| --- | --- | --- |
| dshmarket | 1.45.1 | 可视化插件市场：浏览、搜索并一键安装社区插件（需联网） |
| dsh-find-plugin | 0.3.7 | 在智能体内从 GitHub 搜索 DSH 插件（按 star 排序，需联网） |

### 增强与统计
| 插件 | 版本 | 用途 |
| --- | --- | --- |
| dsh-better-sidebar | 0.18.1 | 类 VSCode 的右侧边栏：资源管理器 / 编辑器 / 终端 / Git / 浏览器，按会话隔离 |
| dsh-cost-meter | 1.7.17 | 会话费用统计：单会话与当日费用、历史记录、官方价格同步、多厂商 90+ 模型定价 |

## 说明

1. **完全离线可用**：安装包已内置 Node.js 及全部依赖，同事无需安装 Node.js、无需联网拉取任何依赖。
2. **已禁用自动更新**：安装包中移除了「自动更新检查」插件（dsh-update-checker），避免离线环境下自更新影响稳定；后续如需在线升级，可联系管理员更新安装包。
3. **不含 API Key**：安装包不含任何密钥，每位同事首次使用时自行填写。
4. 联网相关功能（网页搜索、插件市场安装新插件、费用价格同步）在有网络时才生效；离线时核心对话与办公文档功能不受影响。

## 开源来源与致谢

本安装包集成的插件均来自 GitHub 上的开源创作者，特此列出原始仓库并致谢：

| 插件 / 技能 | 开源仓库 |
| --- | --- |
| DeepSeek Harness（核心本体） | [deepseek-ai/deepseek-harness](https://github.com/deepseek-ai/deepseek-harness) |
| dshmarket | [dsh-market/dsh-market](https://github.com/dsh-market/dsh-market) |
| dsh-find-plugin | [awesome-dsh-plugin/dsh-find-plugin](https://github.com/awesome-dsh-plugin/dsh-find-plugin) |
| dsh-better-sidebar | [omdsh-dev/DSH-better-sidebar](https://github.com/omdsh-dev/DSH-better-sidebar) |
| dsh-univer-office（含 univer 系列技能） | [dream-num/dsh-univer-office](https://github.com/dream-num/dsh-univer-office) |
| dsh-cost-meter | [Han-1413141/dsh-cost-meter](https://github.com/Han-1413141/dsh-cost-meter) |
| @liustack/modsearch | [liustack/modsearch](https://github.com/liustack/modsearch) |
| ppt-master（技能） | [hugohe3/ppt-master](https://github.com/hugohe3/ppt-master) |
| dsh-update-checker（本包已禁用） | [Airmetro/dsh-update-checker](https://github.com/Airmetro/dsh-update-checker) |

> 本仓库仅做离线打包与分发，便于内网 / 受限网络环境一键安装；各插件版权归原作者所有，请遵守各仓库的开源协议（多数为 MIT）。
