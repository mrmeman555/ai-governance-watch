# Event: Claw Code — Clean-Room Harness Rewrite Hits 50K Stars in 2 Hours

## Date
2026-03-31 (hours after the Claude Code leak)

## Source
- [CLAW-CODE] https://github.com/ultraworkers/claw-code
- [CLAW-CODE-SITE] https://claw-code.codes/

## What happened
Hours after the Claude Code source leak, Sigrid Jin published Claw Code — a clean-room rewrite of the agent harness architecture in Rust and Python. No proprietary code. Independently audited. It hit 50K GitHub stars in 2 hours, one of the fastest accumulation rates GitHub has ever recorded.

Claw Code reimplements the core architectural patterns — tool system (19 permission-gated tools), query engine for LLM integration, multi-agent orchestration, and memory management — without copying any Anthropic source. Independent code audits confirmed it contains no proprietary code, no model weights, no API keys, and no user data.

This was the third independent implementation of the same architecture (after Claude Code and OpenClaw). Three codebases, three different languages, one converging pattern. The harness architecture is reproducible. It's not anyone's IP. It's an emerging standard.

The clean-room nature also made it untouchable by DMCA — while Anthropic was filing takedowns against repos hosting the leaked source, the rewrites were legally clean.

## Who's affected
The entire AI agent ecosystem. Claw Code proved that the harness pattern can be independently reproduced, which means governance frameworks need to address the pattern itself — not specific vendor implementations.

## Key links
- [Claw Code repo](https://github.com/ultraworkers/claw-code) [REPO-CLAW-CODE]
- [Claw Code site](https://claw-code.codes/) [CLAW-CODE-SITE]
- [Medium — Claw Code killed Claude Code?](https://medium.com/data-science-in-your-pocket/claw-code-killed-claude-code-02aab80b0838) [CLAW-CODE-MEDIUM]

---

*Added: 2026-04-08*
*Citation keys reference [SOURCES.md](../SOURCES.md).*
