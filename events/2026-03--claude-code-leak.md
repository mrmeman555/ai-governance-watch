# Event: Claude Code Source Leak

## Date
2026-03-31

## Source
- [CLAUDE-LEAK-TECHCRUNCH] [TechCrunch — Anthropic took down thousands of repos](https://techcrunch.com/2026/04/01/anthropic-took-down-thousands-of-github-repos-trying-to-yank-its-leaked-source-code-a-move-the-company-says-was-an-accident/)
- [CLAUDE-LEAK-FUTURISM] [Futurism — Anthropic suddenly cares about IP](https://futurism.com/artificial-intelligence/anthropic-suddenly-cares-about-intellectual-property-claude-leak)
- [DMCA-ANTHROPIC] [GitHub DMCA notice](https://github.com/github/dmca/blob/master/2026/03/2026-03-31-anthropic.md)

## What happened
A misconfigured npm package (version 2.1.88 of @anthropic-ai/claude-code) shipped a 59.8 MB source map file that exposed the complete TypeScript source code — 513,000 lines across 1,906 files. Security researcher Chaofan Shou tweeted the discovery, and 16 million people saw the thread.

This was the proprietary harness Anthropic had just sued to protect (see [Anthropic v. OpenCode](2026-03--anthropic-v-opencode.md)). The leaked architecture revealed:
- **~40 tools** — file read/write, bash execution, web search, notebook editing, subagent dispatch
- **Dynamic permission checking** — every tool call goes through a permission gate (allow, deny, ask user)
- **Memory consolidation** — "autoDream" system that summarizes and compresses context between sessions
- **Subagent orchestration** — spawns child agents with isolated contexts for parallel work
- **Undercover mode** — strips Anthropic branding from commits (for enterprise clients)
- **Feature flags** — KAIROS (always-on proactive assistant), ULTRAPLAN (remote Opus planning sessions)
- **Hook system** — PreToolUse, PostToolUse, PreCompact, SubagentStart/Stop lifecycle events

Not a breach. Not a hack. A supply chain packaging failure — one missing exclusion in a config file exposed the entire architecture of a $2.5B AI product.

**The DMCA fallout:** Anthropic filed takedown notices that accidentally took down 8,100 legitimate GitHub repos. They retracted most of them, ultimately targeting only 1 repo and 96 forks with actual leaked code. Engineer Boris Cherny acknowledged the overbroad takedowns were unintentional.

When people compared the leaked architecture to OpenClaw, they saw the same pattern. Tools, permission gates, memory, subagent orchestration, audit logging. The convergence was now provable.

## Who's affected
Every organization using Claude Code (hundreds of thousands of developers). Every enterprise evaluating AI agent security. The leak exposed what the harness layer looks like — making governance discussions concrete rather than theoretical.

## Key links
- [Leaked source (DMCA in progress)](https://github.com/codeaashu/claude-code) [REPO-CLAUDE-LEAK]
- [Claurst — clean-room Rust rewrite](https://github.com/Kuberwastaken/claurst) [REPO-CLAURST]
- [Collection of analysis and rewrites](https://github.com/chauncygu/collection-claude-code-source-code) [REPO-LEAK-COLLECTION]
- [Full leak analysis](https://claudefa.st/blog/guide/mechanics/claude-code-source-leak) [CLAUDE-LEAK-ANALYSIS]

---

*Added: 2026-04-08*
*Citation keys reference [SOURCES.md](../SOURCES.md).*
