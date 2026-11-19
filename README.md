# JS_Skills — Claude Code 自定义命令合集

> JaysinSU 的个人 Claude Code Skills 仓库，持续更新。

本仓库统一管理所有运行在 [Claude Code](https://claude.ai/code) 上的自定义命令（Custom Commands / Skills），覆盖 AI 情报采集、科研写作等场景。

---

## Skill 列表

| Skill | 目录 | 用途 | 命令数 |
|-------|------|------|--------|
| AI 情报采集 | [`ai-intel/`](./ai-intel/) | 自动采集、过滤、整理 AI/Agent 领域最新动态，输出 Daily Digest 到 Obsidian | 4 |
| 科研写作助手 | [`research-writing/`](./research-writing/) | 面向本科/研究生的论文写作全流程辅助，支持头脑风暴、章节写作、LaTeX 输出 | 1 |
| 论文插图生成 | [`docpic-prompt.md`](./docpic-prompt.md) | 输入论文文案，自动判断图类型并生成 Gemini（Nano Banana）专用英文图片 prompt | 1 |

---

## 目录结构

```
JS_Skills/
├── README.md                        ← 本文件，总览
├── ai-intel/                        ← AI 情报采集 Skill
│   ├── README.md                    ← ai-intel 详细说明
│   ├── ai-scout.md                  ← /ai-scout 采集命令
│   ├── ai-filter-rank.md            ← /ai-filter-rank 过滤评分命令
│   ├── ai-classify-digest.md        ← /ai-classify-digest 生成简报命令
│   └── ai-research.md               ← /ai-research 深度研究命令
├── research-writing/                ← 科研写作 Skill
│   └── research-writing.md          ← /research-writing 论文写作命令
└── docpic-prompt.md                 ← /docpic-prompt 论文插图生成命令
```

---

## 安装方法

将对应 skill 文件复制到 Claude Code 的自定义命令目录：
ai-intel 命令中的路径均相对于 Obsidian Vault 根目录；请从该目录启动 Claude Code。

```bash
# Windows
C:\Users\<用户名>\.claude\commands\

# macOS / Linux
~/.claude/commands/
```

**ai-intel（目录型 skill）：**
```
.claude/commands/
└── ai-intel/
    ├── ai-scout.md
    ├── ai-filter-rank.md
    ├── ai-classify-digest.md
    └── ai-research.md
```

**research-writing（单文件 skill）：**
```
.claude/commands/
└── research-writing.md
```

**docpic-prompt（单文件 skill）：**
```
.claude/commands/
└── docpic-prompt.md
```

复制完成后，在 Claude Code 中输入 `/` 即可看到对应命令。

---

## Skill 简介

### AI 情报采集（ai-intel）

面向 AI 产品经理的情报自动化工作流，4 条命令构成完整闭环：

```
/ai-scout → /ai-filter-rank → /ai-classify-digest → /ai-research [主题]
  采集         过滤评分           生成简报 & 同步          深度研究（按需）
```

覆盖 GitHub Trending、Hacker News、Reddit、X/Twitter、大厂官方博客，输出结果沉淀至 Obsidian Vault，可选同步飞书多维表格。

→ 详见 [`ai-intel/README.md`](./ai-intel/README.md)

---

### 科研写作助手（research-writing）

面向本科与研究生的论文写作全流程辅助，支持 7 种论文类型，含头脑风暴、章节写作、文献综述、LaTeX 输出等模块。核心原则：流程优先，绝不编造文献。

```
/research-writing
```

→ 详见 [`research-writing/research-writing.md`](./research-writing/research-writing.md)

---

### 论文插图生成（docpic-prompt）

面向建筑学硕士论文的 AI 插图 prompt 生成工具。输入一段论文文案，自动判断图类型（轴测图、理论框架图、空间行为图、设计策略概念图等），输出一条 Gemini（Nano Banana）专用英文 prompt，附中文说明。

风格锁定：素雅技术插图风，暖灰 + 冷蓝色板，米白背景，手绘质感线稿，匿名人物剪影，标注引线 + 图例框。

工作流：英文首次生成 → 确认质量 → 再 prompt 将文案改为中文。

```
/docpic-prompt
```

→ 详见 [`docpic-prompt.md`](./docpic-prompt.md)

---

## 更新记录

| 日期 | 变更内容 |
|------|---------|
| 2026-04-17 | 初始建立仓库，迁移 ai-intel（4条命令）、新增 research-writing |
| 2026-04-22 | 新增 docpic-prompt：建筑学论文插图 Gemini prompt 生成 skill |

## 许可

本项目采用 MIT 许可证，详见 [LICENSE](./LICENSE)。
