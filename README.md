# JS_Skills — Claude Code 自定义命令合集

> JaysinSU 的个人 Claude Code Skills 仓库，持续更新。

本仓库统一管理所有运行在 [Claude Code](https://claude.ai/code) 上的自定义命令（Custom Commands / Skills），覆盖 AI 情报采集、科研写作等场景。

---

## Skill 列表

| Skill | 目录 | 用途 | 命令数 |
|-------|------|------|--------|
| AI 情报采集 | [`ai-intel/`](./ai-intel/) | 自动采集、过滤、整理 AI/Agent 领域最新动态，输出 Daily Digest 到 Obsidian | 4 |
| 科研写作助手 | [`research-writing/`](./research-writing/) | 面向本科/研究生的论文写作全流程辅助，支持头脑风暴、章节写作、LaTeX 输出 | 1 |

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
└── research-writing/                ← 科研写作 Skill
    └── research-writing.md          ← /research-writing 论文写作命令
```

---

## 安装方法

将对应 skill 文件复制到 Claude Code 的自定义命令目录：

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

## 更新记录

| 日期 | 变更内容 |
|------|---------|
| 2026-04-17 | 初始建立仓库，迁移 ai-intel（4条命令）、新增 research-writing |
