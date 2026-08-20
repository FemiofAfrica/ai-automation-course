# AI Automation for Marketing Executives - 4-Week Live Course Outline

**Course Title:** AI Automation for Marketing: From Ground Zero to Autonomous Operations
**Target Audience:** Marketing executives & senior marketing leaders
**Delivery Style:** Practical, hands-on, zero fluff. Every session starts from fundamentals, ends with a working deliverable.
**Format:** 4 live sessions × ~3 hours each (one per week)
**Prerequisites:** None technical. Must be honest about what you don't know. Must have real marketing operations pain points to apply the learning to.
**Max Cohort:** 6–8 students (to allow live Q&A and troubleshooting)

---

## Why This Course Exists (Updated)

Marketing executives are drowning in AI hype. Everyone's selling "AI-powered marketing" but nobody is explaining what an LLM actually is, what an API does, or why a webhook isn't a fish. The gap between *having AI tools* and *running AI-powered marketing operations* starts with a basic vocabulary gap - and this course fills it from the ground up.

This is not a theory course. Every week ends with a working artifact the student can use Monday morning. But we don't skip fundamentals just because they're simple. We explain them first, then we build.

---

## Week 1: Foundations of AI Automation - What You're Actually Working With

**Session Length:** ~3 hours
**Objective:** By the end of this session, the student understands exactly what every AI term means, how the pieces fit together, and can look at any marketing task and map it to the right automation approach - without relying on vendor marketing.

### Part 1: The Vocabulary Every Marketing Exec Needs (60 min)

**1.1 What Is a Model?**
- Plain English: a model is a pattern-recognition machine trained on data. It doesn't "think" - it predicts the next most likely word/pixel/action based on what it's seen before.
- Analogy: Like a new hire who's read the entire internet. Brilliant but needs clear instructions, has no context on your brand yet, and can hallucinate confidently.
- Model types relevant to marketing: text models (Claude, GPT), image models (DALL-E, Midjourney), embedding models (for search/similarity).

**1.2 What Is an LLM?**
- Large Language Model = a text model scaled up enough to hold conversations, follow instructions, and generate coherent long-form content.
- Key properties: context window (how much it can "see" at once), token limits, temperature (creativity vs. precision).
- Demo: The same prompt, different models (Claude vs. GPT vs. Gemini) - show how output quality varies.
- No jargon hand-waving. Show the token counter. Show a context window overflow. Make it tangible.

**1.3 What Is an API?**
- Plain English: an API is a waiter. You give it an order (structured request), it brings back what the kitchen (the model/service) made.
- Why it matters for marketers: APIs let one tool talk to another. Claude Code lets your marketing stack *programmatically* generate content, and workflow tools use APIs to connect 200+ tools.
- Analogy: APIs are the difference between copying data manually between spreadsheets and having Google Sheets auto-sync with your CRM.
- Show a real API call (curl or an HTTP node), simple, visual, no code required to understand.

**1.4 What Is a Webhook?**
- Plain English: a webhook is a phone that rings when something happens. "When a new lead fills out the form, call this URL and tell it the lead details."
- Analogy: An API is "go get data from this place." A webhook is "call me when something happens." Pull vs. push.
- Marketing examples: form submission → webhook triggers Claude Code → enriches lead → Slack notification.
- Live demo: Show a webhook in action (form submit → Claude Code receives it → logs it). Students see the trigger happen in real time.

**1.5 What Is an AI Agent / Agent Harness?**
- Plain English: an AI agent is an LLM with tools, memory, and autonomy. It doesn't just answer one question - it can be given a goal ("monitor competitors and brief me weekly") and execute multi-step work independently, using tools (web search, APIs, file system) along the way.
- Analogy: Claude.ai is a brilliant intern you have to hand-hold with every prompt. A harness is that same intern, after 6 months, who knows your brand, works without supervision, and tells you when something needs your attention.
- Agent harness: the software that wraps the LLM with tools, memory, skills, and multi-platform delivery.
- Key distinction: Chat UI (Claude.ai, ChatGPT) vs. Agent (persistent, autonomous, tool-using).

**Quick Vocabulary Quiz:** 5 scenarios, students identify which concept applies. Low stakes, high retention.

### Part 2: The Input-to-Output Pipeline - How AI Agents Actually Work (20 min)

**The Big Picture - Why This Matters Before Anything Else:**

Before we talk about tools, workflows, or automation layers, you need to understand one thing: the architecture is the same every time. Whether you're using Claude.ai for a single task or a multi-agent system running 24/7 - the input-to-output pipeline is identical. Every week of this course teaches you how to optimize one part of this pipeline.

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
| **① You give input** | You say: "Write a LinkedIn post about the new analytics dashboard" | The prompt - your instruction to the agent |
| **② Gather context** | Analyst opens the brand book, persona guide, and product specs on their desk | Agent loads brand vault docs, project files, reference material |
| **③ Search memory** | Analyst remembers: "Last time we launched a feature, the CTO persona responded best to 'time saved' messaging" | Agent searches session history + persistent memory for relevant past learnings |
| **④ Use tools/skills/MCP** | Analyst opens LinkedIn, checks character limits, pulls the analytics dashboard screenshot from Google Drive | Agent runs a skill (LinkedIn post format), calls MCP tools (Google Drive, image analyzer, web search) |
| **⑤ All flows to LLM** | Analyst sits down with all gathered material - brand guide, past notes, tool outputs - and starts writing | Everything - context, memory, tool results - is packed into the LLM's input context window |
| **⑥ Model produces output** | Analyst hands back a finished post | The LLM generates the response - text, JSON, action, or decision |

**Why This Pipeline Is the Skeleton of the Entire Course:**

Every week of this course teaches you how to make one part of this pipeline more powerful:

| Course Week | What You Learn | Which Pipeline Step It Optimizes |
|---|---|---|
| **Week 1 (today)** | The vocabulary + this pipeline | Understanding the whole flow |
| **Week 2: Context Engineering** | Building your brand vault, voice guides, persona docs, campaign histories | **Step ②** - giving the agent richer context so it produces better output |
| **Week 3: The Marketing Harness** | Claude Code reading your vault, pulling Meta data through Composio, delivering a weekly report | **Steps ② + ④ + ⑧** - context, tools, and a durable trigger |
| **Week 4: The Operating System** | Hardening the harness: more skills, memory across runs, failure alerts | **Steps ③ + ④ + ⑦** - memory, skills, and state |

**Key Insight:** A better prompt helps Step ①. A richer brand vault helps Step ②. Persistent memory helps Step ③. Powerful tools and skills help Step ④. A smarter model helps Step ⑥. **The best automation systems improve ALL steps** - not just one.

**Quick Comprehension Check (2 min):**
- "I spent 10 minutes writing the perfect prompt but Claude still produced generic copy" - which pipeline step is weak? (Answer: Step ② - the agent lacked brand context)
- "My agent gives good output but can't actually send the email or post to social" - which step is weak? (Answer: Step ④ - no tools connected)
- "Every session I have to re-explain who our target audience is" - which step is weak? (Answer: Step ③ - memory isn't persisting between sessions)

**The Takeaway:** Every time you interact with an AI agent - whether it's Claude.ai, ChatGPT, or your own harness - this pipeline is running behind the scenes. Understanding it means you can diagnose *why* an output is weak and know exactly *which lever* to pull to fix it. That's what the rest of this course teaches.

### Part 3: The Four-Layer Automation Stack (40 min)

1. **Chat & Reasoning** (Claude.ai, ChatGPT) - ad-hoc analysis, drafting, brainstorming
2. **Workflow Automation** (Claude Code + skills) - connecting your tools end-to-end, no code for the marketer
3. **Autonomous Agents** (Claude Code scheduled, or a hosted agent) - persistent AI assistants that learn, remember, and execute
4. **Orchestration** (multi-agent systems) - coordinating multiple AI agents working together

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

## Week 2: Claude & Context Engineering - Giving Your AI the Right Brand Context

**Session Length:** ~3 hours
**Objective:** Understand the 2026 paradigm shift - capable models shift the leverage away from wording prompts. The higher-leverage skill is now **context engineering**: building knowledge bases (brand vaults, memory stores, knowledge graphs) that give agents rich brand context so they do their best work without needing perfectly crafted prompts.

**Why this shift matters:** In 2025, marketers needed intricate prompt templates - persona blocks, few-shot examples, chain-of-thought instructions - to get good output from even the best models. By 2026, models like Claude Opus 5 and Fable 5 are capable enough that the bottleneck has moved. The question is no longer "How do I phrase this prompt?" but "Does my agent have the brand context it needs to make good decisions?" A great model with thin context produces generic output. A capable model with rich context produces work that feels like your brand.

**Strictly marketing framing:** This entire session is delivered through the lens of a marketing executive who needs her AI to *already know* her brand, audience, campaign history, and competitive positioning - so every interaction is informed, on-brand, and context-aware from the first message.

### Part 1: Refresher + The Context Shift (15 min)
- Quick recap: what an LLM is and how Claude fits into a marketing stack
- **The 2026 shift: Context > Prompting:**
  - Models today (Claude Opus 5, Fable 5) are intelligent enough to do brilliant work - if you give them the right context to work with
  - Analogy: You don't give a world-class chef a recipe. You stock the kitchen with your ingredients, tell them your taste, and let them cook. The chef is good enough; the secret is the pantry.
  - Prompt engineering still matters, and clear instructions still help. What changed is where the leverage sits: with capable models, building rich knowledge environments beats re-wording requests. Anthropic frames context engineering as the natural progression of prompt engineering.
  - Real test: A great prompt on a model with no brand context produces better output than a mediocre prompt - but a capable model with a full brand vault produces output indistinguishable from your senior copywriter.
- Claude's strengths in a context-engineering world:
  - Claude's 200K context window: big enough to hold your entire brand context vault in a single session
  - Claude excels at structured outputs (tables, JSON, markdown) - your brand vault feeds structured data, Claude returns structured content
  - Claude's Artifacts: living documents that reference your brand vault as their source of truth
- The model lineup for marketing use (current as of July 2026) - choosing the right brain for your context:
  - **Claude Haiku 4.5** (fastest, near-frontier): bulk product descriptions, social post variants, A/B subject lines - tasks where speed × volume matters, fed by a slim context slice
  - **Claude Sonnet 5** (balanced daily driver): campaign briefs, competitive analyses, ad copy, email nurture sequences - the standard marketing work, needs a solid context vault
  - **Claude Opus 5** (enterprise): complex analysis, high-stakes messaging, positioning review, strategy - needs your fullest brand context to do its best work
  - **Claude Fable 5** (highest capability): multi-step research agents, competitive intelligence, brand strategy - the top tier, and the one that benefits most from a deep, rich context vault
- **Marketing decision framework:** "For a Q3 product launch with 40 assets across 6 channels, which Claude model do you feed which slice of your brand vault?"

### Part 2: Context Engineering for Marketing (50 min)
**2.1 The Shift: Why Context Engineering Is the Higher-Leverage Skill**
- **The old way:** Spend 15 minutes crafting the perfect persona block, few-shot examples, and constraint list. Re-engineering prompts per task. Maintaining a library of 50 prompt templates. Every new campaign starts from scratch.
- **The 2026 way:** Spend 15 minutes building a reusable brand context asset (buyer persona doc, voice guide, campaign retro). Point the model at it. Let the model do its job without you crafting a long prompt each time.
- **What changed:** Models in 2025 needed hand-holding - chain-of-thought, explicit reasoning instructions, heavily engineered prompts. Models in 2026 are capable enough that the work goes into **what you tell them, not how you tell them.**
- **The new skill stack for marketers:**
  1. **Knowledge curation** - what brand context you capture (voice, personas, competitive intel, history)
  2. **Knowledge structuring** - how you format it so agents can consume it (structured docs, linked notes, schemas)
  3. **Knowledge accessibility** - how the agent finds the right context at the right time (memory systems, project files, retrieval)
  4. **Knowledge maintenance** - keeping the vault alive as your brand evolves
- **The ROI reframe:** Every hour you invest in building your brand context vault saves hours of future prompt rewriting. Context is a compounding asset; prompt libraries are disposable.

**2.2 Building Your Brand Context Vault - What Goes In**
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

**2.3 Tools for Context Management - Your Brand Vault Stack**
- **Obsidian - The Brand Context Vault Foundation:**
  - Markdown-based, local-first, infinitely linkable
  - Each context asset is a markdown note: `Brand Voice.md`, `Persona - CTO.md`, `Competitor - Salesforce.md`
  - Links between notes create a knowledge graph: a persona note links to the campaign history notes where that persona was targeted, which link to the A/B test results from that campaign
  - Tags organize by type (`#persona`, `#campaign`, `#voice`, `#competitor`), channel (`#linkedin`, `#email`, `#blog`), and status (`#active`, `#archive`, `#draft`)
  - Graph view: see how your brand knowledge connects - visual proof of gaps ("I have personas but no content examples for this segment")
  - Community plugins: Dataview (query your vault), Templater (context templates), Omnisearch (find context fast)
  - **Live demo:** Open an Obsidian vault with a real agency brand - show the knowledge graph, click through linked persona → campaign → performance notes. Show the student what "brand memory" looks like as a file system.
- **GBrain - Knowledge Graphs for Relational Context:**
  - Visual knowledge graphs that show how brand concepts connect: "This campaign reached Persona A through LinkedIn, using Message Theme B, with 3.2x ROAS"
  - Better than folders for understanding relationships between brand assets
  - Useful for agencies managing multiple brands - each brand as a separate graph, no cross-contamination
  - Why it matters for agents: agents can traverse graph relationships ("Find all campaigns targeting Persona A that performed above benchmark") without being explicitly told the connections
- **honcho.dev - Persistent Session Memory for Agents:**
  - The missing piece: agents that remember who you are and what you've been working on - across conversations
  - honcho.dev provides persistent memory for agents: you tell your agent something once ("I'm focusing on ABM for fintech this quarter"), it remembers in the next session
  - How it complements the context vault: the vault is the reference library (stable, curated, versioned). Honcho is the ongoing conversation memory (dynamic, session-to-session, ephemeral context)
  - **Marketing use case:** You start working on a Q3 product launch campaign in Week 1. In Week 2, you ask your agent "What messaging did we decide for the healthcare vertical?" - Honcho remembers the discussion, your vault stores the finalized messaging hierarchy. Together, nothing falls through the cracks.
  - **Real scenario:** A marketing director briefs the agent on Monday about next quarter's event strategy. On Wednesday, they ask "Remind me what we decided about the speaking slot vs. booth debate" - the agent remembers, even though it's been 48 hours and 15 other conversations.

**2.4 Structuring Brand Information So Agents Can Actually Use It**
Not all brand information is equally agent-usable. The key is structure that models can parse reliably.

- **The Context Template - a standard format for every vault entry:**
  ```markdown
  ---
  title: Brand Voice Guide
  type: voice
  status: active
  tags: [voice, foundation, evergreen]
  last_updated: 2026-07-15
  ---

  ## Voice Archetype
  "The trusted expert who's also human" - like a senior consultant who knows their stuff but doesn't talk down to you.

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
  - Use "you" and "your" - audience is the hero

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
  - YAML frontmatter lets agents filter by type, status, date - "only active buyer personas"
  - Tables are the most reliably parseable format for models - use them for comparisons, scales, and mappings
  - Consistent headings let Claude navigate without needing the full doc in context - it can section-search
  - Frontmatter `type` tags enable your agent to auto-select context: "I'm writing a blog post → load voice guide + relevant persona + tone scale for blogs"

- **From prompt library to context vault - what changes:**
  - Prompt library is procedural: "When writing ad copy, follow this 5-step structure." Each prompt is an instruction.
  - Context vault is declarative: "Here's who we are, who we talk to, what we believe, and what we've learned." The agent figures out how to use it.
  - The prompt library needed updating as models changed. The context vault is model-agnostic - it stays valuable regardless of which AI you use.
  - A context vault can feed Claude, GPT, Gemma, Grok, or your own harness - it's portable knowledge, not fragile instructions.

### Part 3: Claude with Rich Context - What Changes in Practice (35 min)
**3.1 Before/After Demo - Same Task, With and Without Context**
**Scenario:** "Write a LinkedIn post announcing our new integration with Salesforce."
**Without context vault (the old way):** The student spends 10 minutes crafting a prompt with persona blocks, tone instructions, audience definitions, and constraint lists. Output is decent - but sounds like every other AI-generated LinkedIn post. Generic.
**With context vault (the new way):** The student opens their Claude Project configured with the brand context vault. Claude already knows:
- Brand voice: authoritative but warm, avoid hype words, use "customers" not "users"
- Target persona: CTO of mid-market SaaS companies - cares about integration ease, data privacy, time-to-value
- Product details: the integration syncs in 5 minutes with no code, supports BI-directional sync, field-level mapping
- Past campaign data: last integration launch (HubSpot) performed best with "practical value" messaging vs. "strategic partnership" messaging
- Competitive intel: Salesforce ecosystem is crowded - positioning must emphasize ease of setup vs. competitors' 2-week implementation
- Do-not-says: "seamless" (overused), "enterprise-grade" (meaningless), named competitors
**Result:** Claude generates a LinkedIn post that actually sounds like the brand, speaks directly to the right buyer, references real capabilities, and avoids well-worn clichés - in one shot, no prompt iteration. The student spent zero time engineering the prompt and 15 minutes (once) building the context vault.

**3.2 Claude Projects as Your Agent's Brand Workspace**
- **Projects aren't just prompt libraries - they're context containers:**
  - Upload your entire brand context vault (all the docs from 2.2) to a Claude Project
  - Every chat in that project starts with Claude already knowing your brand, personas, competitors, and campaign history
  - Custom instructions become the permanent context layer: "Use the Brand Voice Guide from the project files as your voice reference. When asked about a persona, reference the relevant persona doc. When generating competitive content, reference the competitor docs."
- **The difference:** In 2025, custom instructions were a prompt - "You are a senior marketer who writes for CTOs." In 2026, custom instructions are a librarian - "Reference these context files to understand who we are and who we're talking to."
- **Artifacts** become living documents that the whole team edits - built on top of the context vault's truth

**3.3 Claude's 200K Context - Your Entire Brand Vault, One Upload**
- The 200K context window fits an entire brand context vault (~50–100 well-structured markdown notes) in a single session
- **Practical workflow:** Your Obsidian vault (or folder of markdown files) → export as a single markdown file → upload to Claude project → Claude reads your entire brand knowledge base
- This means: no more "please wait while I upload five documents" - your agent has permanent access to your full brand context
- **Demo:** Drag a student's completed context vault into a Claude project → ask Claude "What's our brand voice on pricing?" → Claude finds the relevant section in the vault and answers from the source of truth → ask "Who are we targeting for the Q4 product launch?" → Claude cross-references personas and campaign history from the vault

**3.4 The Decision Framework - When You Need More Context, Not a Better Prompt**
| Symptom | Old Diagnosis | New Diagnosis | Fix |
|---|---|---|---|
| Output is too generic | "My prompt needs better persona work" | "The model doesn't have enough brand context" | Add brand voice guide + persona docs to vault |
| Output misses audience nuance | "I need more few-shot examples" | "Needs the buyer persona doc with pain points and triggers" | Curate a richer persona doc |
| Output feels off-brand | "Tone instructions aren't specific enough" | "The do-say/don't-say tables aren't complete enough" | Add more exemplars and edge cases |
| Output is factually wrong about product | "Prompt should include product specs" | "Product info isn't in the context vault" | Add product spec doc to vault |
| Output doesn't learn from past mistakes | "I keep having to say the same things" | "Campaign history isn't surfaced to the model" | Add campaign post-mortems to vault |
| Takes 5 iterations to get it right | "I need to refine my prompt technique" | "Context vault needs richer examples and edge cases" | Feed back your corrections into the vault |

**Key insight for marketers:** Every time you find yourself correcting an AI's output, that correction is **new context you should add to your vault**, not a better prompt to write. Corrections are data. The vault gets smarter every time you use it.

### Part 4: Beyond the Chat UI - The API Layer (25 min)
- **What the API enables that chat can't for marketing:**
  - Batch generate 200 localized ad variants in 3 minutes - each variant drawing from a different persona context slice
  - Embed Claude inside your campaign automation (Claude Code reads the vault, calls Composio for live data)
  - Programmatic context switching: same brief, different persona context → Claude produces 5 variations for 5 segments
- Conceptual walkthrough: "Here's what happens when Claude Code calls Composio with your brand vault as reference" - no code, just the request/response cycle visualized
- **Cost model for marketing execs:** "Generating 50 personalized email sequences per day costs ~$X in tokens. Compare that to a copywriter - and remember, with a context vault, each email is on-brand on the first generation, not the fifth revision."
- **Decision framework - which Claude interface for which marketing job:**
  | Marketing Task | Use This | Why |
  |---|---|---|
  | Draft one campaign brief with brand vault reference | Claude.ai Project | Vault-loaded, iterative, collaborative |
  | Generate 100 local landing pages from persona vault | Claude API via Claude Code | Programmatic, batch, per-segment context injection |
  | Analyze 50 customer transcripts against buyer personas | Claude.ai Project upload | Context window fits transcripts + vault |
  | Daily competitor monitoring brief | Claude Code scheduled | Persistent, scheduled, autonomous, vault-fed |

### Part 5: Live Build - Brand Context Vault (60 min)
Build a reusable brand context vault that feeds your AI agent - replacing the prompt library model. Delivered as an Obsidian vault (or structured markdown folder) + Claude Project configured with vault context.

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
2. **Write the Index** - a single note that links to every section with a description of what each contains. This becomes the agent's "table of contents" for your brand context.
3. **Fill the first 3 context assets** (guided by instructor):
   - **Brand Voice Guide** - using the structured template from 2.4 (tone scale, do-say/don't-say, vocabulary)
   - **One Buyer Persona** - the student's most important audience (structured: demographics, pain points, triggers, objections, channel preferences, quoted language)
   - **Do-Not-Says** - at least 5 things the agent should never say about the brand

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

   When I ask you who we are, reference the vault. When I ask you to write something, reference the vault. Do not guess - the vault is the source of truth.
   ```
4. **Verification test:** Ask Claude "Who are we and what's our brand voice?" - it should answer from the vault, not from training data.

**Phase 3: Test the Vault Against Real Scenarios (15 min)**
Students run 3 real marketing tasks against their vault-fed Claude project:
1. **"Write a LinkedIn post about our recent [product milestone / feature launch] targeting [persona from vault]. Reference our brand voice guide."**
2. **"Our competitor [name] just announced [feature]. Draft a competitive response brief using our positioning docs. Reference our do-not-says."**
3. **"We're running a campaign targeting [persona from vault] for [campaign type]. What messaging hierarchy from our vault should we use, and what past campaign data supports it?"**

**Phase 4: Feedback Loop - Corrections Become Context (10 min)**
- Review the outputs. Where was Claude off-brand? Where did it miss audience nuance?
- **The vault fix:** Instead of writing a better prompt, add the correction to the vault:
  - "It used 'leverage' - add 'leverage' to the do-not-says list"
  - "It missed the procurement team's price-sensitivity - add that to the persona doc"
  - "It sounded too formal for LinkedIn - add a more casual LinkedIn tone example to the voice guide"
- **Key insight:** Every correction is an investment in the vault. The next generation will be better because you enriched the context, not because you wrote a more clever prompt.

**Deliverable:** A **Brand Context Vault** - a structured knowledge base (Obsidian vault or markdown folder) with an Index, Brand Voice Guide, Buyer Persona, and Do-Not-Says, configured as a Claude Project with librarian-style custom instructions. Students leave with a system they can expand with every campaign, every persona, every competitive insight - reducing context setup from 15 minutes per task to zero.

### Homework for Week 3 (Prepares Your Vault for the Harness)
- Add 2 more context assets to your Brand Context Vault:
  - A second Buyer Persona (your next most important audience)
  - One Campaign Retro (any past campaign - what worked, what bombed, why)
- **Vault prep for Week 3:** Make sure your vault path is accessible and you know the exact folder structure (Claude Code will read these files directly). Ensure your vault has clear YAML frontmatter on each note (type, status, last_updated) - the harness filters on these.
- Bring your vault path written down, on the laptop you will use in class.
- Have an Instagram Business (or Creator) account linked to a Facebook Page, because Week 3 pulls live data from them through Composio.
- Install Claude Code before class (see the setup guide). No Docker, no Hermes.

---

## Week 3: The Marketing Intelligence Harness - Claude Code + Composio

**Session Length:** ~3 hours
**Objective:** Build a Claude Code marketing harness that reads your Week 2 Brand Context Vault, pulls real Instagram and Facebook data through Composio, creates a useful weekly insights report, saves the report back into the vault, and delivers it to you automatically every week.

> **Tooling note (revision of the earlier plan):** The original outline planned n8n as the Week 3 environment and Hermes Agent as Week 4. We have revised that. Week 3 uses **Claude Code** as the practical agent harness: it runs on the student's laptop, reads the vault as local files, and its skills system fits a weekly report cleanly. The student does **not** install Hermes. Week 4 hardens and expands this same harness rather than introducing a different product.

**The harness thread:** Every part of this session starts from your Week 2 brand vault as the source of truth. When the report needs to know your brand voice, it reads the vault. When it ranks posts, it explains what worked using the data. When it finishes, it writes the report into the vault's reports folder and logs the run. The vault is the hub, Claude Code is the worker, Composio is the hand on Meta.

**Strictly marketing framing:** This session never shows a generic "hello world" agent. Every build starts from a marketing problem rooted in the gap between having brand knowledge and using live performance data.

### Part 1: Readiness Gate and Vault Recovery (25 min, capped)
- Quick recap: the pipeline and where the harness sits (steps ②, ④, ⑧).
- **The gate (from Class 2 continuity):** confirm Claude Code can open the vault; confirm the vault has at least Index, Brand Voice, Buyer Persona, Product Facts, Do-Not-Says, and one Campaign Retro or Insights note; provide a copyable Claude Code repair prompt that creates only missing pieces without overwriting real content; run a quick context test showing Claude can answer a brand-specific question from the vault.
- Do not spend the full class repeating Class 2. Cap this recovery at 20 to 25 minutes.

### Part 2: The Harness Architecture (25 min)
- **Nine layers, one diagram:** model/brain, instructions (CLAUDE.md), context/vault, skills as reusable procedures, tools/MCP (Composio), permissions and approval boundaries, memory/state (run log), trigger/schedule, output/delivery.
- **One analogy:** the marketing deputy seated in your office, with a filing cabinet (vault), procedure binders (skills), a phone to Meta (tools), a keycard (permissions), a notebook (memory), an alarm clock (schedule), and a courier (delivery).
- **Diagnose by layer:** a table mapping symptoms (generic report, invented metrics, "no connected account", asks to post, runs once, never delivered, repeats a mistake) to the weak layer and the first fix.

### Part 3: Install Instructions and the Skill (25 min)
- **CLAUDE.md** at the vault root: the standing rules (treat the vault as source of truth, never invent metrics, save reports to reports/weekly/, append to run-log, do not post without explicit approval).
- **The skill** at `.claude/skills/weekly-marketing-insights/SKILL.md`: the exact procedure, with frontmatter `name`, `description`, and `allowed-tools` pre-approving Read/Write/Edit plus the Composio Meta tool prefixes. Uses the current official Claude Code skills format (Agent Skills standard).

### Part 4: Connect Composio, then Verify (30 min)
- Install the Composio Claude Code plugin (`/plugin marketplace add ComposioHQ/composio-plugin-cc`, then `/plugin install composio@composio`).
- Connect Instagram Business and the Facebook Page with real OAuth approval (`/composio-connect instagram`, `/composio-connect facebook`).
- **Prerequisites and Meta limits:** Instagram must be Business/Creator linked to a Page; Facebook side must be a Page, not a profile; both under one Business Manager.
- **Least privilege:** connect only instagram and facebook. Managed OAuth means no tokens in your files.
- **Verification call before building the report:** confirm at least one account returns real data. Reconnect only the missing toolkit if one is unconnected.
- **Secret handling:** never paste tokens into CLAUDE.md, the skill, screenshots, the repo, or the handout.
- **Meta tool quirks (from the local Composio Meta reference):** IG takes integer unix timestamps, FB takes string dates; metrics silently omitted when absent; follower_count suppressed under 100 followers (use user info); FB per-post engagement comes from the post object, not deprecated insights; wrong arg name 400s with the exact field named.

### Part 5: Inspect Raw Data, Find the Gaps (20 min)
- Pull the window's data and list exactly which metrics returned and which were absent.
- Train the eye on suppression and deprecation. The rule: "no data" when absent, never estimate.

### Part 6: Run the Report by Hand and Critique (20 min)
- Invoke `/weekly-marketing-insights`. It reads the vault, pulls Meta, ranks, explains, and writes `reports/weekly/<brand>-social-<date>.md`.
- **Report structure (exact headings), under 500 words, real numbers only:**
  ```
  # <Brand> Social Report, <start> to <end>
  ## Snapshot
  ## Top Performers
  ## What's not working
  ## Replication playbook
  ## Action items
  ```
- **Grounding test:** every number traces to Meta or the vault; absent metrics say "no data"; top post has a permalink and a specific reason; action items have owners; voice respects do-not-says.

### Part 7: Schedule a Test Run and Verify Delivery (20 min)
- **Why not Claude Code's in-session scheduler for production:** scheduled tasks are session-scoped and expire in seven days. For a weekly job, use the OS scheduler (cron on macOS/Linux, Task Scheduler on Windows). Honest caveat: laptop automation runs only when the machine is on and connected.
- Build a safe non-interactive launcher (`claude -p "/weekly-marketing-insights" --allowedTools "..."`).
- **Test schedule** a few minutes out, confirm the report lands and run-log records status.
- **Delivery:** default is email through a connected Composio email toolkit. If that connection is not set up, the report is written to the vault and the log is flagged "not delivered" - honestly, not meeting the full delivery criterion. The student supplies the email at run time; it is never written into course files.

### Part 8: Weekly Production Schedule + Verification (15 min)
- Swap the test cron for Monday 08:00 local (or the Windows Task Scheduler equivalent).
- Final verification checklist, then homework: let it run twice, fix the first wrong call in the vault, and connect email if still on the vault-only fallback.

**Deliverable:** A **weekly Meta insights report that runs and delivers itself** - a Claude Code project with CLAUDE.md, one verified skill, Composio connected to Instagram and Facebook, a reports/weekly/ output folder with a run log, and a Monday 08:00 schedule on the student's laptop.

### Homework for Week 4
- Let the weekly report run twice. Read both. Note one thing it got wrong and fix that in the vault note responsible, not in the draft.
- If delivery is still the vault-only fallback, connect a Composio email toolkit so the report reaches your inbox.
- Bring the last two reports and your run log to Week 4.

---

## Week 4: The Marketing Operating System - Hardening and Expanding the Harness

**Session Length:** ~3 hours
**Objective:** Take the Week 3 marketing harness and turn it into a durable marketing operating system: more skills, a memory layer that spans runs, failure alerts that page you, and a path off the laptop if uptime matters. This week expands the same Claude Code + vault + Composio system. It does **not** require installing Hermes or a different agent framework; the student keeps the harness they built and grows it.

**The harness thread (capstone):** Week 2 built the vault. Week 3 made Claude Code read it and deliver a weekly report. Week 4 makes that harness self-improving and resilient: it notices when a connection broke, it carries lessons across weeks, and it can hold several skills, not just one.

**Strictly marketing framing:** This session is delivered as "You hired a deputy in Week 3. This week you give that deputy a proper office: a memory that survives the weekend, an alert system when something breaks, and the ability to take on more than the Monday report."

### Part 1: Recap - The Harness You Already Own (15 min)
- Quick recap: the nine layers from Week 3. Which ones are solid (vault, skill, Composio, schedule) and which are thin (memory across runs, failure alerts, multi-skill).
- Why hardening matters: a one-skill harness is a demo; an operating system is something you can ignore until it pings you.

### Part 2: Memory That Spans Runs (30 min)
- The run log (Layer 7) becomes a real memory store: each week's status, top post, and anomalies feed next week's "what changed" line.
- A lightweight `insights-log.md` that the harness updates when it finds a durable pattern (for example "Reels outperform carousels 3 weeks running"). The vault is the long-term memory; the log is the recent memory.
- Honcho.dev as optional session memory if the student wants cross-session recall beyond the files.

### Part 3: More Skills, One Harness (30 min)
- The harness can hold multiple skills. Add, as the student needs them, not all at once:
  - **competitor-watch** - a skill that checks a competitor's recent Meta moves and writes a brief to the vault.
  - **campaign-retro** - a skill that turns a finished campaign's numbers into a retro note, reusing the Week 2 retro template.
  - **content-brief** - a skill that drafts a brief from a persona and product facts.
- Keep the social-insights-reporting skill as the anchor. Resist bolting on the 139-idea library as a weekly job; use it as reference context for the replication playbook instead.
- Each skill follows the same `.claude/skills/<name>/SKILL.md` format and the same grounding rules.

### Part 4: Failure Alerts and Permissions Hardening (30 min)
- Make the harness loud when it fails: the run log records errors, and a small wrapper notifies the student (for example a Desktop notification or a message via a connected Composio channel) when a run ends "not delivered" or "no connected account."
- Tighten `allowed-tools` per skill so reporting skills can never post or send without explicit approval.
- Secrets review: confirm no token lives in any file, the repo, or screenshots.

### Part 5: Off the Laptop If Uptime Matters (20 min)
- Honest limit from Week 3: laptop automation only runs when the machine is on and online.
- Options for durability: a always-on machine, a cloud runner, or a hosted agent. Frame the tradeoff (cost, setup, who owns the account) without prescribing one.
- The vault and skills travel with the student, so moving the runner does not mean rebuilding the system.

### Part 6: Live Build - The Operating System (35 min)
Students harden their Week 3 harness:
1. Promote the run log to a spanning memory; add an `insights-log.md` the skill updates.
2. Add one second skill the student will actually use (competitor-watch or campaign-retro).
3. Add a failure alert so a broken Monday run pages them.
4. Confirm the weekly schedule still fires after the changes.
5. Run a manual end-to-end test and confirm the new memory line appears next run.

**Deliverable:** A **marketing operating system** - the Week 3 harness now with spanning memory, at least two skills, failure alerts, and a durable schedule. The same vault, the same Claude Code, bigger surface.

---

## Course Arc Summary

```
Week 1: Foundations     → "I understand the AI stack - LLMs, APIs, webhooks, agents -
                           and can map my marketing ops against it"
Week 2: Claude           → "I can build brand context vaults that feed my agents,
                           making context engineering my superpower"
Week 3: The Harness      → "I have a Claude Code marketing harness that reads my vault,
                           pulls Meta data through Composio, and delivers a weekly report"
Week 4: The OS           → "That harness is now a self-improving operating system with
                           memory, multiple skills, and failure alerts"
```

## What the Student Walks Away With

| Week | Tangible Deliverable |
|------|---------------------|
| 1 | **Automation Readiness Map** - their entire marketing workload mapped against the AI stack with prioritized next steps |
| 2 | **Brand Context Vault** - structured knowledge base (voice guide, personas, do-not-says) feeding Claude and agents - grows smarter every campaign |
| 3 | **Weekly Marketing Intelligence Harness** - Claude Code project with a verified skill, Composio connected to Instagram + Facebook, a reports/weekly/ folder, and a Monday 08:00 schedule that delivers the report |
| 4 | **Marketing Operating System** - the Week 3 harness hardened: spanning memory, multiple skills, failure alerts, durable schedule |

### Knowledge Evolution

| Before | After |
|--------|-------|
| "AI" is a black box | Can explain what an LLM, API, webhook, and agent actually are |
| Uses ChatGPT for ad-hoc tasks | Has a scheduled harness that reads the vault and delivers a weekly report |
| Manual handoffs between tools | End-to-end automated weekly insights, written back to the vault |
| Doesn't know what tools exist | Knows exactly which layer (chat, workflow, agent, orchestration) for which job |
| Depends on engineering for automation | Can build and deploy their own marketing automation independently |
| No framework for evaluating AI | Clear decision criteria rooted in actual capabilities |

---

## Tool Coverage Summary

| Tool | Weeks | What the Student Can Do After |
|------|-------|-------------------------------|
| **LLM concepts** | 1, throughout | Explain what a model, API, webhook, token, and agent are - to stakeholders and vendors |
| **Claude** | 2, 3, 4 | Build structured brand context vaults that give agents rich brand awareness; produce marketing content that sounds like your brand, not a generic AI |
| **Claude Code** | 3, 4 | Run a local agent harness: instruction file, reusable skills, headless scheduled runs, vault-fed reports |
| **Composio** | 3, 4 | Connect Claude Code to Instagram Business and a Facebook Page through managed OAuth; pull real Meta insights without writing API code |
| **Operating system scheduler** | 3, 4 | Run the weekly report on cron (macOS/Linux) or Task Scheduler (Windows); understand the laptop-online caveat |
| **honcho.dev (optional)** | 4 | Persistent session memory across conversations, if wanted |

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
- Willingness to install software (Claude Code in Week 3; no Docker required)
- A Google account (for Google Sheets/docs integrations in demos)
- Claude.ai account by Week 2

### What's NOT Covered (Intentionally)
- Writing code from scratch (we use GUI tools + templates and Claude Code's skill system)
- Training/fine-tuning models (not needed for 99% of marketing use cases)
- Building AI from the ground up
- Vendor evaluation frameworks (we focus on open-source + accessible tools)
- Prompt injection security or adversarial attacks
