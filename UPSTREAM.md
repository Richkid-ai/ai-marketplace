# Upstream tracking

Every package in `plugins/` or `skills/` is a reviewed COPY of a third-party source, not a link. This table tracks what was copied, from where, and when — so we know exactly what a teammate is running.

| Package | Upstream repo | Copied commit SHA | Copy date | Notes |
|---|---|---|---|---|
| ponytail | https://github.com/DietrichGebert/ponytail (MIT) | e3ba2aa6f1e6f0bc4d69eb09c9f0d0a93af56156 | 2026-09-23 | Claude Code plugin only — 3 Node.js lifecycle hooks (SessionStart, SubagentStart, UserPromptSubmit), 6 skills. Other-agent files (Cursor/Codex/Copilot/Gemini/etc.), MCP server, benchmarks, tests, docs skipped as not needed. |
| cowork-plugin-management | https://github.com/anthropics/knowledge-work-plugins/tree/main/cowork-plugin-management (Anthropic) | 1bd42820da111e5f0206e570bf5228a1c35839c7 | 2026-09-23 | Markdown-only plugin, no hooks/scripts/MCP config — safe. Requires the Cowork desktop app environment, not plain Claude Code; skills won't trigger correctly otherwise. |
| product-management | https://github.com/anthropics/knowledge-work-plugins/tree/main/product-management (Anthropic) | 1bd42820da111e5f0206e570bf5228a1c35839c7 | 2026-09-23 | Markdown-only skills, no hooks/scripts. Declares .mcp.json for ~14 third-party services (Slack, Linear, Asana, Notion, Figma, Gmail, Calendar, etc.) — each is opt-in per user via their own OAuth login, nothing connects automatically on install. Checked stakeholder-update and other skills: they draft output for the user, never auto-send. |
| productivity | https://github.com/anthropics/knowledge-work-plugins/tree/main/productivity (Anthropic) | 1bd42820da111e5f0206e570bf5228a1c35839c7 | 2026-09-23 | Markdown-only skills, no hooks/scripts. Declares .mcp.json for Slack, Notion, Asana, Linear, Gmail, Calendar, etc. — same opt-in-per-user model as product-management. |
