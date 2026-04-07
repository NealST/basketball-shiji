# 工作流程 · Editorial Workflow

> 从选题到发布的完整流程指南

---

## 总览

```
选题 → 研究 → 大纲 → 初稿 → 修订 → 发布
Idea → Research → Outline → Draft → Revision → Publish
```

每篇传记文章的完整流程分为六个阶段，每个阶段有明确的输出物和检查项。

---

## 阶段一：选题 · Idea

**目标**：确定下一篇文章的主角，评估可行性。

**步骤：**
1. 从篮球名人堂球员名单中选择候选人
2. 评估以下维度：
   - 故事弧线是否完整（有起伏、有张力）
   - 资料是否充足（可检索英文/中文来源）
   - 与已发布文章的差异性（时代、位置、风格）
3. 在 `research/<player-slug>.md` 创建研究文件，写下初步选题理由

**输出物：** 确认选题，创建研究笔记文件

**状态标记：** 文章文件尚未创建

---

## 阶段二：研究 · Research

**目标**：收集充足的素材，支撑传记写作。

**步骤：**
1. 打开 `research/<player-slug>.md`，按模板填写基础信息
2. 收集以下来源：
   - 维基百科页面（英文/中文）
   - Basketball-Reference.com 统计数据
   - 重要赛事的赛后报道
   - 名人堂入选演讲
   - 球员自传或重要访谈
3. 整理关键事件时间线、核心数据、重要引言
4. 记录争议点或待核实信息，用 `[?]` 标注

**输出物：** 填写完整的 `research/<player-slug>.md`

**状态标记：** `status: research`

---

## 阶段三：大纲 · Outline

**目标**：搭建文章结构，确认叙事弧线。

**步骤：**
1. 复制 `templates/player-biography.md` 到 `outlines/<player-slug>-outline.md`
2. 使用 `prompts/generate-outline.md` 配合AI生成初版大纲
3. 在每个章节下写出3–5个关键叙事点
4. 确认以下内容：
   - 故事的高潮时刻是否突出？
   - "太史公曰"的核心论点是否明确？
   - 时间线是否合理流畅？
5. 大纲定稿后，作为写作蓝图

**输出物：** `outlines/<player-slug>-outline.md`

**状态标记：** `status: draft`（文章文件已创建）

---

## 阶段四：初稿 · Draft

**目标**：完成第一版可读稿件。

**步骤：**
1. 复制 `templates/player-biography.md` 到 `articles/drafts/<player-slug>.md`
2. 填写YAML前置信息（frontmatter）
3. 参照大纲，逐节起草内容
4. 可使用 `prompts/draft-biography.md` 配合AI生成各节初稿
5. 写作原则：
   - 先保证完整性，不必追求完美
   - 标记 `[待补充]` 或 `[待核实]` 的地方
   - "太史公曰"可最后写，待整体方向明确后再落笔
6. 完成后自读一遍，确认叙事流畅、事实无明显错误

**输出物：** `articles/drafts/<player-slug>.md`（完整初稿）

**状态标记：** `status: draft`

---

## 阶段五：修订 · Revision

**目标**：打磨稿件至发布水准。

**步骤：**

### 5a. 事实核查
- 使用 `prompts/fact-check.md` 配合AI进行一致性检查
- 核实所有数据（夺冠次数、MVP次数、年份等）
- 确认专有名词拼写与译名一致

### 5b. 文风润色
- 使用 `prompts/classical-rewrite.md` 对关键段落进行古典风格润色
- 重点打磨"太史公曰"节
- 检查是否符合文风指南（`guides/style-guide.md`）中的30/70比例

### 5c. 结构优化
- 检查段落节奏是否符合风格指南中的建议
- 确认各节字数大致在建议范围内
- 检查年表是否完整准确

### 5d. 标题与推广文案
- 使用 `prompts/title-hooks.md` 生成标题选项和社交媒体摘要
- 确定最终标题
- 准备发布摘要（100字以内）

**输出物：** 修订后的文章文件，更新 `status: revision`

---

## 阶段六：发布 · Publish

**目标**：将文章发布到目标平台。

**步骤：**
1. 最终校对（错别字、标点、格式）
2. 更新frontmatter：
   ```yaml
   status: "published"
   publish_date: "YYYY-MM-DD"
   word_count: XXXX
   ```
3. 将文件从 `articles/drafts/` 移动到 `articles/published/`
4. 发布到目标平台（微信公众号、Substack、个人网站等）
5. 更新封面图至 `assets/covers/<player-slug>-cover.jpg`（如有）

**输出物：** `articles/published/<player-slug>.md`

**状态标记：** `status: published`

---

## 文件命名规范

| 类型 | 路径 | 命名示例 |
|------|------|---------|
| 文章草稿 | `articles/drafts/` | `michael-jordan.md` |
| 已发布文章 | `articles/published/` | `michael-jordan.md` |
| 研究笔记 | `research/` | `michael-jordan.md` |
| 大纲 | `outlines/` | `michael-jordan-outline.md` |
| 封面图 | `assets/covers/` | `michael-jordan-cover.jpg` |

**命名原则：**
- 全小写英文，空格用连字符 `-` 替代
- 使用球员英文名（slug格式）
- 不使用特殊字符

---

## 快速参考

```
选题完成后：
  → 创建 research/<player>.md

研究完成后：
  → 创建 outlines/<player>-outline.md
  → 创建 articles/drafts/<player>.md（填frontmatter）

初稿完成后：
  → articles/drafts/<player>.md status: draft

修订完成后：
  → articles/drafts/<player>.md status: revision

发布后：
  → 移动至 articles/published/<player>.md
  → status: published，填写 publish_date
```

---

*本文档版本：v1.0*
