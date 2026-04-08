# AI Security & Governance — Reference Notes

A collection of reference material on agent harnesses, AI governance gaps, and recent events reshaping cybersecurity assessment practices.

---

## What happened this week

**March 31 — Claude Code source leak.** A misconfigured npm package exposed 513,000 lines of Anthropic's agent harness source code. Not a breach — a supply chain packaging failure. One missing config line. The leaked architecture revealed the full orchestration layer: ~40 tools, dynamic permission gates, memory consolidation, subagent orchestration, and a hook system for injecting custom governance. DMCA takedowns are in progress, but the architecture is now public knowledge.

**April 1 — OpenClaw hits 247K GitHub stars.** The first popular open-source agent harness proved the harness — not the model — is the product. You can swap in Claude, GPT, Gemini, or a local model. The model is interchangeable. The harness is what gives it agency. When Claude Code's source leaked the same week, people could compare the proprietary harness to the open-source one side by side. Same architecture.

**April 1 — Claude Managed Agents enters beta.** Anthropic began selling the harness itself as a managed service — containerized execution, built-in tools, persistent sessions, network access controls. Multi-agent orchestration and persistent memory are in research preview. [Docs](https://platform.claude.com/docs/en/managed-agents/overview)

**April 7 — Project Glasswing launches.** Anthropic deployed Claude Mythos Preview to ~50 partner organizations (AWS, Apple, Google, Microsoft, CrowdStrike, Palo Alto Networks, and others) with $100M in usage credits. Mythos has already found thousands of high-severity zero-days — including a 27-year-old bug in OpenBSD and a 16-year-old flaw in FFmpeg that automated tools ran 5 million times without catching. [Announcement](https://www.anthropic.com/glasswing)

**The thread connecting all of it:** The model is the brain. The harness is the nervous system. The harness is where governance controls need to live — and the frameworks (ISO 42001, NIST AI RMF, SOC 2 TSC) are mostly silent on it. Meanwhile, AI-powered vulnerability discovery just demonstrated that the "reasonable security" baseline has shifted.

---

## Contents

### [Agent Harnesses — What Makes AI Models Intelligent](agent-harnesses.md)
What an agent harness is, why it matters more than the model itself, and how three real harnesses (Claude Code, OpenClaw, Claw Code) reveal a converging architecture that governance frameworks haven't caught up to yet.

### [Agent Harness Risk & Control Matrix (SOC 2 Mapping)](harness-risk-matrix.md)
A control-by-control mapping of harness governance areas — tool execution auth, payload logging, memory persistence, subagent delegation, rate/cost guardrails — to SOC 2 Trust Services Criteria. Includes vCISO implementation notes.

### [Project Glasswing — What It Means for GRC](glasswing-brief.md)
Anthropic launched Project Glasswing on April 7, 2026 with AWS, Apple, Google, Microsoft, CrowdStrike, and others. Their Mythos model found thousands of zero-day vulnerabilities — including bugs that survived 27 years of human review. This brief covers what that means for SOC 2, HITRUST, HIPAA, and vCISO advisory practices.

---

## Key Links

| Resource | Link |
|----------|------|
| Project Glasswing (Anthropic) | [anthropic.com/glasswing](https://www.anthropic.com/glasswing) |
| Claude Code leaked source (DMCA in progress) | [github.com/codeaashu/claude-code](https://github.com/codeaashu/claude-code) |
| Claurst — clean-room Rust rewrite | [github.com/Kuberwastaken/claurst](https://github.com/Kuberwastaken/claurst) |
| OpenClaw — first popular open-source harness | [github.com/openclaw/openclaw](https://github.com/openclaw/openclaw) |
| Cranium AI — harness-level governance platform | [cranium.ai](https://cranium.ai/) |
| Claude Managed Agents — Anthropic's harness-as-a-service (beta) | [platform.claude.com](https://platform.claude.com/docs/en/managed-agents/overview) |
| Innovaiden — Glasswing assessment baseline analysis | [innovaiden.com](https://www.innovaiden.com/insights/project-glasswing-cybersecurity-assessment-baseline) |

---

*April 2026 — Aaron Reveley*

---

> *Research and analysis by Aaron Reveley. Writing assisted by Claude (Anthropic).*
