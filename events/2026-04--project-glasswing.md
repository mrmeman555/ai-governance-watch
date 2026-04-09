# Event: Project Glasswing Launches

## Date
2026-04-07

## Source
- [Anthropic announcement](https://www.anthropic.com/glasswing)
- [CrowdStrike on Mythos Preview](https://www.crowdstrike.com/en-us/blog/crowdstrike-founding-member-anthropic-mythos-frontier-model-to-secure-ai/)
- [CyberScoop — Open Source Vulnerability Implications](https://cyberscoop.com/project-glasswing-anthropic-ai-open-source-software-vulnerabilities/)
- [Fortune — Anthropic Claude Mythos](https://fortune.com/2026/04/07/anthropic-claude-mythos-model-project-glasswing-cybersecurity/)
- NBC News (April 8, 2026)
- WIRED (April 8, 2026)
- ZDNET (April 8, 2026)
- Inside Defense (April 8, 2026)

## What happened
Anthropic launched Project Glasswing — a restricted initiative giving ~50 organizations access to Claude Mythos Preview, a frontier AI model purpose-built for vulnerability discovery.

> *"Mythos Preview has already found thousands of high-severity vulnerabilities, including some in every major operating system and web browser. Given the rate of AI progress, it will not be long before such capabilities proliferate, potentially beyond actors who are committed to deploying them safely. The fallout—for economies, public safety, and national security—could be severe. **Project Glasswing is an urgent attempt to put these capabilities to work for defensive purposes.**"*
> — [Anthropic](https://www.anthropic.com/glasswing)

**Partners:** AWS, Apple, Google, Microsoft, Cisco, CrowdStrike, Palo Alto Networks, JPMorganChase, NVIDIA, Broadcom, Linux Foundation.

**Funding:** $100M in model usage credits + $4M+ in direct donations to open-source security organizations (Linux Foundation, Apache Software Foundation, Alpha-Omega, OpenSSF).

**System card:** Anthropic published a [244-page capabilities assessment](https://red.anthropic.com/2026/mythos-preview/) detailing what Mythos Preview can do. The numbers are staggering.

**Key findings so far:**
- 27-year-old vulnerability in OpenBSD — signed integer overflow in TCP SACK implementation, remote denial of service via null pointer dereference
- 16-year-old vulnerability in FFmpeg H.264 codec — slice counter mismatch between 32-bit and 16-bit fields causes out-of-bounds heap write. Automated tools executed this code 5 million times without catching it.
- 17-year-old FreeBSD NFS RPC vulnerability (CVE-2026-4747) — stack buffer overflow in RPCSEC_GSS authentication allowing unauthenticated root access via ROP chain fragmented across multiple packets
- Autonomously chained up to 4 Linux kernel vulnerabilities (KASLR bypasses, OOB read/writes, heap manipulation) to gain full machine control
- Firefox 147 JavaScript engine: 181 working exploits (vs. 2 for the previous model, Opus 4.6)
- OSS-Fuzz benchmarking: 595 crashes at tiers 1-2, 10 full control flow hijacks vs. 1 for prior models
- Thousands of previously unknown high-severity flaws across foundational software
- Can reverse-engineer closed-source and firmware targets

**The human factor:** "Engineers at Anthropic with no formal security training have asked Mythos Preview to find remote code execution vulnerabilities overnight, and woken up the following morning to a complete, working exploit."

**Cost:** $50–$2,000 per individual exploit. ~$20,000 for the full OpenBSD vulnerability search (~1,000 scaffold runs). ~$10,000 for FFmpeg.

**Disclosure:** Over 99% of discovered vulnerabilities remain unpatched. Anthropic uses SHA-3 hash commitments to prove possession of undisclosed findings without revealing details.

**Access:** Restricted to ~50 partner organizations. Anthropic does not plan to make Mythos Preview generally available but aims to "enable users to safely deploy Mythos-class models at scale" with safeguards in an upcoming Opus model. Innovaiden estimates the capability gap is temporary — 12-18 months before broadly accessible.

## Day-after fallout (April 8, 2026)

Glasswing dominated headlines the day after launch:

- **National security:** Former national security officials are using the launch to urge Congress to renew Section 702 of the Foreign Intelligence Surveillance Act, citing increased cyber risks from frontier models.
- **Stock market:** Cybersecurity stocks surged — CrowdStrike and Palo Alto Networks in particular, as investors view their Glasswing partnership as a critical "enforcement layer" for AI-era security.
- **Pentagon FY2027 budget:** Released the same day. Proposes massive expansion in autonomous warfare and AI adoption, while cutting CISA's budget by $707M to refocus it on protecting critical infrastructure.

The timing is hard to ignore: the Pentagon is expanding AI offense while cutting the agency responsible for civilian defense — on the same day the most powerful vulnerability discovery AI in history goes public.

## Who's affected
Every organization that depends on software. The vulnerabilities Mythos found exist in foundational infrastructure (operating systems, browsers, media libraries) that virtually every enterprise runs. More specifically: GRC consulting firms, assessors, vCISOs, and any organization subject to security compliance frameworks.

## Framework impact
- **SOC 2:** CC3.2 (Risk Assessment) — legacy code risk ratings no longer defensible. CC4.1 (Monitoring) — "periodic" scanning may not meet "effective" threshold. CC7.1 (Vulnerability Management) — must expand beyond known-CVE remediation.
- **HITRUST:** 07.d (Technical Vulnerability Management) — may need to include AI-augmented discovery as a standard input. 01.v (Information Access Restriction) — zero-day exposure affects access control risk calculus.
- **HIPAA:** §164.308(a)(1) — risk analysis that doesn't account for AI-discoverable vulnerabilities in ePHI systems is arguably incomplete.
- **ISO 42001:** None directly (Glasswing is about what AI finds, not AI governance itself)
- **NIST AI RMF:** None directly

## Key links
- [Project Glasswing — Anthropic](https://www.anthropic.com/glasswing)
- [Mythos Preview Capabilities Assessment (system card)](https://red.anthropic.com/2026/mythos-preview/)
- [Innovaiden — Glasswing assessment baseline analysis](https://www.innovaiden.com/insights/project-glasswing-cybersecurity-assessment-baseline)
- [Simon Willison — Glasswing analysis](https://simonwillison.net/2026/Apr/7/project-glasswing/)

---

*Added: 2026-04-08*
