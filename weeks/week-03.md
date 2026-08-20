# Week 3: The Marketing Intelligence Harness

**Session Length:** ~3 hours
**Objective:** Build a Claude Code marketing harness that reads your Brand Context Vault, pulls real Instagram and Facebook data through Composio, writes a useful weekly insights report, saves it back into the vault, and delivers it to you automatically every week.

> **Note on tooling:** Earlier outlines planned n8n as the Week 3 environment. This week uses **Claude Code** as the practical agent harness instead. Claude Code runs on the student's own laptop, its skills system fits a weekly report cleanly, and it reads the vault directly. Hermes is not installed for the student. Week 4 hardens and expands this same harness rather than introducing a different product.

---

## Key Concepts Covered

- The harness anatomy: nine layers (model, instructions, context, skills, tools, permissions, memory, trigger, delivery)
- The marketing-deputy analogy for an autonomous system
- Diagnosing failures by layer
- CLAUDE.md as the instruction file, scoped to this project
- A Claude Code skill (`.claude/skills/weekly-marketing-insights/SKILL.md`) as a reusable operating procedure
- Composio Claude Code plugin: connecting Instagram Business and a Facebook Page with managed OAuth
- Meta tool quirks: IG integer timestamps vs FB string dates, metric suppression under 100 followers, deprecated post insights
- The report structure: Snapshot, Top Performers, What's not working, Replication playbook, Action items
- Grounding rule: real numbers only, "no data" when absent, never invent metrics
- Scheduling: why Claude Code's in-session scheduler is not durable, and the OS cron / Task Scheduler route for a weekly job
- Delivery: email via a connected Composio email toolkit, or honest vault-only fallback

## Deliverable

**A weekly Meta insights report that runs and delivers itself:** a Claude Code project with CLAUDE.md, one verified skill, Composio connected to Instagram and Facebook, a reports/weekly/ output folder with a run log, and a Monday 08:00 schedule on the student's laptop. The report follows the exact five-heading structure and stays under 500 words.

## Lesson Arc (mapped to the handout)

1. **Recap and readiness gate (25 min):** confirm the Class 2 vault opens in Claude Code, has the six required notes, repair anything missing with a safe prompt, run a brand-specific context test. Capped at 25 minutes, not a repeat of Class 2.
2. **Harness architecture (25 min):** the nine-layer diagram, the marketing-deputy analogy, and a diagnose-by-layer table.
3. **Install instructions and skill (25 min):** write CLAUDE.md and `.claude/skills/weekly-marketing-insights/SKILL.md` at the exact paths.
4. **Connect Composio (30 min):** install the plugin, connect instagram and facebook, verify before building. Secret handling rule stated plainly.
5. **Inspect raw data (20 min):** find missing or suppressed metrics before analysis.
6. **Run and critique (20 min):** manual run, score against the grounding test.
7. **Test schedule and delivery (20 min):** near-term cron run, confirm the report lands and the run log records status.
8. **Weekly production schedule (15 min):** swap to Monday 08:00, final checklist, homework.

## Prerequisites

- Claude Code installed (free to start, per the official install docs)
- The Class 2 Brand Context Vault on the laptop you will use in class
- An Instagram Business or Creator account linked to a Facebook Page, under one Meta Business Manager
- Composio account (free tier) for the Claude Code plugin and Meta toolkits
- A connected email toolkit (Gmail or similar) if you want the report delivered by email; otherwise the report lands in the vault and the log flags it not delivered

---

*Full details in the [Class 3 handout](../class-03/). Week 4 expands this harness into the marketing operating system.*
