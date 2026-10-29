# Obsidian Card and Knowledge Skill

Turn explicitly selected conversation material into concise Obsidian cards and structured, shareable long-form notes.

The writing rules are largely platform-neutral. What changes by platform is how the skill is installed and whether the agent can write to a local Obsidian vault.

## Platform support

| Platform | How to use | Directly write local Obsidian files? |
|---|---|---|
| Codex | Install this repository as a skill; invoke `$obsidian-card-knowledge` or ask to generate cards and a knowledge base. | Yes, when the local Codex environment can access the selected vault. |
| Claude Code | Install under `~/.claude/skills/obsidian-card-knowledge/`; invoke `/obsidian-card-knowledge`. | Yes, when Claude Code has permission to access the vault path. |
| Gemini CLI | Install from this repository with `gemini skills install`; check with `/skills list`. | Yes, when the local CLI has access to the vault path. |
| ChatGPT Skills | Upload the skill through the Skills interface where available. | Depends on the chat surface and connected file tools; otherwise it returns Markdown for you to save. |
| Other chat models | Paste `SKILL.md` or the prompt-only adapter into the chat or a custom agent. | Usually no; save the generated Markdown into Obsidian yourself unless the product provides file access. |
| Doubao | Add the instructions to a custom agent, or paste them into the current chat. | Ordinary chat/custom agents need an explicit local-file tool; otherwise save Markdown manually. |
| DeepSeek | Use prompt-only instructions in regular chat; use a project instruction in DeepSeek Harness. | Harness documents local file read/write; direct `SKILL.md` import is not confirmed. |
| Kimi | Install/create a Skill from the Skills panel or `/skill-creator`; Kimi Work is the desktop option. | Kimi Work can work with authorized local project files; ordinary web chat generally returns Markdown. |
| Tongyi / Qwen | Use a custom assistant if available, or paste the instructions; developers can configure a Bailian agent. | Requires an explicitly connected local file tool for local vault writes. |
| WorkBuddy | Import the skill package through its Skills interface, or provide `SKILL.md` as task instructions. | Yes, after granting access to the vault directory and verifying the writes. |

See [`platforms/`](platforms/) for setup and capability notes, including [Doubao](platforms/doubao.md), [DeepSeek](platforms/deepseek.md), [Kimi](platforms/kimi.md), [Tongyi/Qwen](platforms/tongyi.md), and [WorkBuddy](platforms/workbuddy.md). Availability and UI steps may vary by plan, workspace, and product version.

## Install

### Codex

Use Codex's skill installer with this GitHub repository, or copy the repository contents into a skill directory such as `~/.codex/skills/obsidian-card-knowledge/`.

### Claude Code

```bash
git clone https://github.com/nixxx00133-svg/obsidian-card-knowledge.git ~/.claude/skills/obsidian-card-knowledge
```

Then invoke `/obsidian-card-knowledge` in Claude Code.

### Gemini CLI

```bash
gemini skills install https://github.com/nixxx00133-svg/obsidian-card-knowledge.git
```

Use `/skills list` to confirm discovery.

### ChatGPT Skills

If your account or workspace has Skills enabled, download this repository and upload the skill through the Skills interface. If the active ChatGPT surface cannot access your local vault, ask for Markdown output and save it yourself.

## Use

After a discussion, ask to “generate cards and a knowledge base” or invoke the skill explicitly. It uses available context from the current conversation; it does not automatically import other chats.

Before its first write, provide or confirm the Obsidian vault and the folders for cards and long articles. The skill keeps the two note types separate, uses consistent metadata and headings, and checks YAML and internal links.

## Portability

This repository contains no personal vault path or conversation archive. The skill asks users to select or confirm an accessible Obsidian destination when one is not already configured.

## Official references

- [OpenAI: Build skills](https://developers.openai.com/plugins/build/skills)
- [OpenAI Help: Skills in ChatGPT](https://help.openai.com/en/articles/20001066-skills-in-chatgpt)
- [Anthropic: Extend Claude with skills](https://code.claude.com/docs/en/skills)
- [Gemini CLI: Agent Skills](https://geminicli.com/docs/cli/skills/)
- [Doubao: custom agents](https://www.doubao.com/legal/feature_intro)
- [DeepSeek Harness](https://www.deepseek.com/zh/harness/)
- [Kimi: Skills](https://www.kimi.com/help/plugins-and-skills/what-are-skills)
- [Kimi Work](https://www.kimi.com/en/help/kimi-work/overview)
- [Alibaba Cloud Bailian: Agent applications](https://docs.bailian.console.aliyun.com/zh/model-studio/single-agent-application)
- [WorkBuddy: product guide](https://www.workbuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Product-Guide)
