# AI Automation for Marketing Executives — 4-Week Live Course Outline

**Course Title:** AI Automation for Marketing: From Ground Zero to Autonomous Operations
**Target Audience:** Marketing executives & senior marketing leaders
**Delivery Style:** Practical, hands-on, zero fluff. Every session starts from fundamentals, ends with a working deliverable.
**Format:** 4 live sessions × ~3 hours each (one per week)
**Prerequisites:** None technical. Must be honest about what you don't know. Must have real marketing operations pain points to apply the learning to.
**Max Cohort:** 6–8 students (to allow live Q&A and troubleshooting)

---

## Why This Course Exists (Updated)

Marketing executives are drowning in AI hype. Everyone's selling "AI-powered marketing" but nobody is explaining what an LLM actually is, what an API does, or why a webhook isn't a fish. The gap between *having AI tools* and *running AI-powered marketing operations* starts with a basic vocabulary gap — and this course fills it from the ground up.

This is not a theory course. Every week ends with a working artifact the student can use Monday morning. But we don't skip fundamentals just because they're simple. We explain them first, then we build.

---

## Week 1: Foundations of AI Automation — What You're Actually Working With

**Session Length:** ~3 hours
**Objective:** By the end of this session, the student understands exactly what every AI term means, how the pieces fit together, and can look at any marketing task and map it to the right automation approach — without relying on vendor marketing.

### Part 1: The Vocabulary Every Marketing Exec Needs (60 min)

**1.1 What Is a Model?**
- Plain English: a model is a pattern-recognition machine trained on data. It doesn't "think" — it predicts the next most likely word/pixel/action based on what it's seen before.
- Analogy: Like a new hire who's read the entire internet. Brilliant but needs clear instructions, has no context on your brand yet, and can hallucinate confidently.
- Model types relevant to marketing: text models (Claude, GPT), image models (DALL-E, Midjourney), embedding models (for search/similarity).

**1.2 What Is an LLM?**
- Large Language Model = a text model scaled up enough to hold conversations, follow instructions, and generate coherent long-form content.
- Key properties: context window (how much it can "see" at once), token limits, temperature (creativity vs. precision).
- Demo: The same prompt, different models (Claude vs. GPT vs. Gemini) — show how output quality varies.
- No jargon hand-waving. Show the token counter. Show a context window overflow. Make it tangible.

**1.3 What Is an API?**
- Plain English: an API is a waiter. You give it an order (structured request), it brings back what the kitchen (the model/service) made.
- Why it matters for marketers: APIs let one tool talk to another. Claude API lets your marketing stack *programmatically* generate content. n8n uses APIs to connect 200+ tools.
- Analogy: APIs are the difference between copying data manually between spreadsheets and having Google Sheets auto-sync with your CRM.
- Show a real API call (curl or n8n HTTP node) — simple, visual, no code required to understand.

**1.4 What Is a Webhook?**
- Plain English: a webhook is a phone that rings when something happens. "When a new lead fills out the form, call this URL and tell it the lead details."
- Analogy: An API is "go get data from this place." A webhook is "call me when something happens." Pull vs. push.
- Marketing examples: form submission → webhook triggers n8n → Claude enriches lead → Slack notification.
- Live demo: Show a webhook in action (form submit → n8n receives it → logs it). Students see the trigger happen in real time.

**1.5 What Is an AI Agent / Agent Harness?**
- Plain English: an AI agent is an LLM with tools, memory, and autonomy. It doesn't just answer one question — it can be given a goal ("monitor competitors and brief me weekly") and execute multi-step work independently, using tools (web search, APIs, file system) along the way.
- Analogy: Claude.ai is a brilliant intern you have to hand-hold with every prompt. Hermes Agent is that same intern, after 6 months, who knows your brand, works without supervision, and tells you when something needs your attention.
- Agent harness: the software that wraps the LLM with tools, memory, skills, and multi-platform delivery.
- Key distinction: Chat UI (Claude.ai, ChatGPT) vs. Agent (persistent, autonomous, tool-using).

**Quick Vocabulary Quiz:** 5 scenarios, students identify which concept applies. Low stakes, high retention.

### Part 2: The Input-to-Output Pipeline — How AI Agents Actually Work (20 min)

**The Big Picture — Why This Matters Before Anything Else:**

Before we talk about tools, workflows, or automation layers, you need to understand one thing: the architecture is the same every time. Whether you're using Claude.ai for a single task or a multi-agent system running 24/7 — the input-to-output pipeline is identical. Every week of this course teaches you how to optimize one part of this pipeline.

Here's the foundational flow:

```
┌─────────────────────────────────────────────────────────────────┐
│                 THE AGENT PIPELINE (every interaction)          │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  ① YOU GIVE                           ⑥ MODEL PRODUCES         │
│     INPUT ─────────────────────────┐      ┌─── OUTPUT            │
│                                    │      │   (response,         │
│                                    ▼      │    content,           │
│  ② AGENT GATHERS                ┌──────┐  │    action)            │
│     CONTEXT                     │      │  │                      │
│     (brand vault,               │  LLM │──┘                      │
│      projects, docs)            │      │                         │
│                                  │      │                          │
│  ③ AGENT SEARCHES               └──────┘                          │
│     MEMORY                           ▲                            │
│      (past sessions,             ④ + ⑤  → LLM                  │
│      user preferences,                (context + tools            │
│      learned corrections)              + skills + MCP             │
│                                       = augmented input)          │
│  ④ AGENT USES TOOLS                                                │
│     (skills, plugins,                                               │
│      MCP servers)                                                    │
│                                                                     │
│  ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ │
│  The LLM is the brain. Everything else feeds the brain.          │
│                                                                   │
└─────────────────────────────────────────────────────────────────┘
```

**The Simple Analogy: The Marketing Operations Center**

Imagine you're briefing a senior marketing analyst (the LLM). You walk into their office and say "Write a LinkedIn post about our new feature." Here's what actually happens:

| Pipeline Step | In Human Terms | In AI Terms |
|---|---|---|
| **① You give input** | You say: "Write a LinkedIn post about the new analytics dashboard" | The prompt — your instruction to the agent |
| **② Gather context** | Analyst opens the brand book, persona guide, and product specs on their desk | Agent loads brand vault docs, project files, reference material |
| **③ Search memory** | Analyst remembers: "Last time we launched a feature, the CTO persona responded best to 'time saved' messaging" | Agent searches session history + persistent memory for relevant past learnings |
| **④ Use tools/skills/MCP** | Analyst opens LinkedIn, checks character limits, pulls the analytics dashboard screenshot from Google Drive | Agent runs a skill (LinkedIn post format), calls MCP tools (Google Drive, image analyzer, web search) |
| **⑤ All flows to LLM** | Analyst sits down with all gathered material — brand guide, past notes, tool outputs — and starts writing | Everything — context, memory, tool results — is packed into the LLM's input context window |
| **⑥ Model produces output** | Analyst hands back a finished post | The LLM generates the response — text, JSON, action, or decision |

**Why This Pipeline Is the Skeleton of the Entire Course:**

Every week of this course teaches you how to make one part of this pipeline more powerful:

| Course Week | What You Learn | Which Pipeline Step It Optimizes |
|---|---|---|
| **Week 1 (today)** | The vocabulary + this pipeline | Understanding the whole flow |
| **Week 2: Context Engineering** | Building your brand vault, voice guides, persona docs, campaign histories | **Step ②** — giving the agent richer context so it produces better output |
| **Week 3: n8n Workflows** | Connecting tools, automating multi-step marketing tasks, reading/writing context on the fly | **Step ④** — giving the agent tools to act in the real world (send emails, update CRM, post to social) |
| **Week 4: Hermes Agents** | Persistent memory, skills that load automatically, multi-platform autonomous operation | **Steps ③ + ④** — agent remembers past sessions and runs skills without you re-explaining everything |

**Key Insight:** A better prompt helps Step ①. A richer brand vault helps Step ②. Persistent memory helps Step ③. Powerful tools and skills help Step ④. A smarter model helps Step ⑥. **The best automation systems improve ALL steps** — not just one.

**Quick Comprehension Check (2 min):**
- "I spent 10 minutes writing the perfect prompt but Claude still produced generic copy" — which pipeline step is weak? (Answer: Step ② — the agent lacked brand context)
- "My agent gives good output but can't actually send the email or post to LinkedIn" — which step is weak? (Answer: Step ④ — no tools connected)
- "Every session I have to re-explain who our target audience is" — which step is weak? (Answer: Step ③ — memory isn't persisting between sessions)

**The Takeaway:** Every time you interact with an AI agent — whether it's Claude.ai, ChatGPT, or your own Hermes instance — this pipeline is running behind the scenes. Understanding it means you can diagnose *why* an output is weak and know exactly *which lever* to pull to fix it. That's what the rest of this course teaches.

### Part 3: The Four-Layer Automation Stack (40 min)

1. **Chat & Reasoning** (Claude.ai, ChatGPT) — ad-hoc analysis, drafting, brainstorming
2. **Workflow Automation** (n8n) — connecting your tools end-to-end, no code
3. **Autonomous Agents** (Hermes Agent) — persistent AI assistants that learn, remember, and execute
4. **Orchestration** (multi-agent systems) — coordinating multiple AI agents working together

For each layer:
- What it is in plain terms
- A real marketing use case
- What it costs (free/paid/open-source)
- The marketing maturity curve: where is your org?

**Exercise:** Map 10 real marketing tasks to the right layer. Honesty corner: what NOT to automate.

### Part 4: Quick-Build Deliverable (50 min)

**Deliverable: Automation Readiness Map**
A structured document where the student:
1. Lists their top 10 recurring marketing tasks/processes
2. Maps each to the appropriate automation layer (or "don't automate")
3. Identifies which foundational tools they're missing (API access, webhook capability, etc.)
4. Ranks by ROI priority (time saved × frequency × strategic value)

Delivered as: A template they fill out during the session and leave with as their action plan for the next 3 weeks of the course.

### Homework for Week 2
- Get a Claude.ai account (Pro tier recommended, $20/mo)
- Bring 3 real marketing challenges you'd like Claude to help with
- Complete any gaps in the Automation Readiness Map

---

## Week 2: Claude & Context Engineering — Giving Your AI the Right Brand Context

**Session Length:** ~3 hours
**Objective:** Understand the 2026 paradigm shift — models are intelligent enough that prompt engineering is obsolete. The real skill is **context engineering**: building knowledge bases (brand vaults, memory stores, knowledge graphs) that give agents rich brand context so they do their best work without needing perfectly crafted prompts.

**Why this shift matters:** In 2025, marketers needed intricate prompt templates — persona blocks, few-shot examples, chain-of-thought instructions — to get good output from even the best models. By 2026, models like Claude Opus 5 and Fable 5 are capable enough that the bottleneck has moved. The question is no longer "How do I phrase this prompt?" but "Does my agent have the brand context it needs to make good decisions?" A great model with thin context produces generic output. A capable model with rich context produces work that feels like your brand.

**Strictly marketing framing:** This entire session is delivered through the lens of a marketing executive who needs her AI to *already know* her brand, audience, campaign history, and competitive positioning — so every interaction is informed, on-brand, and context-aware from the first message.

### Part 1: Refresher + The Context Shift (15 min)
- Quick recap: what an LLM is and how Claude fits into a marketing stack
- **The 2026 shift: Context > Prompting:**
  - Models today (Claude Opus 5, Fable 5) are intelligent enough to do brilliant work — if you give them the right context to work with
  - Analogy: You don't give a world-class chef a recipe. You stock the kitchen with your ingredients, tell them your taste, and let them cook. The chef is good enough; the secret is the pantry.
  - Prompt engineering was a 2024–2025 skill — teaching fragile models to understand what you wanted. Context engineering is the 2026+ skill — building rich knowledge environments where capable models thrive.
  - Real test: A great prompt on a model with no brand context produces better output than a mediocre prompt — but a capable model with a full brand vault produces output indistinguishable from your senior copywriter.
- Claude's strengths in a context-engineering world:
  - Claude's 200K context window: big enough to hold your entire brand context vault in a single session
  - Claude excels at structured outputs (tables, JSON, markdown) — your brand vault feeds structured data, Claude returns structured content
  - Claude's Artifacts: living documents that reference your brand vault as their source of truth
- The model lineup for marketing use (current as of July 2026) — choosing the right brain for your context:
  - **Claude Haiku 4.5** (fastest, near-frontier): bulk product descriptions, social post variants, A/B subject lines — tasks where speed × volume matters, fed by a slim context slice
  - **Claude Sonnet 5** (balanced daily driver): campaign briefs, competitive analyses, ad copy, email nurture sequences — the standard marketing work, needs a solid context vault
  - **Claude Opus 5** (enterprise): complex analysis, high-stakes messaging, positioning review, strategy — needs your fullest brand context to do its best work
  - **Claude Fable 5** (highest capability): multi-step research agents, competitive intelligence, brand strategy — the top tier, and the one that benefits most from a deep, rich context vault
- **Marketing decision framework:** "For a Q3 product launch with 40 assets across 6 channels, which Claude model do you feed which slice of your brand vault?"

### Part 2: Context Engineering for Marketing (50 min)

**2.1 The Shift: Why Context Engineering Replaces Prompt Engineering**
- **The old way:** Spend 15 minutes crafting the perfect persona block, few-shot examples, and constraint list. Re-engineering prompts per task. Maintaining a library of 50 prompt templates. Every new campaign starts from scratch.
- **The 2026 way:** Spend 15 minutes building a reusable brand context asset (buyer persona doc, voice guide, campaign retro). Point the model at it. Let the model do its job with zero prompt engineering.
- **What changed:** Models in 2025 needed hand-holding — chain-of-thought, explicit reasoning instructions, heavily engineered prompts. Models in 2026 are capable enough that the work goes into **what you tell them, not how you tell them.**
- **The new skill stack for marketers:**
  1. **Knowledge curation** — what brand context you capture (voice, personas, competitive intel, history)
  2. **Knowledge structuring** — how you format it so agents can consume it (structured docs, linked notes, schemas)
  3. **Knowledge accessibility** — how the agent finds the right context at the right time (memory systems, project files, retrieval)
  4. **Knowledge maintenance** — keeping the vault alive as your brand evolves
- **The ROI reframe:** Every hour you invest in building your brand context vault saves 10 hours of future prompt engineering. Context is a compounding asset; prompt libraries are disposable.

**2.2 Building Your Brand Context Vault — What Goes In**

Your brand context vault is the reference library your agent consults before doing any marketing work. It replaces the prompt library. Here's what belongs in it:

| Context Asset | What It Contains | Why the Agent Needs It |
|---|---|---|
| **Brand Voice Guide** | Tone exemplars, do-say/don't-say tables, vocabulary lists, personality traits, voice doppelgängers ("write like Mailchimp meets a knowledgeable friend") | Every piece of content sounds like you, not a generic AI |
| **Buyer Personas (3–5)** | Demographics, job titles, pain points, buying triggers, objections, channel preferences, decision criteria, quoted language from real customers | Content is written for a specific human, not a segment |
| **Competitive Intelligence** | Top 3–5 competitors, their positioning, your differentiators vs. each, messaging gaps you can exploit, recent moves | Content positions against real competitors, not straw men |
| **Product & Feature Specs** | Product descriptions, feature lists, pricing tiers, use cases, integration ecosystem | Content is accurate and specific, not generic |
| **Campaign Histories** | Campaign name, date, channels, target audience, messaging themes, performance metrics, what worked, what bombed, why | Agent learns from past success (and failure) without retelling |
| **Content Library Index** | Links to top-performing content pieces, evergreen assets, cornerstone content by topic | Agent can reference, repurpose, and avoid duplicating |
| **Messaging Hierarchy** | Hero message → supporting messages (3–5) → proof points per message → objection handlers | Consistent narrative across all channels and campaigns |
| **Do-Not-Says** | Banned words, outdated positioning, withdrawn claims, topics to avoid | Prevents embarrassing output without being in every prompt |
| **Industry & Audience Research** | Market trends, relevant statistics, customer interview quotes, social listening insights | Content has texture and authority, not AI-smoothness |

**2.3 Tools for Context Management — Your Brand Vault Stack**

- **Obsidian — The Brand Context Vault Foundation:**
  - Markdown-based, local-first, infinitely linkable
  - Each context asset is a markdown note: `Brand Voice.md`, `Persona - CTO.md`, `Competitor - Salesforce.md`
  - Links between notes create a knowledge graph: a persona note links to the campaign history notes where that persona was targeted, which link to the A/B test results from that campaign
  - Tags organize by type (`#persona`, `#campaign`, `#voice`, `#competitor`), channel (`#linkedin`, `#email`, `#blog`), and status (`#active`, `#archive`, `#draft`)
  - Graph view: see how your brand knowledge connects — visual proof of gaps ("I have personas but no content examples for this segment")
  - Community plugins: Dataview (query your vault), Templater (context templates), Omnisearch (find context fast)
  - **Live demo:** Open an Obsidian vault with a real agency brand — show the knowledge graph, click through linked persona → campaign → performance notes. Show the student what "brand memory" looks like as a file system.

- **GBrain — Knowledge Graphs for Relational Context:**
  - Visual knowledge graphs that show how brand concepts connect: "This campaign reached Persona A through LinkedIn, using Message Theme B, with 3.2x ROAS"
  - Better than folders for understanding relationships between brand assets
  - Useful for agencies managing multiple brands — each brand as a separate graph, no cross-contamination
  - Why it matters for agents: agents can traverse graph relationships ("Find all campaigns targeting Persona A that performed above benchmark") without being explicitly told the connections

- **honcho.dev — Persistent Session Memory for Agents:**
  - The missing piece: agents that remember who you are and what you've been working on — across conversations
  - honcho.dev provides persistent memory for agents: you tell your agent something once ("I'm focusing on ABM for fintech this quarter"), it remembers in the next session
  - How it complements the context vault: the vault is the reference library (stable, curated, versioned). Honcho is the ongoing conversation memory (dynamic, session-to-session, ephemeral context)
  - **Marketing use case:** You start working on a Q3 product launch campaign in Week 1. In Week 2, you ask your agent "What messaging did we decide for the healthcare vertical?" — Honcho remembers the discussion, your vault stores the finalized messaging hierarchy. Together, nothing falls through the cracks.
  - **Real scenario:** A marketing director briefs the agent on Monday about next quarter's event strategy. On Wednesday, they ask "Remind me what we decided about the speaking slot vs. booth debate" — the agent remembers, even though it's been 48 hours and 15 other conversations.

**2.4 Structuring Brand Information So Agents Can Actually Use It**

Not all brand information is equally agent-usable. The key is structure that models can parse reliably.

- **The Context Template — a standard format for every vault entry:**
  ```markdown
  ---
  title: Brand Voice Guide
  type: voice
  status: active
  tags: [voice, foundation, evergreen]
  last_updated: 2026-07-15
  ---
  
  ## Voice Archetype
  "The trusted expert who's also human" — like a senior consultant who knows their stuff but doesn't talk down to you.
  
  ## Tone Scale
  | Situation | Target | Avoid |
  |---|---|---|
  | Blog posts | Authoritative but warm | Academic / corporate |
  | Social media | Conversational, opinionated | Salesy, robotic |
  | Email nurture | Helpful, personal | Pushy, generic |
  | Landing pages | Benefit-driven, confident | Feature-dump, hype |
  
  ## Do Say
  - "Here's what we found"
  - "Our customers tell us"
  - Short sentences. Punchy. Active voice.
  - Use "you" and "your" — audience is the hero
  
  ## Don't Say
  - "Revolutionize" / "disrupt" / "game-changer"
  - "Leverage" / "synergize" / "best-in-class"
  - Named competitors (refer by category: "other analytics tools")
  - Unsubstantiated claims ("we're the #1" without citation)
  
  ## Voice Doppelgängers
  - HubSpot blog (casual authority level)
  - Lenny's Newsletter (personal, opinionated)
  - *Not:* McKinsey (too formal), Apple (too minimal)
  
  ## Vocabulary
  - Use "customers" not "users"
  - Use "insights" not "data" (data is raw; insights are actionable)
  - Use "recommend" not "implement" (we suggest; client decides)
  ```

- **Why structure matters:**
  - YAML frontmatter lets agents filter by type, status, date — "only active buyer personas"
  - Tables are the most reliably parseable format for models — use them for comparisons, scales, and mappings
  - Consistent headings let Claude navigate without needing the full doc in context — it can section-search
  - Frontmatter `type` tags enable your agent to auto-select context: "I'm writing a blog post → load voice guide + relevant persona + tone scale for blogs"

- **From prompt library to context vault — what changes:**
  - Prompt library is procedural: "When writing ad copy, follow this 5-step structure." Each prompt is an instruction.
  - Context vault is declarative: "Here's who we are, who we talk to, what we believe, and what we've learned." The agent figures out how to use it.
  - The prompt library needed updating as models changed. The context vault is model-agnostic — it stays valuable regardless of which AI you use.
  - A context vault can feed Claude, GPT, Gemma, Grok, or your own Hermes agent — it's portable knowledge, not fragile instructions.

### Part 3: Claude with Rich Context — What Changes in Practice (35 min)

**3.1 Before/After Demo — Same Task, With and Without Context**

**Scenario:** "Write a LinkedIn post announcing our new integration with Salesforce."

**Without context vault (the old way):**
The student spends 10 minutes crafting a prompt with persona blocks, tone instructions, audience definitions, and constraint lists. Output is decent — but sounds like every other AI-generated LinkedIn post. Generic.

**With context vault (the new way):**
The student opens their Claude Project configured with the brand context vault. Claude already knows:
- Brand voice: authoritative but warm, avoid hype words, use "customers" not "users"
- Target persona: CTO of mid-market SaaS companies — cares about integration ease, data privacy, time-to-value
- Product details: the integration syncs in 5 minutes with no code, supports BI-directional sync, field-level mapping
- Past campaign data: last integration launch (HubSpot) performed best with "practical value" messaging vs. "strategic partnership" messaging
- Competitive intel: Salesforce ecosystem is crowded — positioning must emphasize ease of setup vs. competitors' 2-week implementation
- Do-not-says: "seamless" (overused), "enterprise-grade" (meaningless), named competitors

**Result:** Claude generates a LinkedIn post that actually sounds like the brand, speaks directly to the right buyer, references real capabilities, and avoids well-worn clichés — in one shot, no prompt iteration. The student spent zero time engineering the prompt and 15 minutes (once) building the context vault.

**3.2 Claude Projects as Your Agent's Brand Workspace**
- **Projects aren't just prompt libraries — they're context containers:**
  - Upload your entire brand context vault (all the docs from 2.2) to a Claude Project
  - Every chat in that project starts with Claude already knowing your brand, personas, competitors, and campaign history
  - Custom instructions become the permanent context layer: "Use the Brand Voice Guide from the project files as your voice reference. When asked about a persona, reference the relevant persona doc. When generating competitive content, reference the competitor docs."
- **The difference:** In 2025, custom instructions were a prompt — "You are a senior marketer who writes for CTOs." In 2026, custom instructions are a librarian — "Reference these context files to understand who we are and who we're talking to."
- **Artifacts** become living documents that the whole team edits — built on top of the context vault's truth

**3.3 Claude's 200K Context — Your Entire Brand Vault, One Upload**
- The 200K context window fits an entire brand context vault (~50–100 well-structured markdown notes) in a single session
- **Practical workflow:** Your Obsidian vault (or folder of markdown files) → export as a single markdown file → upload to Claude project → Claude reads your entire brand knowledge base
- This means: no more "please wait while I upload five documents" — your agent has permanent access to your full brand context
- **Demo:** Drag a student's completed context vault into a Claude project → ask Claude "What's our brand voice on pricing?" → Claude finds the relevant section in the vault and answers from the source of truth → ask "Who are we targeting for the Q4 product launch?" → Claude cross-references personas and campaign history from the vault

**3.4 The Decision Framework — When You Need More Context, Not a Better Prompt**

| Symptom | Old Diagnosis | New Diagnosis | Fix |
|---|---|---|---|
| Output is too generic | "My prompt needs better persona work" | "The model doesn't have enough brand context" | Add brand voice guide + persona docs to vault |
| Output misses audience nuance | "I need more few-shot examples" | "Needs the buyer persona doc with pain points and triggers" | Curate a richer persona doc |
| Output feels off-brand | "Tone instructions aren't specific enough" | "The do-say/don't-say tables aren't complete enough" | Add more exemplars and edge cases |
| Output is factually wrong about product | "Prompt should include product specs" | "Product info isn't in the context vault" | Add product spec doc to vault |
| Output doesn't learn from past mistakes | "I keep having to say the same things" | "Campaign history isn't surfaced to the model" | Add campaign post-mortems to vault |
| Takes 5 iterations to get it right | "I need to refine my prompt technique" | "Context vault needs richer examples and edge cases" | Feed back your corrections into the vault |

**Key insight for marketers:** Every time you find yourself correcting an AI's output, that correction is **new context you should add to your vault**, not a better prompt to write. Corrections are data. The vault gets smarter every time you use it.

### Part 4: Beyond the Chat UI — The API Layer (25 min)

- **What the API enables that chat can't for marketing:**
  - Batch generate 200 localized ad variants in 3 minutes — each variant drawing from a different persona context slice
  - Embed Claude inside your campaign automation (n8n triggers Claude API with context from your vault per lead enrichment)
  - Programmatic context switching: same brief, different persona context → Claude produces 5 variations for 5 segments
- Conceptual walkthrough: "Here's what happens when n8n calls Claude with your brand vault as reference" — no code, just the request/response cycle visualized
- **Cost model for marketing execs:** "Generating 50 personalized email sequences per day costs ~$X in tokens. Compare that to a copywriter — and remember, with a context vault, each email is on-brand on the first generation, not the fifth revision."
- **Decision framework — which Claude interface for which marketing job:**

| Marketing Task | Use This | Why |
|---|---|---|
| Draft one campaign brief with brand vault reference | Claude.ai Project | Vault-loaded, iterative, collaborative |
| Generate 100 local landing pages from persona vault | Claude API via n8n | Programmatic, batch, per-segment context injection |
| Analyze 50 customer transcripts against buyer personas | Claude.ai Project upload | Context window fits transcripts + vault |
| Real-time lead enrichment with company context | Claude inside n8n workflow | Sub-second, event-driven, uses vault persona matcher |
| Daily competitor monitoring brief | Claude as Hermes agent brain | Persistent, scheduled, autonomous, vault-fed |

### Part 5: Live Build — Brand Context Vault (60 min)

Build a reusable brand context vault that feeds your AI agent — replacing the prompt library model. Delivered as an Obsidian vault (or structured markdown folder) + Claude Project configured with vault context.

**The core principle:** This vault is a living asset. Every correction you make to your agent's output is context you should add back to the vault. The vault compounds in value every time you use it.

**Phase 1: Create Your Brand Context Vault (20 min)**

Students build, following along with the instructor:

1. **Create the vault structure** (Obsidian or markdown folder):
   ```
   brand-context-vault/
   ├── 01-voice/
   │   ├── brand-voice-guide.md
   │   └── tone-scale-by-channel.md
   ├── 02-personas/
   │   ├── persona-cto.md
   │   ├── persona-vp-marketing.md
   │   └── persona-procurement.md
   ├── 03-competitive/
   │   ├── competitor-A.md
   │   ├── competitor-B.md
   │   └── positioning-comparison.md
   ├── 04-product/
   │   ├── product-specs.md
   │   ├── features-and-benefits.md
   │   └── pricing-and-tiers.md
   ├── 05-campaigns/
   │   ├── q2-demand-gen-retro.md
   │   ├── q1-product-launch.md
   │   └── content-library-index.md
   ├── 06-messaging/
   │   ├── messaging-hierarchy.md
   │   ├── value-propositions.md
   │   └── do-not-says.md
   └── index.md
   ```

2. **Write the Index** — a single note that links to every section with a description of what each contains. This becomes the agent's "table of contents" for your brand context.

3. **Fill the first 3 context assets** (guided by instructor):
   - **Brand Voice Guide** — using the structured template from 2.4 (tone scale, do-say/don't-say, vocabulary)
   - **One Buyer Persona** — the student's most important audience (structured: demographics, pain points, triggers, objections, channel preferences, quoted language)
   - **Do-Not-Says** — at least 5 things the agent should never say about the brand

**Phase 2: Configure Claude with the Vault (15 min)**

1. Create a Claude Project named after the student's brand
2. Upload the complete context vault (as a single merged markdown file, or folder upload)
3. Set custom instructions as a **librarian instruction** (not a persona prompt):
   ```
   You are a marketing assistant for [Brand Name]. You have access to our brand context vault in this project's files. Before generating any content:
   1. Read the Brand Voice Guide for tone and vocabulary
   2. Reference the relevant Persona doc for audience understanding
   3. Check the Do-Not-Says list before approving any language
   4. Reference Campaign Histories if the task relates to a past campaign
   5. Check Competitive Intelligence if positioning against competitors is relevant
   
   When I ask you who we are, reference the vault. When I ask you to write something, reference the vault. Do not guess — the vault is the source of truth.
   ```
4. **Verification test:** Ask Claude "Who are we and what's our brand voice?" — it should answer from the vault, not from training data.

**Phase 3: Test the Vault Against Real Scenarios (15 min)**

Students run 3 real marketing tasks against their vault-fed Claude project:

1. **"Write a LinkedIn post about our recent [product milestone / feature launch] targeting [persona from vault]. Reference our brand voice guide."**
2. **"Our competitor [name] just announced [feature]. Draft a competitive response brief using our positioning docs. Reference our do-not-says."**
3. **"We're running a campaign targeting [persona from vault] for [campaign type]. What messaging hierarchy from our vault should we use, and what past campaign data supports it?"**

**Phase 4: Feedback Loop — Corrections Become Context (10 min)**

- Review the outputs. Where was Claude off-brand? Where did it miss audience nuance?
- **The vault fix:** Instead of writing a better prompt, add the correction to the vault:
  - "It used 'leverage' — add 'leverage' to the do-not-says list"
  - "It missed the procurement team's price-sensitivity — add that to the persona doc"
  - "It sounded too formal for LinkedIn — add a more casual LinkedIn tone example to the voice guide"
- **Key insight:** Every correction is an investment in the vault. The next generation will be better because you enriched the context, not because you wrote a more clever prompt.

**Deliverable:** A **Brand Context Vault** — a structured knowledge base (Obsidian vault or markdown folder) with an Index, Brand Voice Guide, Buyer Persona, and Do-Not-Says, configured as a Claude Project with librarian-style custom instructions. Students leave with a system they can expand with every campaign, every persona, every competitive insight — reducing context setup from 15 minutes per task to zero.

### Homework for Week 3 (Prepares Your Vault for n8n)
- Add 2 more context assets to your Brand Context Vault:
  - A second Buyer Persona (your next most important audience)
  - One Campaign Retro (any past campaign — what worked, what bombed, why)
- **Vault prep for Week 3:** Make sure your vault path is accessible and you know the exact folder structure (n8n will read these files directly). Ensure your vault has clear YAML frontmatter on each note (type, status, last_updated) — n8n's Code node can parse this for dynamic context filtering.
- Install Docker Desktop (if not already installed) — n8n runs in Docker
- Have access to at least 2 marketing tools you use daily (Gmail, Slack, Notion, Google Sheets, HubSpot, etc.)
- Bring 1 manual marketing workflow you do repeatedly that involves 3+ tools (e.g., "Every Monday I pull LinkedIn ad data, paste into a slide deck, add commentary, and email the team")
- **Optional vault stretch goal:** Add a `tone-scale-by-channel.md` note with platform-specific tone targets (LinkedIn = authoritative but warm, Twitter = conversational/opinionated, email = helpful/personal) — your Week 3 n8n workflows will reference this directly

---

## Week 3: n8n — Vault-Powered Workflows That Feed Your Marketing Stack

**Session Length:** ~3 hours
**Objective:** Connect your Brand Context Vault from Week 2 to your entire marketing stack. Build automated n8n workflows that **pull context FROM the vault** and **write results TO the vault** — making the vault a living asset that grows smarter with every campaign, not a static document you built once and forgot.

**The vault thread:** Every workflow in this session starts with your Week 2 brand vault as the source of truth. When n8n needs to know your brand voice, it reads the vault. When Claude generates content, it's fed context from the vault. When a campaign finishes, the results flow back into the vault. The vault is the hub, n8n is the spoke system.

**Strictly marketing framing:** This session never shows a generic "hello world" workflow. Every build starts from a marketing problem rooted in the gap between having brand knowledge and using it across tools.

### Part 1: Refresher — How n8n Connects Your Vault to Your Tools (15 min)
- Quick recap: what is an API? What is a webhook? (straight from Week 1)
- **The vault connection:** Your Obsidian vault is a folder of markdown files on your filesystem. n8n can READ those files (read file node, RSS/local file trigger) and WRITE to them (write file node, HTTP request to Obsidian Local REST API). Your vault is not just a reference document — it's a machine-readable database.
- **How this changes your approach to workflow design:** Instead of hardcoding brand voice instructions into each n8n prompt, you inject them dynamically from the vault. Change a persona in the vault → every downstream workflow automatically picks up the update. The vault becomes a single source of truth, not 15 different prompt templates scattered across workflows.
- n8n v1.0: self-hosted (keep sensitive campaign data + your vault on your infra) vs. n8n Cloud (start in 5 minutes) — what each costs, when to use which for marketing ops

### Part 2: n8n Architecture — Focus on Vault Integration (25 min)

- **The canvas with the vault as the hub:** triggers → read vault context → Claude generates with context → write results to tools + vault → close the loop
- **File nodes for vault reads:** n8n's Read Binary Files / Read File nodes can read individual markdown notes from your Obsidian vault path. You can read `brand-voice-guide.md` in one workflow step, pass its content into the Claude prompt context, and Claude already knows your voice.
- **Writing to the vault:** n8n's Write File node can append or create new .md files in your vault. A campaign retro is generated → n8n writes it to `brand-context-vault/05-campaigns/q3-campaign-retro.md`. Your vault is now updated. Obsidian's graph view picks up the new note. Your whole knowledge graph grows automatically.
- **Obsidian Local REST API (optional):** For advanced setups, the Obsidian Local REST API community plugin lets n8n create, update, and search notes via HTTP requests — no file path dependencies.
- **Trigger types relevant to marketing:** webhook (form fill, CRM event, tool push), schedule/cron (weekly ad report, daily social queue), file watcher (new vault note created → trigger workflow), manual (click a button to approve and publish)
- **Node types:** action nodes (Gmail send, Slack message, Google Sheet append, HubSpot create contact), data transformation (parse YAML frontmatter from vault notes, extract persona fields, enrich with lookup), HTTP requests (call Claude API, fetch ad platform data), file read/write (interact with vault)
- **Error handling basics for marketing:** what happens when Claude API is busy, HubSpot rejects a contact, or an email bounces — design workflows that fail gracefully instead of falling silent

**Live demo — Vault-to-output in 10 minutes:** n8n reads `brand-voice-guide.md` and `persona-cto.md` from the vault → passes them as context to Claude API → Claude generates a LinkedIn post targeting that persona, using that voice → n8n writes the output to `content-library-index.md` in the vault as a new entry → posts the draft to Slack for approval. Everyone sees the data flow from vault → Claude → tools → back to vault in real time.

### Part 3: Vault-Powered Marketing Workflows (50 min)

Walk through 4 real marketing workflows with live demos. Students follow along on their own n8n instances. Every workflow starts and ends with the Brand Context Vault.

**Workflow 1: Social Content Repurposing Engine (Vault-Fed)**
Campaign scenario: Your team published a 2,000-word thought leadership blog post. You need LinkedIn posts, Twitter threads, and a newsletter blurb — but you don't want to re-explain your brand voice to Claude every time. The vault already knows your voice, personas, and messaging hierarchy.

- **Step 1 — Read vault context:** n8n reads `brand-voice-guide.md` and `tone-scale-by-channel.md` from `brand-context-vault/01-voice/` → extracts tone instructions, do-say/don't-say lists, and LinkedIn-specific tone targets
- **Step 2 — Trigger:** RSS feed detects new blog post, or Notion page tagged "Published"
- **Step 3 — Claude API node (vault-context-injected):** Claude receives the blog post content + the vault voice guide as system context + the relevant tone scale. It generates:
  - 3 LinkedIn post variants (thought-leader, data-driven, customer-story — each matching the vault's LinkedIn tone target)
  - A Twitter thread (5-tweet structure, following the vault's vocabulary rules)
  - A newsletter blurb (matching the vault's email nurture tone)
- **Step 4 — Output to tools:** LinkedIn post via n8n's LinkedIn connector (draft/scheduled), Twitter thread via Twitter API, newsletter blurb appended to an "Upcoming Newsletter" Google Sheet
- **Step 5 — Write back to vault:** n8n creates a new note at `brand-context-vault/05-campaigns/social-content-log.md` appending a row: date, article title, all generated variant URLs, and a link back to the source blog post. The vault now knows what content was produced and when.
- **Key learning:** file read for vault context, multi-output AI with vault-injected prompts, vault write-back for self-documenting workflows
- **Marketing metric saved:** 2 hours/week per article × 4 articles/month = 8 hours/month reclaimed — and every post is automatically on-brand because the vault enforces brand voice without prompt engineering

**Workflow 2: Lead Enrichment — Persona-Matched Routing (Vault-Referenced)**
Campaign scenario: A whitepaper download form captures name + email. But unlike a generic enrichment pipeline, your workflow cross-references the lead against your vault's buyer personas to route them with precision.

- **Step 1 — Read vault personas:** n8n reads `persona-cto.md`, `persona-vp-marketing.md`, and `persona-procurement.md` from `brand-context-vault/02-personas/` → extracts pain points, buying triggers, channel preferences, and objections for each
- **Step 2 — Trigger:** Webhook from form submission (HubSpot form, Typeform, or manual webhook)
- **Step 3 — Claude API node (vault-persona-injected):** Claude receives the lead info (name, email, company domain) + the 3 buyer persona docs from the vault. Claude web-searches the company, then matches the lead to the most relevant persona from the vault based on company profile, job title, and industry. Returns: persona match, enrichment data, and a personalized outreach angle drawn from that persona's pain points and buying triggers.
- **Step 4 — Conditional routing using vault persona data:** If matched to "CTO persona" → route to technical sales team + personalize email using that persona's objections (from vault). If matched to "VP Marketing" → route to marketing sales team + personalize with brand awareness angle (from vault). If matched to "Procurement" → route to deal desk with pricing sensitivity language (from vault).
- **Step 5 — Update vault with new lead pattern:** n8n appends an anonymized note to `brand-context-vault/02-personas/persona-match-log.md`: "Date, lead industry, matched persona, company size range". Over time, this vault document reveals persona concentration patterns — "80% of our leads match the CTO persona" → signal to build more content for VP Marketing.
- **Key learning:** vault persona injection into AI context, conditional routing based on vault data, vault analytics via write-back
- **Marketing metric saved:** Lead response time from 2 hours → 2 minutes. Lead-to-persona matching accuracy improves because the vault personas are the same ones your marketing strategy is built on — no disconnect between how you segment and how you enrich.

**Workflow 3: Content Operations — Vault as the Brand Gate (Vault-Validated)**
Campaign scenario: Your content team produces a draft in Notion. Before it goes live, it must pass a brand voice compliance check against your vault's voice guide and do-not-says. No more sending off-brand copy to the editor and hoping they catch it.

- **Step 1 — Read vault brand rules:** n8n reads `brand-voice-guide.md` and `do-not-says.md` from `brand-context-vault/01-voice/` and `06-messaging/`
- **Step 2 — Trigger:** Notion database status changes from "Draft Complete" to "Ready for Review"
- **Step 3 — Claude API node 1 (Brand Compliance Check):** Claude receives the draft + the vault's brand voice guide + do-not-says list. It checks every sentence against: do-not-say vocabulary, tone scale for the target channel, and persona relevance. Returns a structured compliance report: "✅ Brand voice: Pass (matches 'authoritative but warm' tone). ⚠️ Do-not-say violation found: 'leverage' on line 3 — suggested replacement: 'use'. ✅ Persona alignment: Matches CTO persona pain points."
- **Step 4 — Conditional:** If compliance passes → Claude API node 2 generates a summary of the article for the content library. If compliance flags issues → Slack node sends a message to the writer: "Content flagged for brand voice issues — 3 do-not-say violations found. Fixes recommended. Article held from publication until reviewed."
- **Step 5 — Write to vault:** On approval, n8n creates a new entry in `brand-context-vault/05-campaigns/content-library-index.md` with title, URL, persona targeted, and brand compliance score. Over time, you can query: "Which content pieces scored highest on brand compliance?" — the vault tracks quality automatically.
- **Key learning:** vault as a validation source of truth, conditional branches based on vault rules, automated quality QA
- **Marketing metric saved:** Off-brand content from 3 incidents/month → near zero. Editor review cycle from 2 days → same-day. The vault enforces brand standards mechanically, not manually.

**Workflow 4: Weekly Campaign Dashboard — Pulled from Vault, Written to Vault**
Campaign scenario: Every Monday, n8n produces a campaign performance report. But the report isn't just numbers — it compares performance against the vault's campaign history, competitive intel, and messaging hierarchy to deliver strategic recommendations rooted in your actual brand context.

- **Step 1 — Read vault context:** n8n reads competitive intel (`brand-context-vault/03-competitive/`), messaging hierarchy (`brand-context-vault/06-messaging/`), and past campaign retros (`brand-context-vault/05-campaigns/`)
- **Step 2 — Trigger:** Schedule node — every Monday at 8 AM
- **Step 3 — HTTP Request nodes:** pull campaign data from Meta Ads API, Google Ads API, LinkedIn Campaign Manager API (cost, impressions, CTR, conversions)
- **Step 4 — Claude API node (vault-context-enriched):** Claude receives the campaign data + vault context: competitive positions (e.g., "Competitor A is winning on LinkedIn — we should counter-position there"), past campaign learnings (e.g., "Q2 demand gen underperformed on Meta — don't replicate that channel mix"), and messaging hierarchy (e.g., "The 'innovation' message outperforms 'cost savings' for CTO persona"). Claude generates a 3-section executive summary: "This week's top performer was [Campaign X] vs. benchmark from vault Q2 retro. [Campaign Y] underperforms our competitive position against Competitor A — recommended action: shift budget. New insight: The 'innovation' message variant is outperforming 'reliability' — update messaging hierarchy in vault to reflect this."
- **Step 5 — Write insight back to vault:** n8n appends a campaign note to `brand-context-vault/05-campaigns/weekly-insights.md` with this week's top finding and recommended vault update. The vault grows a "channel performance over time" knowledge base organically.
- **Step 6 — Email delivery:** Gmail/SMTP node sends formatted report to stakeholders — with a footnote: "This report was generated using your brand vault as the context baseline. Campaign retros, competitive intel, and messaging priorities all pulled from your vault."
- **Key learning:** vault context injection for AI analysis, vault write-back for self-improving knowledge, multi-source data aggregation with brand context
- **Marketing metric saved:** Monday report from 2 hours → 5 minutes. But the key metric: every report improves the vault, and a smarter vault means better future reports. Compound improvement, not just time savings.

### Part 4: The Vault-Claude-n8n Bridge — Context Injection Patterns (30 min)

- **The injection pattern — how vault context travels through a workflow:**
  ```
  Vault .md file → n8n Read File → (file content as string) → Claude API prompt context → Claude generates with that context → output flows to tools → n8n Write File → vault .md file updated
  ```
- **Parsing vault frontmatter in n8n:** Use n8n's Code node (JavaScript) or Set node to extract YAML frontmatter from vault markdown notes (type, status, last_updated, tags). This lets you filter: "Only read persona docs where status = 'active'" or "Only pull competitor docs tagged with #priority"
- **Dynamic context injection — persona-selective workflows:** A workflow detects the lead's industry from a form → reads only the relevant persona from the vault (using a lookup on frontmatter) → injects just that persona's context into Claude. Not the whole vault — just the context slice needed.
- **Multi-step vault pipelines — how the vault grows through workflows:**
  - Campaign launches → vault gets a new `campaign-launch-log.md`
  - Content published → vault gets a new `content-library-index.md` entry
  - Competitive brief generated → vault's competitive intel section gets an update
  - Lead patterns analyzed → vault's persona section gets enrichment data
  - Every workflow that touches your brand should leave a record in the vault
- **Cost awareness for marketing budgets:**
  - Each Claude API call in a workflow has a token cost — but injecting vault context is cheap (voice guides are ~2K tokens, personas ~1K each). The vault reduces iteration cost because Claude gets it right on the first generation.
  - Use Haiku for vault-parsing steps (identity extraction, frontmatter queries), Sonnet for content generation, Opus for strategic analysis against vault context
  - Show a real cost calculation: "This lead enrichment workflow costs ~$0.03 per lead + the vault read is free (local file). At 200 leads/month, that's $6. And every enrichment adds a searchable record back to the vault."
- **Error recovery for campaign-critical workflows:** what happens when Claude is down, rate-limited, or returns bad output — design fallback paths (retry with delay, use last cached vault output, alert the team instead of failing silently)

### Part 5: Live Build — Vault-Backed Multi-Channel Campaign Distribution Pipeline (60 min)

Build a publish-ready workflow where the **brand vault is the source of truth for everything the campaign produces.** The vault defines the voice, selects the persona, sets the do-not-says, and stores the results. The workflow is just the delivery mechanism.

**Campaign scenario:** Your team is launching a new research report ("2025 State of B2B Marketing"). The report is done, the landing page is live. Now someone needs to: write the launch posts using the brand's actual voice (from the vault), target the right persona (from the vault), avoid banned language (from the vault), and store everything back in the vault for future reference.

Build this workflow:

1. **Step 1 — Read vault context:** n8n reads `brand-voice-guide.md` and `tone-scale-by-channel.md` → extracts LinkedIn tone target (authoritative but warm), Twitter tone (conversational, opinionated), email tone (helpful, personal), and do-not-says. Also reads `persona-cto.md` (the primary buyer for this report) — pain points, channel preferences, and quoted language.

2. **Step 2 — Trigger — Single "Launch" signal:** A new Notion page tagged "Ready to Publish" with campaign name, report URL, and key stat

3. **Step 3 — Claude generates 4 channel-specific variants, vault-context-injected:**
   - **LinkedIn post:** 3-paragraph post using vault's LinkedIn tone target, addressing CTO persona pain points from vault, avoiding do-not-says from vault
   - **Twitter thread:** 8-tweet arc (hook → findings → surprise stat → CTA) using vault's Twitter tone (conversational, opinionated), with vocabulary approved by vault
   - **Email announcement:** Subject line, preheader, 150-word body, CTA button — using vault's email nurture tone (helpful, personal), referencing CTO persona's buying triggers from vault
   - **Short-form video script:** 60-second script (hook → 3 key stats → CTA overlay) matching vault's brand voice archetype

4. **Step 4 — Tool delivery:** Queue LinkedIn post, Twitter thread, schedule email via Gmail/SMTP

5. **Step 5 — Write campaign launch to vault:** n8n creates a new note at `brand-context-vault/05-campaigns/state-of-b2b-launch.md`:
   ```markdown
   ---
   title: 2025 State of B2B Marketing — Launch
   type: campaign
   status: launched
   tags: [campaign, launch, report]
   date: 2026-07-28
   ---
   ## Campaign Overview
   - **Report URL:** https://...
   - **Target Persona:** CTO (from vault)
   - **Voice Guide Used:** Brand Voice Guide v1
   - **Channels:** LinkedIn, Twitter, Email
   
   ## Channel Assets
   - LinkedIn post: [url]
   - Twitter thread: [url]
   - Email send: [url]
   
   ## Notes
   Campaign launched via n8n vault-backed pipeline.
   All content passed vault brand compliance check automatically.
   ```
   Your vault now has a permanent, structured record of this launch. Next campaign, the vault will have more context to pull from.

6. **Step 6 — Google Sheets performance log:** Append row with campaign name, timestamp, channel URLs, and "Check back in 7 days" placeholder

7. **Step 7 — Human-in-the-loop approval gate:** Before anything goes live, n8n sends a Slack message with preview links and a "👍 Approve / 🔁 Edit / ❌ Cancel" button — the workflow pauses until the marketing director clicks approve

**Deliverable:** A fully functional **Vault-Backed Campaign Distribution Pipeline** — a workflow that reads brand context from the Week 2 vault, generates channel-specific content in the brand's voice, publishes to tools, and writes campaign results back to the vault. Template provided so students can swap in their own vault structure and channel preferences.

### Homework for Week 4
- Ensure your Week 2 Brand Context Vault has at least: Brand Voice Guide, 2 Buyer Personas, Do-Not-Says, and 1 Campaign Retro (these feed directly into the Hermes agent you'll build next week)
- Install Hermes Agent (instructions provided: `pip install hermes-agent`)
- Have a Claude API key ready (guide provided for getting one)
- Look at your vault and identify: which section of the vault do you want your Hermes agent to reference most frequently? This becomes your agent's primary knowledge domain.
- Think of 1 recurring marketing task you'd want an agent to handle autonomously — ideally something that currently consumes 2+ hours of your week (e.g., "Monday morning competitor briefing using vault competitive intel," "inbound lead persona-matching using vault personas," "weekly content performance recap compared to vault campaign history")

---

## Week 4: Hermes Agent — An Agent That Lives in Your Brand Vault

**Session Length:** ~3 hours
**Objective:** Deploy a persistent AI agent that has your Week 2 Brand Context Vault as its memory, knowledge base, and writing desk. The agent doesn't just "have brand memory" — it literally lives in the vault. It reads your voice guide when it writes content, consults your personas before targeting audiences, logs campaign retros back into the vault, and uses honcho.dev for session-to-session persistence. Tie together everything from Weeks 1–3 with the vault as the thread connecting it all.

**The vault thread:** This is the capstone. Week 2 built the vault. Week 3 showed n8n reading from and writing to it. This week, you deploy an agent that **lives inside the vault** — it boots up every morning with your entire brand context already loaded, writes its outputs back into the vault's structure, and uses the vault's knowledge graph as its reference library. The vault is no longer a document you maintain — it's a living knowledge base your agent depends on and improves.

**Strictly marketing framing:** This session is delivered as "You're hiring a new team member — one that never sleeps, never forgets, and costs a fraction of a junior hire. And here's the kicker: on day one, they've already read everything in your brand vault. Every persona document. Every campaign retro. Your voice guide. Your competitor intel. They arrive with complete brand context, not a blank slate." Every concept, every demo, every skill starts from the vault.

### Part 1: Refresher — The Vault Thread Across Three Weeks (15 min)
- **Quick recap — the vault arc:**
  - **Week 2:** You built the vault. Brand Voice Guide, Buyer Personas, Do-Not-Says, Campaign Histories — structured knowledge about your brand.
  - **Week 3:** You connected the vault to n8n. Workflows that read vault context for content generation, wrote campaign data back to vault notes, and used vault personas for lead routing.
  - **Week 4 (today):** Your agent lives in the vault permanently. It doesn't need n8n to read the vault — it has direct filesystem access. It brings together everything: the vault as memory, n8n as tool execution, Claude as reasoning.
- **Why the vault makes agents possible for marketing:** Without the vault, an agent starts blank every time. With the vault, your agent arrives with 30+ hours of brand context pre-loaded. The difference between a generic AI assistant and one that sounds like your brand's senior marketer is the vault.
- **How Hermes connects to the vault specifically:**
  - **Obsidian vault path → Hermes filesystem tool:** Hermes can read any file in the vault — `brand-voice-guide.md`, `persona-cto.md`, `competitor-A.md` — and use that content as system context for reasoning
  - **Vault as skill references:** Skills like "competitor analysis" can be coded to first read the competitive intel section of the vault before researching — so the agent knows what you already know
  - **Vault as output destination:** When Hermes completes a campaign retro, analysis, or content brief, it writes the result as a new vault note — linked to existing vault entries
  - **honcho.dev for session memory:** Between sessions, honcho.dev remembers what you were working on — so the agent doesn't lose track between Tuesday's campaign brief and Thursday's review

### Part 2: What Hermes Agent Is — Your Vault's Permanent Resident (30 min)

**2.1 Core Concepts — The Vault-Living Agent**
- Hermes is an open-source agent framework by Nous Research
- It wraps any LLM (Claude API, GPT, DeepSeek, local models) with tools, memory, and multi-platform delivery
- **The critical vault concept:** Hermes has a `filesystem` tool that can read and write markdown files — exactly the format your Obsidian vault uses. This means your vault is natively accessible to Hermes. No export, no conversion, no special API. Your markdown notes are Hermes' memory store.
- It is NOT a separate model — it's a harness that turns any model into a marketing operations assistant that **already knows your brand because it has read your vault**

**2.2 Key Capabilities — How Hermes Uses Your Vault**

- **Vault-as-memory (read):** Hermes reads your vault on startup or on demand. When you say "Write a LinkedIn post about our new feature," Hermes first reads `brand-voice-guide.md` from the vault for tone instructions, then reads the relevant persona doc (`persona-cto.md`) for audience context, then reads `do-not-says.md` for banned language. Every output is vault-informed.
  - *Marketing scenario:* You ask "What's our competitive position against Competitor A?" Hermes reads `brand-context-vault/03-competitive/competitor-A.md` from your vault → summarizes their positioning, your differentiator, and messaging gaps — from the vault, not from web search.
- **Vault-as-notebook (write):** Hermes creates new vault notes as outputs. Campaign retro analysis → written to `brand-context-vault/05-campaigns/2026-q3-retro.md`. Content brief → written to a content calendar folder in the vault. The vault grows with every agent interaction.
  - *Marketing scenario:* After analyzing this week's campaign performance, Hermes writes a companion note: `week-10-insights.md` linked back to the campaign brief it was created from, with a dataview-compatible frontmatter so Obsidian can query it.
- **honcho.dev for session-to-session persistence:** The vault is your curated knowledge (stable, versioned). But what about the fact that you were mid-way through planning a Q4 campaign when you had to hop on a call? honcho.dev gives Hermes conversational memory — it remembers what you were working on, what decisions were made, and what the next step is.
  - *Marketing scenario:* Monday: You brief Hermes on a competitor launch and ask it to draft a response by Wednesday. Tuesday: You reopen Hermes and say "Continue the competitor response." Hermes remembers the context from Monday (via honcho.dev), reads the competitive intel from the vault, and picks up where it left off.
- **Skills — reusable procedures that reference vault assets:** Skills are markdown files that describe multi-step procedures. They can (and should) reference specific vault folders as context sources.
- **Self-improvement loop feeds the vault:** You give feedback ("This brief didn't use our new competitive positioning") → Hermes patches the skill AND updates the vault (adds the missing competitive insight to the vault) → next execution is better. Feedback improves both the agent and the vault.

**2.3 What Changes for a Marketing Team — The Vault is Now Alive**

- **Before:** You built a vault in Week 2. You connected it to n8n in Week 3. But nobody lives in it — it's a reference library you visit occasionally. Campaign retros are forgotten. Persona updates are manual. Competitive intel goes stale.
- **After:** Your Hermes agent lives in the vault. It reads it for every task. It writes campaign retros back to it. It updates competitive intel when it discovers new information. It notes when a persona assumption is outdated. The vault was a reference library; now it's a living operations center that evolves with every campaign, every analysis, every interaction.

### Part 3: Setting Up Hermes — Onboarding Your Agent Into the Vault (40 min)

**Live walkthrough — students follow along on their machines, connecting Hermes to their actual Week 2 vault:**

1. **Installation & provider setup** (10 min)
   - Install Hermes (`pip install hermes-agent`)
   - Configure Claude as the reasoning engine (API key setup)
   - First run: chat with the agent — give it a real marketing task ("What do you know about my brand?" — it knows nothing yet, because it hasn't been pointed at the vault. Shows why vault integration is everything.)

2. **Connecting Hermes to your Week 2 vault — the critical setup step** (15 min)
   - **The vault path configuration:** Set your Obsidian vault path as a Hermes filesystem root. Hermes can now see every `.md` file in your vault as a readable/writeable document.
   - **Vault index as agent entry point:** Hermes reads your vault's `index.md` (which links to every section). This becomes the agent's table of contents for your brand knowledge.
   - **Brand memory = vault section reads:** Instead of manually uploading context, Hermes is configured to read specific vault folders on boot:
     - `brand-context-vault/01-voice/` → brand voice guidelines
     - `brand-context-vault/02-personas/` → buyer personas
     - `brand-context-vault/03-competitive/` → competitive intelligence
     - `brand-context-vault/05-campaigns/` → campaign histories
     - `brand-context-vault/06-messaging/` → messaging hierarchy
   - **honcho.dev setup for session persistence:** Configure honcho.dev with your API key. Now Hermes remembers your conversation context between sessions — that Q4 campaign you started planning yesterday? Hermes remembers where you left off.
   - **Verification:** Ask "Hermes, what's our brand voice and who are our key personas?" — it should answer from your vault files, not guess. Ask "What's our competitive positioning against Competitor A?" — it reads the competitor intel section of your vault.

3. **Building 3 skills that use the vault as context source** (15 min)
   Skills are plain markdown files — editable, shareable, version-controllable. Each skill below explicitly references vault assets as its context source and vault folders as its output destination.

   - **Skill 1: Competitive Analysis Brief (Vault-Fed)**
     Trigger: "Run competitive analysis on [company]"
     Context source: Reads `brand-context-vault/03-competitive/` for existing intelligence on this competitor → doesn't duplicate what you already know
     Procedure: Web search company → read landing page + latest blog/press → Claude writes structured competitive brief (positioning, strengths, weaknesses, messaging gaps, recommended counter-positioning)
     Vault write-back: Saves result to `brand-context-vault/03-competitive/[company]-analysis.md` as a new vault note with frontmatter (type: competitor-analysis, date, status: draft) — Obsidian graph view now links this new note into your knowledge graph
     *Marketing use case:* Before a quarterly strategy meeting, brief the team on everyone in the landscape — and every brief enriches the vault for the next time.

   - **Skill 2: Content Brief Generator (Vault-Persona-Aware)**
     Trigger: "Create content brief for [topic/product] targeting [persona]"
     Context source: Reads `brand-context-vault/02-personas/[persona-name].md` for pain points, channel preferences, and buying triggers — plus `brand-context-vault/04-product/` for accurate product specs
     Procedure: Research topic (web search) → Claude writes positioning, messaging hierarchy, channel-specific asset briefs, SEO keywords, and success metrics — all referencing the vault persona as the audience anchor
     Vault write-back: Saves to `brand-context-vault/content-briefs/[topic]-brief.md` with links to the persona doc and product specs it used
     *Marketing use case:* A freelance writer needs a brief. The brief arrives with the persona's actual pain points and buying triggers — from the vault — not generic "our target audience is CTOs."

   - **Skill 3: Campaign Retrospective (Vault-Writing)**
     Trigger: "Run retro on [campaign name/period]"
     Context source: Reads `brand-context-vault/05-campaigns/` for the campaign launch record, plus `brand-context-vault/06-messaging/` for the messaging hierarchy that was used
     Procedure: Pull campaign data from specified source (n8n workflow that fetches ad platform data, or a Google Sheet with campaign KPIs) → Claude analyzes performance vs. goals, identifies what drove results, surfaces anomalies, writes action recommendations
     Vault write-back: Saves the full retro as `brand-context-vault/05-campaigns/[campaign]-retro.md` with YAML frontmatter (type: retro, campaign: [name], date, status: complete, key-insight: "video outperformed blog 3:1") — the vault now has a permanent, queryable campaign history
     *Marketing use case:* Post-campaign debrief that produces action items AND enriches the vault for future campaign planning. Next time you brief a campaign, the vault has richer history for the agent to reference.

4. **Multi-platform delivery — the vault agent everywhere** (5 min)
   - **Connect Hermes to Slack:** Marketing team posts "Hermes, check our competitive intel in the vault and brief us on Competitor B" in #marketing-research → Hermes reads `brand-context-vault/03-competitive/competitor-B.md` → summarizes with latest web research → posts structured brief. Team discusses without leaving Slack — and the vault is the source of truth.
   - **Connect Hermes to email:** Forward a competitor's press release to hermes@yourdomain.com → Hermes reads the vault's competitive intel section → cross-references what you already knew → writes a competitive response brief → saves it as a new vault note → replies with a summary. The brief is in your vault before you finish reading the press release.

### Part 4: Hermes + n8n — Both Sharing the Same Vault (30 min)

- **The vault is the shared context between Hermes and n8n:** Hermes and n8n both read from and write to the same vault. This is the architecture that ties everything together:

  ```
          ┌─────────────────────────┐
          │  Brand Context Vault    │
          │  (Obsidian .md files)   │
          └──────┬──────────┬───────┘
                 │          │
           Reads/Writes  Reads/Writes
                 │          │
          ┌──────▼──┐  ┌───▼────────┐
          │ Hermes  │  │    n8n     │
          │ (Agent) │  │ (Workflow) │
          └─────────┘  └────────────┘
  ```

- **Pattern 1: n8n writes to vault → Hermes reacts to vault changes:**
  - n8n completes a lead enrichment workflow → writes findings to `brand-context-vault/02-personas/lead-patterns.md`
  - Hermes (watching vault changes or triggered by you) notices the new lead patterns → offers: "I see new lead enrichment data in the vault. 80% match the CTO persona but only 30% convert. Want me to analyze and update the persona doc with this insight?"
  - *The vault is the shared journal — both tools leave notes for each other.*

- **Pattern 2: Hermes decides → n8n executes multi-tool response → writes result to vault:**
  - Hermes is running a competitive monitoring skill. It finds a major competitor launch.
  - It reads the vault's competitive intel to understand your position vs. this competitor.
  - Hermes decides: "This needs immediate action." It calls an n8n webhook.
  - n8n workflow runs: creates Asana task, posts Slack alert to #war-room, drafts CMO briefing email, schedules team huddle.
  - **n8n workflow also writes to vault:** Creates a new note `brand-context-vault/03-competitive/competitor-X-launch-response.md` with the n8n-generated response actions, linked back to the existing competitor doc.
  - Hermes reads that vault note on next startup and knows the response is already in motion.

- **Pattern 3: The vault as the handoff protocol:**
  - You hand a task to n8n (scheduled campaign report) → n8n writes the report to the vault
  - You hand a task to Hermes (analyze the week's data) → Hermes reads the vault note n8n created, analyzes it, writes findings back
  - Neither tool needs to talk directly — they communicate through the vault. This is the most resilient integration pattern: even if one tool is down, the vault preserves the data.

- **Live demo — Vault-mediated campaign response:**
  Campaign scenario: A competitor launches a new feature.
  1. Hermes (monitoring skill) detects new product announcement via RSS/blog monitoring
  2. Hermes reads `brand-context-vault/03-competitive/[competitor].md` to understand your current positioning against them
  3. Hermes researches the new feature → writes initial analysis to `brand-context-vault/03-competitive/[competitor]-new-feature-threat.md` — the vault is updated immediately
  4. Hermes decides: "This is significant — escalate" and calls n8n webhook
  5. n8n workflow reads Hermes' vault note for context → creates Asana task, Slack alert, briefing email
  6. n8n writes to vault: appends `response-actions.md` with the actions taken, backlinks to the threat analysis
  7. Your vault now has a complete, linked record: threat detected → analysis → response actions — all in one graph

- **Decision framework — when Hermes handles vs. n8n handles (with vault in mind):**

| Scenario | Handle In | Vault Role |
|----------|-----------|------------|
| Post draft to social on schedule | n8n | n8n reads vault voice guide for tone, writes post-log to vault |
| What angle should this social post take? | Hermes | Hermes reads vault personas + campaign history for context |
| Should I update the persona doc? | Hermes | Hermes analyzes lead data, writes updated persona to vault |
| Build weekly report from ad data | n8n | n8n aggregates data, writes raw report to vault |
| What story does this week's data tell? | Hermes | Hermes reads n8n's vault report, adds strategic analysis |
| Detect stale vault content | Hermes | Hermes scans vault frontmatter, flags outdated entries |

### Part 5: Compressed — Multi-Agent Orchestration & Production (30 min)

**Orchestration — When One Vault-Living Agent Isn't Enough**
- **The vault scales to multiple agents:** Each agent reads the same vault but specializes in different sections. A research agent focuses on `03-competitive/` and `05-campaigns/`. A content agent focuses on `01-voice/`, `02-personas/`, and `06-messaging/`. All share the same vault as their source of truth — no context fragmentation.
- **The pattern — agents sharing a vault:**
  1. **Monitoring Agent:** Watches competitor blogs, press releases — flags moves and writes raw intelligence to `brand-context-vault/03-competitive/intelligence-flags/`
  2. **Research Agent:** Monitors the flags folder → reads new intelligence → deep-dives → produces structured brief → writes to `03-competitive/` as a proper competitor doc
  3. **Content Agent:** Reads the new competitor doc → drafts response assets → writes drafts to `brand-context-vault/content-drafts/`
  4. **Distribution Agent:** Takes approved content from vault → calls n8n workflows → schedules across channels → logs performance to `brand-context-vault/05-campaigns/`
  5. **Manager Agent:** Monitors all vault sections, flags stale content, identifies coverage gaps in the vault
- **Marketing analogy:** This is a marketing team sharing one shared drive (the vault). Each person has their focus area but everything is in one place, connected, searchable.

**Production — Keeping Your Vault Healthy**
- **Vault reliability:** Your vault is markdown files — they don't go down. Even if Hermes or n8n is offline, your vault is intact. This is the resilience of a file-based knowledge base.
- **Vault maintenance via Hermes:** Create a skill "vault-health-check" that scans every note's `last_updated` frontmatter and flags anything over 90 days without an update. "Flagging 3 persona docs and 2 competitor docs as potentially stale — review these vault entries."
- **Cost management for marketing budgets:**
  - The vault reads are free (local filesystem). Only Claude API calls cost tokens.
  - Model tiering by task: Haiku for vault-maintenance tasks (scanning frontmatter, flagging stale content), Sonnet for content generation against vault context, Opus for strategic analysis against the full vault knowledge base
- **Security — the vault model is inherently safer:** Your vault lives on your machine. Hermes reads it locally. n8n reads it locally. No third-party cloud stores your brand context. You choose what flows through external APIs (only the Claude API calls with selected context slices).

### Part 6: Live Build — Brand Intelligence Agent, Pre-Loaded with Your Vault (60 min)

Students build their own production-ready marketing agent that lives in their Week 2 vault.

1. **Deploy** — Hermes instance running with Claude as the brain, vault path configured

2. **Configure brand memory (from the vault, not from scratch):**
   Instead of manually typing brand info, Hermes reads directly from the vault:
   - `brand-context-vault/index.md` → the agent's table of contents for your brand
   - `brand-context-vault/01-voice/brand-voice-guide.md` → voice guidelines
   - `brand-context-vault/02-personas/persona-cto.md` → primary persona
   - `brand-context-vault/02-personas/persona-vp-marketing.md` → secondary persona
   - `brand-context-vault/03-competitive/` → competitive landscape
   - `brand-context-vault/05-campaigns/` → campaign history and learnings
   - `brand-context-vault/06-messaging/do-not-says.md` → banned language
   - **Verification:** Ask "Hermes, what's in my brand vault?" — it should list the vault structure. Ask "What did I learn from my last campaign?" — it reads the campaign retro from the vault.

3. **Set up honcho.dev for session persistence:**
   - Configure honcho.dev API key
   - Start a conversation: "We're planning a Q4 ABM campaign targeting the CTO persona. Let's start with competitive positioning."
   - Close Hermes. Reopen. Ask: "Continue where we left off on the Q4 campaign." Hermes remembers via honcho.dev — and has the vault context ready from the filesystem.

4. **Build 3 skills that use the vault as context source and output destination:**
   - **Skill 1: Competitive Analysis Brief** — reads vault competitive Intel section first, then web researches, writes result as a new vault note
   - **Skill 2: Content Brief Generator** — reads vault persona doc + product specs, generates brief, saves to vault content-briefs folder
   - **Skill 3: Campaign Retrospective** — pulls performance data, reads vault campaign launch record, writes retro to vault campaigns folder with frontmatter

5. **Connect the Week 3 vault-backed n8n workflow:**
   - The lead enrichment pipeline from Week 3 (Workflow 2) writes persona-match data to the vault
   - Hermes detects the new lead-patterns.md in the vault → offers: "I see new lead patterns. Want me to analyze and update the persona doc?"
   - This demonstrates the vault as shared context: n8n writes → Hermes reads → Hermes enriches → writes back → n8n reads the enriched vault on next execution

6. **Test with a real scenario — the vault arc complete:**
   **"Analyze our main competitor's latest product launch. Reference what we already know in the vault. Write a brief. Save it to the vault."**
   - Instructor demonstrates: Hermes reads `brand-context-vault/03-competitive/[competitor].md` → sees what you already know → web researches for updates → Claude writes brief → saves to `brand-context-vault/03-competitive/[competitor]-updated-analysis.md`
   - Students run it on their own agent with their own vault and competitor
   - Debrief: The output is better because the vault prevented the agent from re-researching what you already knew. The vault is the agent's memory — the agent starts with knowledge, not a blank state.

**Deliverable:** A live **Brand Intelligence Agent** — pre-loaded with your Week 2 vault, configured to read vault context for every task, write outputs back as new vault notes, and maintain session memory via honcho.dev. The vault is no longer a static reference — it's the agent's permanent home. Students leave with a working AI team member that already knows their entire brand context because it lives in the vault.

---

## Course Arc Summary

```
Week 1: Foundations     → "I understand the AI stack — LLMs, APIs, webhooks, agents — 
                           and can map my marketing ops against it"
Week 2: Claude           → "I can build brand context vaults that feed my agents,
                           making context engineering my superpower"
Week 3: n8n              → "I can build workflows that read brand context FROM my vault 
                           and write campaign results TO my vault — the vault is my 
                           automation hub"
Week 4: Hermes Agent     → "I have an AI agent that LIVES in my brand vault — it wakes 
                           up every day knowing my voice, personas, and campaigns, and 
                           writes its outputs back into the vault. The vault is its home"
```

## What the Student Walks Away With

| Week | Tangible Deliverable |
|------|---------------------|
| 1 | **Automation Readiness Map** — their entire marketing workload mapped against the AI stack with prioritized next steps |
| 2 | **Brand Context Vault** — structured knowledge base (voice guide, personas, do-not-says) feeding Claude and agents — grows smarter every campaign |
| 3 | **Vault-Backed Campaign Distribution Pipeline** — n8n workflow that reads brand context FROM your Week 2 vault, generates channel-specific content in your brand's voice, publishes to LinkedIn + Twitter + email, and writes campaign records back to the vault |
| 4 | **Brand Intelligence Agent** — live Hermes instance that lives in your Week 2 vault, reads brand context for every task, writes outputs back as new vault notes, and maintains session memory via honcho.dev. The vault is its permanent home |

### Knowledge Evolution

| Before | After |
|--------|-------|
| "AI" is a black box | Can explain what an LLM, API, webhook, and agent actually are |
| Uses ChatGPT for ad-hoc tasks | Has a persistent agent that lives in the brand vault — reads vault context, writes outputs back, remembers sessions |
| Manual handoffs between tools | End-to-end automated workflows connecting 200+ tools |
| Doesn't know what tools exist | Knows exactly which layer (chat, workflow, agent, orchestration) for which job |
| Depends on engineering for automation | Can build and deploy their own automation independently |
| No framework for evaluating AI | Clear decision criteria rooted in actual capabilities |

---

## Tool Coverage Summary

| Tool | Weeks | What the Student Can Do After |
|------|-------|-------------------------------|
| **LLM concepts** | 1, throughout | Explain what a model, API, webhook, token, and agent are — to stakeholders and vendors |
|| **Claude** | 2, 3, 4 | Build structured brand context vaults that give agents rich brand awareness; produce marketing content that sounds like your brand, not a generic AI |
| **n8n** | 3, 4 | Build production-grade marketing workflows that read brand context FROM the Week 2 vault, inject it into AI prompts, and write campaign results back TO the vault as structured notes |
| **Hermes Agent** | 4 | Deploy autonomous agents that live in the Week 2 vault — read vault context as their permanent memory, write outputs back as vault notes, and maintain session persistence via honcho.dev |
| **Orchestration** | 4 (compressed) | Understand multi-agent patterns for when workloads outgrow a single agent |
| **Production ops** | 4 (compressed) | Manage costs, reliability, security, and team rollout |

---

## Logistics

### Each Session's Structure (3 hours)

| Segment | Duration | What |
|---------|----------|------|
| Check-in & homework review | 15 min | What worked, what broke, questions |
| New concepts & demos | 60 min | Foundations first, then tools |
| Guided build / workshop | 60 min | Students build alongside instructor |
| Deliverable wrap | 30 min | Finalize, save, test the week's artifact |
| Homework & preview | 15 min | What to install/prepare for next week |

### Prerequisites for Students (Week 1)
- Laptop with internet
- A real marketing problem they want to solve
- Willingness to install software (Docker, Python)
- A Google account (for Google Sheets/docs integrations in demos)
- Claude.ai account by Week 2

### What's NOT Covered (Intentionally)
- Writing code from scratch (we use GUI tools + templates)
- Training/fine-tuning models (not needed for 99% of marketing use cases)
- Building AI from the ground up
- Vendor evaluation frameworks (we focus on open-source + accessible tools)
- Prompt injection security or adversarial attacks
