---
name: obsidian-card-knowledge
description: Turn a user's explicitly requested conversation synthesis into consistent Obsidian cards and structured, shareable knowledge articles. Use when the user asks to generate or organize cards and a knowledge base, or explicitly invokes this skill; do not create notes during exploratory discussion alone.
---

# Obsidian Card and Knowledge Article Synthesis

Turn conversation material the user explicitly asks to preserve into two distinct outputs: concise cards and structured, shareable long-form knowledge articles. Write them into the user's chosen Obsidian vault.

By default, synthesize new material from the current conversation since the previous synthesis. If the user explicitly asks for all previous content, use the history available in the current conversation. Do not assume access to other chats; see **Conversation scope**.

## Choose the destination

1. Use a vault path explicitly supplied by the user for this task.
2. Otherwise, if the user has already configured a vault path in the current conversation or local project instructions, use that.
3. Otherwise, locate an Obsidian vault only when there is an obvious accessible candidate. If the target is ambiguous, ask the user which vault and folder to use before writing.
4. Keep cards and long articles in separate subfolders. Prefer existing folder names such as `卡片/` and `知识库/`; if these do not exist, ask before creating a new folder structure when the vault has multiple plausible locations.

Inspect existing notes before writing. Avoid overwriting; create new files or update a directly related article when it is clearly the same topic. Preserve unrelated vault content.

## Editorial principles

- Preserve the user's own wording, concrete experiences, and tone. Mark especially meaningful phrases as the user's own words.
- Distinguish lived facts, the user's interpretation, hypotheses that remain untested, and external research. Do not turn an inference into fact or diagnose the user.
- Cards are short and focused. Long articles begin with a real experience, develop the reasoning, offer a transferable method, and explain limits.
- Do not expand every observation into a long article. Create or update an article only when the theme has enough material to form a coherent, shareable piece; otherwise keep it as a card.
- Add research or theory only when it helps explain the experience. Use reliable sources and accurate links; state what the research does and does not support. Do not add theory just to make content sound more authoritative.
- Check for duplication. If an existing article already covers the same theme, update it instead of creating a near-duplicate.

## Card format

Use the same headings, in this order, for every card:

```markdown
---
type: card
created: YYYY-MM-DD
tags: [tag-one, tag-two]
related:
  - "[[Exact article filename]]"
---

# Card title

## 核心观点
Summarize the insight in one or two sentences.

## 我的经历/观察
Preserve the concrete experience, observation, or quote. If there is no personal evidence, say this is an untested observation; do not invent an experience.

## 可迁移提醒
Give a useful judgment, action, or applicability limit for the reader.

## 反思追问
Ask one question that can deepen thinking.
```

Keep all four sections. If a section is genuinely inapplicable, say so briefly instead of fabricating content. Add multiple quoted links under `related` when a card connects to multiple long articles.

## Long-form article format

Each article should focus on one clear question. Use the following outline where relevant; omit sections that would be forced or repetitive:

```markdown
---
type: knowledge
status: 初稿
created: YYYY-MM-DD
topics: [topic-one, topic-two]
related_cards:
  - "[[Exact card filename]]"
---

# Shareable topic title

## 核心观点
## 问题从哪里来
## 展开解释
## 具体例子
## 可以怎么判断或实践
## 适用范围与边界
## 反思性追问
## 延伸阅读
```

Develop the piece from **real experience → explanation → transferable method → boundaries and open questions**. Make facts, personal judgments, and hypotheses distinguishable. Cite sources near claims they support. Do not pad the article to fill every heading.

## Obsidian properties and links

- Frontmatter must be valid YAML. Use YAML lists for tags and topics.
- In `related` and `related_cards`, each Obsidian link must be a quoted string in a YAML list, e.g. `- "[[Exact note filename]]"`. Do not leave `[[...]]` unquoted or combine multiple links in one scalar.
- Match link targets to the exact Markdown filename without `.md`, including prefixes, spaces, and punctuation. Confirm the destination file exists before writing a link.
- Link cards and their corresponding article both ways: the card's `related` points to the article; the article's `related_cards` points back to the card. When an article links to other existing cards, add that article to those cards' `related` lists too.
- Update the existing article index if the vault has one, using the exact filename in links.
- If a note is renamed or moved, update all affected links and recheck them.

## Verify before reporting completion

1. Parse frontmatter as YAML where a parser is available; otherwise inspect indentation, list syntax, and quoting.
2. Check that every internal link in notes created or changed for this task resolves to an existing Markdown file.
3. Confirm each new card/article pair links to each other, and related existing cards link back to the article.
4. Confirm all cards have the four standard sections, the articles have a clear structure, and the index is updated where present.
5. Report which notes were created or updated and what checks passed. Do not claim to have visually inspected Obsidian unless that was actually done.

## Conversation scope

This skill can use the current conversation's available context and files the user provides. A new conversation does not automatically include another chat's full history. If the user wants a different chat synthesized, ask them to provide its text/export or identify accessible source notes; do not pretend to have read content that is unavailable.
