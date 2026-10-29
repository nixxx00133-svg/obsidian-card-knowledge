# Prompt-only use in other chat models

Use this adapter for chat products without an installable Agent Skills feature or local filesystem access. It works with the model's ordinary chat or custom-instructions feature; exact UI names vary.

1. Paste the repository's `SKILL.md` instructions into the custom agent/system instructions, or attach them to the current chat.
2. Discuss normally. When ready, explicitly ask to generate cards and a knowledge base.
3. Provide the Obsidian folder structure. If the model cannot read or write local files, ask for separate Markdown outputs for each card and article. Save those files manually into Obsidian.
4. Ask it to check frontmatter syntax and exact internal-link targets against the filenames you provide. Do not claim that local files were written or links were opened unless the product actually has those capabilities.

The content structure is portable; automatic discovery, filesystem access, YAML validation, and link checking depend on the host product and tools.
