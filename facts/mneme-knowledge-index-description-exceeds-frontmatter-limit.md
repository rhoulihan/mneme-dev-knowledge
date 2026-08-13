---
topic: mneme-knowledge-index-description-exceeds-frontmatter-limit
---
- [gotcha] mneme's adopt/index generation for a knowledge-index skill builds the SKILL.md frontmatter description by concatenating a scope-prefix string with the plugin's plugin.json description field with no length check, which produced a 579-character description — over Claude Code's 500-character SKILL.md frontmatter limit — only caught by a separate lint step. #mneme #skill-frontmatter #claude-code-platform #plugin-manifest (verified: 2026-08-13)
