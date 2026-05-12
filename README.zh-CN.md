[English](./README.md) | **简体中文**

# 10 周作战日志

一个单文件、零构建、有态度的**面试备战追踪器**，专为 10 周冲刺设计。最初是为一个备战美国头部科技公司面试（NVIDIA、Apple、Google 等）的机器人 / AI 工程师写的，但这套框架适用于任何 10 周面试冲刺。

> 停止选择，开始行动。—— 这工具的全部意义。

**→ 立刻试用：[alexntfound.github.io/neetcode-battle-log](https://alexntfound.github.io/neetcode-battle-log/)**

不用注册。点开链接、设个开始日期、收藏就完事。你的进度存在你自己的浏览器里——不上传服务器，不会被共享。

## 它做什么

打开应用，立刻看到：

- **今日重点** —— 根据日期自动算出：你在哪个 phase、今天该做什么、该不该开始投简历
- **推荐 LeetCode 题** —— 根据当前 phase 的 pattern 焦点（Phase 1 = 数组/哈希 / 双指针 / 滑动窗口等）从 NeetCode 150 里挑两道未解的题
- **每日 + 每周清单** —— 按 phase 定制，按日期持久化
- **累计计数器** —— LC 题数、投递数（练手 / 目标）、mock 次数
- **NeetCode 150 路线图** —— 全部 150 题，附 LC + NC 解法链接、依赖图（与官方 NeetCode 结构一致）、按难度筛选
- **Phase 时间线** —— 可视化你在 10 周冲刺中的位置
- **关键日期倒计时** —— "距开始投目标公司还有 X 天"
- **Day 1 / Phase 切换日特殊指引** —— 关键日子自动弹出「现在就做这五件事」
- **宠物伙伴** —— 首次访问随机孵化 6 种之一（火龙 / 银狼 / 狡狐 / 老龟 / 智枭 / 墨猫）。它会在视窗里走动，勾任务时跳到对应卡片上，随 XP 增长经历 5 个成长阶段。每日 XP 上限 10。连续 7/14/21 天有进度触发 ×1.5 / ×2 / ×2.5 streak 倍率——奖励坚持，不奖励爆刷。
- **备份 / 迁移** —— 一键导出全部进度为 JSON，或从 JSON 文件恢复。换设备、防止清缓存丢数据时用。
- **双语（中文 / English）** —— 底部一键切换，首次访问根据浏览器语言自动判断
- **首次访问 tutorial** —— 交互式向导，帮你选语言、设置开始日期、过一遍各个功能；可在「设置」里重新触发

## 怎么用

**1. 线上版（最快）：** 打开 [alexntfound.github.io/neetcode-battle-log](https://alexntfound.github.io/neetcode-battle-log/) → 点底部 **⚙ 设置** → 改开始日期 → 收藏。每天打开。

**2. 离线 / 本地：** 下载 `index.html`（单文件，零依赖），用任何现代浏览器打开。功能跟线上版完全一致。

**3. 自己托管一份：**

1. Fork 本仓库（或把 `index.html` 复制到你自己的 repo）
2. Settings → Pages → 选 main 分支部署
3. 访问 `https://<你的用户名>.github.io/<仓库名>/`

每个访问者的数据存在**他们自己浏览器的 localStorage 里**——完全私有，不上传到任何服务器，无需账号。换设备？用「设置」里的 **导出 / 导入 JSON** 按钮。

## 配置

所有内容都在 `index.html` 里。计划是一个 JavaScript 对象，位于 `<script>` 标签的顶部——搜索 `PHASE_CONFIGS` 来自定义 phase 名字、重点、每日任务、验收节点。

每个 phase 14 天，共 5 个 phase，总计 70 天。要改这些数字，编辑 `buildPhases()`。

## 存储后端

工具自动检测运行环境：

| 运行环境 | 使用的存储 |
|---|---|
| Claude.ai artifact | `window.storage`（跨 Claude 会话持久化） |
| 其他任何地方（本地文件、GitHub Pages、自建服务器） | 浏览器 `localStorage`（按浏览器、按 origin 持久化） |

所有 key 在 localStorage 里以 `battlelog:` 为前缀。要清空，点底部 **⟲ reset all data**。

## 技术栈

纯 HTML、CSS、原生 JavaScript。无构建步骤。无 npm。无框架。一个文件。

字体走 Google Fonts CDN：
- Instrument Serif（标题展示）
- Noto Serif SC（中文展示）
- JetBrains Mono（正文 / 数据）

## 项目结构

```
battle-log/
├── index.html        # 整个应用——打开这个
├── README.md         # 英文版
├── README.zh-CN.md   # 你正在看的这个
├── LICENSE           # MIT
└── .gitignore
```

就这些。没有 `src/`，没有 `dist/`，没有 `node_modules/`。你发布的文件就是你编辑的文件。

## 致谢

150 题路线图来自 [NeetCode](https://neetcode.io/roadmap)——链接指向原版 LeetCode 题目和 NeetCode 视频解法。本工具不托管任何题目内容，只是上面一层薄薄的组织层。

## 作者

由 **Alex Nan** 制作 —— [github.com/AlexNtFound](https://github.com/AlexNtFound)。

如果你 fork 或再分发本项目，请保留 `LICENSE` 中的版权声明以及 `index.html` 顶部的 banner 注释。

## 协议

MIT —— 见 [LICENSE](./LICENSE)。版权 © 2026 Alex Nan。
