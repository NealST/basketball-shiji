# 篮球世纪 · Basketball Shiji

> 以《史记》列传之笔，书写篮球名人堂的传奇岁月。  
> *Retelling the legends of the Basketball Hall of Fame in the narrative style of Sima Qian's Shiji.*

---

## 项目简介 · Project Overview

**Basketball Shiji**（篮球世纪）是一个长篇连载写作项目，借鉴中国古代史书《史记》的纪传体风格，用现代汉语为篮球名人堂球员撰写人物传记。每篇文章融合史料、赛场叙事与人物评论，结尾以"太史公曰"体裁作结，为读者呈现兼具文化厚度与运动激情的篮球史诗。

**Basketball Shiji** is a serialized writing project that applies the biographical narrative tradition of Sima Qian's *Shiji* (Records of the Grand Historian) to Basketball Hall of Fame legends. Each entry blends historical research, game narrative, and character commentary, closing with a "Taishigong yue" (The Grand Historian remarks) section — giving each athlete the weight of a classical historical figure.

**Writing Goals:**
- Craft engaging, long-form biographies of basketball legends for Chinese-language audiences
- Blend classical literary flavor (~30%) with modern Chinese readability (~70%)
- Build a sustainable, AI-assisted editorial workflow for a long-running serialized project
- Publish across media platforms (WeChat, Substack, website, etc.)

---

## 仓库结构 · Repository Structure

```
basketball-shiji/
├── README.md                   # 本文件 · This file
├── articles/
│   ├── drafts/                 # 草稿 · Work-in-progress drafts
│   └── published/              # 已发布文章 · Published articles
├── outlines/                   # 大纲 · Article outlines
├── research/                   # 研究笔记 · Research notes per player
├── prompts/                    # AI写作提示词 · AI prompt files
│   ├── generate-outline.md
│   ├── draft-biography.md
│   ├── classical-rewrite.md
│   ├── fact-check.md
│   └── title-hooks.md
├── templates/
│   └── player-biography.md     # 传记模板 · Reusable biography template
├── assets/
│   └── covers/                 # 封面图 · Cover images for articles
└── guides/
    ├── style-guide.md          # 文风指南 · Writing style guide
    └── workflow.md             # 工作流程 · Editorial workflow
```

---

## 文章前置信息规范 · Frontmatter Conventions

Every article Markdown file must begin with YAML frontmatter in the following format:

```yaml
---
title: "迈克尔·乔丹传"
title_en: "Michael Jordan"
player: "Michael Jordan"
player_zh: "迈克尔·乔丹"
era: "1984–2003"
teams:
  - "Chicago Bulls"
  - "Washington Wizards"
honors:
  - "6× NBA Champion"
  - "6× Finals MVP"
  - "5× MVP"
  - "Defensive Player of the Year (1988)"
  - "14× All-Star"
  - "Hall of Fame (2009)"
tags:
  - "shooting guard"
  - "dynasty"
  - "Bulls"
  - "GOAT"
status: "draft"          # draft | revision | published
publish_date: ""         # YYYY-MM-DD when published
word_count: 0
---
```

**Status values:**
- `draft` — initial writing, incomplete
- `revision` — under editorial review or AI-assisted refinement
- `published` — finalized and released

---

## 使用模板 · Using the Templates

1. Copy `templates/player-biography.md` to `articles/drafts/<player-slug>.md`
2. Fill in the YAML frontmatter with the player's details
3. Follow the section structure in the template
4. Use the prompts in `prompts/` with an AI assistant to generate or refine content
5. Move to `articles/published/` once finalized

---

## 工作流程 · Workflow

See [`guides/workflow.md`](guides/workflow.md) for the full editorial workflow from idea to publication.

---

## 文风指南 · Style Guide

See [`guides/style-guide.md`](guides/style-guide.md) for tone, vocabulary, and structural guidelines.

---

## AI提示词 · AI Prompts

The `prompts/` directory contains reusable prompt files for:
- Generating structured outlines
- Drafting full biographies
- Rewriting drafts in a more classical tone
- Fact-checking and consistency review
- Generating titles and social-media hooks

---

## 许可 · License

This project is for editorial and publishing use. All original writing is copyright the author.

