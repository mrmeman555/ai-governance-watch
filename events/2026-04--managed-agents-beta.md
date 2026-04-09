# Event: Claude Managed Agents Enters Beta — Harness as a Service

## Date
2026-04-01

## Source
- [MANAGED-AGENTS] https://platform.claude.com/docs/en/managed-agents/overview

## What happened
Anthropic launched Claude Managed Agents in beta — a pre-built, configurable agent harness running in Anthropic's cloud infrastructure. Instead of building your own agent loop, tool execution, and runtime, enterprises get a fully managed environment where Claude can read files, run commands, browse the web, and execute code.

The timing matters: days after suing to protect their harness (OpenCode), and the same day their harness leaked, Anthropic started selling the harness as a managed service. They stopped fighting the pattern and started monetizing it.

The four core concepts map to the standard harness architecture:

| Managed Agents concept | Harness component |
|----------------------|-------------------|
| **Agent** (model + system prompt + tools + MCP servers) | Tool system + Permission layer |
| **Environment** (container with packages, network rules) | Orchestration + Sandboxing |
| **Session** (running instance, generates outputs) | Context management + Memory |
| **Events** (messages, tool results, status updates) | Audit / logging |

Multi-agent orchestration and persistent memory are in research preview. The harness is now a product category — something you buy, not just something you build.

## Who's affected
Enterprise AI adopters. Managed Agents shifts the deployment model from "build your own harness" to "buy a managed one." This changes the responsibility model for governance — organizations inherit some controls from Anthropic but own the configuration, tool scoping, and data handling.

## Key links
- [Claude Managed Agents docs](https://platform.claude.com/docs/en/managed-agents/overview) [MANAGED-AGENTS]
- [API reference](https://platform.claude.com/docs/en/api/beta/sessions) [MANAGED-AGENTS-API]

---

*Added: 2026-04-08*
*Citation keys reference [SOURCES.md](../SOURCES.md).*
