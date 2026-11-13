# Evidence-First Customer Insight

**Version 1.1.2** · A portable, evidence-first customer research skill by Adrian Majerowski.

This skill helps product and customer teams understand what support tickets, feedback, interviews, research notes, and community conversations actually support. It keeps requests and opinions visible without treating them as validated problems or automatic product decisions. It reports evidence, uncertainty, and useful ways to learn more; prioritization remains the team's job.

## Install or use it

The skill itself stays the same across compatible agents. Install the whole `customer-evidence` folder in the location your agent scans:

| Agent | This project only | Your projects |
| --- | --- | --- |
| Codex | `.agents/skills/customer-evidence/` | `~/.agents/skills/customer-evidence/` |
| Claude Code | `.claude/skills/customer-evidence/` | `~/.claude/skills/customer-evidence/` |
| Gemini CLI | `.gemini/skills/customer-evidence/` | `~/.gemini/skills/customer-evidence/` |

If you download GitHub's automatic source ZIP, rename its extracted version-suffixed folder to `customer-evidence` before placing it in a skills directory. The folder name must match the `name` in `SKILL.md`.

Keep the folder name and `SKILL.md` together. You do not need a `Codex.md`, `Claude.md`, `AGENTS.md`, or `CLAUDE.md` copy of the skill. Those are project instruction files with different scope; putting the whole workflow there can make it load every session instead of only when relevant.

For another agent that supports the open Agent Skills format, use its documented skills folder. Keep the full `references/` directory beside `SKILL.md`; it contains the complete method and specialist modules that the root skill routes to.

For a chat that cannot install skills, paste `FULL_CHAT_PROMPT.md` and attach `CHAT_METHOD_LIBRARY.md` as a knowledge or chat file. The library contains every specialist module in one document so the chat can access the complete method. Tell the AI to consult the relevant numbered section before its analysis. `CHAT_PROMPT.md` is a short orientation version, useful only when a platform has a very small instruction limit.

The instructions are plain Markdown; no scripts, network access, or special software are required.

The skill uses the open Agent Skills `SKILL.md` directory convention. The complete public method includes the parent methodology plus extraction, synthesis, follow-up, observation, quality audit, netnography, comparison, research framing, next action, stability, communication, solution evaluation, input quality, methodology reasoning, and collection-improvement references. Any compatible agent can use it, but no single skill package can be installed natively in every AI product. The chat fallback requires both the full prompt and method library; a pasted prompt alone cannot give the AI access to files it has not received. Follow each product's own import steps and data-handling settings.

## Getting useful analysis

State the question, timeframe, product version, and sources you are supplying. Preserve record IDs and thread context when possible. For large exports, split the data into labeled parts and tell the AI how many parts to expect; ask for a combined analysis only after the final part. Remove or redact personal and confidential information the model does not need.

The AI can only analyze the material and tools actually available in that session. This package does not connect to support systems, scrape servers, guarantee complete history, or independently verify customer identity.

## License

Copyright © 2026 Adrian Majerowski. All rights reserved. The included `LICENSE.md` grants no-fee use by one person and their organization, including internal team use, while restricting external redistribution and resale. This is not an open-source license.

## Compatibility

The package is plain Markdown and requires no tool calls. Its portable agent format follows the [Agent Skills specification](https://agentskills.io/specification); the prompt fallback works in chat products that accept pasted instructions. Feature support and import flows differ by product, so compatibility with every AI or agent cannot be guaranteed.
