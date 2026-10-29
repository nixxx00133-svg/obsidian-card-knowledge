# Obsidian Card and Knowledge Skill

A Codex skill that turns explicitly selected conversation material into concise Obsidian cards and structured, shareable long-form notes.

## Use

Ask Codex to “generate cards and a knowledge base” or invoke `$obsidian-card-knowledge` after a discussion. The skill processes the current conversation context; it does not automatically import other chats.

Before the first write, tell the skill which Obsidian vault and folders to use. It keeps cards and long articles separate, uses consistent metadata and headings, and checks YAML and internal links.

## Install locally

Copy this repository's contents into a skill directory, for example:

```text
~/.codex/skills/obsidian-card-knowledge/
```

Then invoke `$obsidian-card-knowledge` in Codex. You can also use Codex's skill installer with this GitHub repository.

## Portability

This skill contains no personal vault path or conversation archive. It asks the user to select or confirm an accessible Obsidian destination when one is not already configured.
