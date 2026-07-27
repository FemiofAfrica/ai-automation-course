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

### Part 2: The Four-Layer Automation Stack (40 min)

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

### Part 3: Quick-Build Deliverable (50 min)

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

## Week 2: Claude & Prompting — Your AI Copilot for Marketing

**Session Length:** ~3 hours
**Objective:** Move beyond casual ChatGPT use. Master Claude for marketing content, analysis, and structured outputs. Understand the Claude API conceptually (don't code — but know when to call in engineering).

**Strictly marketing framing:** This entire session is delivered through the lens of a marketing executive running campaigns, managing brand consistency, briefing agencies, and producing assets at scale. Every prompt example, every demo, every exercise references a real marketing scenario with named audiences, brand constraints, and campaign goals.

### Part 1: Refresher + Model Sharpening (15 min)
- Quick recap: what an LLM is and how Claude fits into a marketing stack
- Claude's strengths vs. other models for marketing work:
  - Claude's 200K context: upload your full brand guidelines, past campaign briefs, competitor swipe file — all at once
  - Claude excels at structured outputs (tables, JSON) — directly usable in campaign dashboards and automation pipelines
  - Claude's Artifacts: living marketing documents, not just chat responses
- The model lineup for marketing use:
  - **Haiku** (fast/cheap): bulk product description generation, social post variants, subject line A/B testing — tasks where speed × volume > peak quality
  - **Sonnet** (balanced): campaign briefs, competitive analyses, ad copy, email nurture sequences — the daily driver for marketing work
  - **Opus** (best quality/costliest): brand strategy docs, thought leadership, high-stakes messaging for launch campaigns, positioning review
- **Marketing decision framework:** "For a Q3 product launch campaign with 40 assets across 6 channels, which model do you use for each asset type?"

### Part 2: Prompt Engineering for Marketing (45 min)

**2.1 Anatomy of a Great Marketing Prompt**
Every prompt element illustrated with a real campaign example:

- **Persona** — "You are a senior demand gen strategist for Salesforce's Enterprise Sales Cloud. You write for VP-level B2B buyers in financial services who care about compliance, not features."
- **Context** — The campaign's target ICP, channel strategy, competitive landscape (uploaded as doc or embedded in custom instructions)
- **Task** — "Write a 3-email nurture sequence for the 'abandoned demo request' trigger. Each email must have a subject line, preheader, body (max 150 words), and a single CTA."
- **Constraints** — "Tone: authoritative but not arrogant. No jargon. Must comply with CAN-SPAM. Do not use the word 'revolutionize.' Reference competitors by category only, never by name."
- **Output format** — "Return as a markdown table with columns: Email #, Trigger, Subject Line, Preheader, Body, CTA, Success Metric"

**2.2 Live Prompt Crafting Workshop — Marketing Edition**
- **Before/After demo:** Start with a bad prompt ("Write some ad copy for our product") and rebuild it step by step into a production-grade marketing brief prompt with persona, brand voice doc, audience segments, and measurable KPIs
- **Marketing personas exercise:** Students write their own reusable persona prompt blocks for 3 audience segments they actually target (e.g., CTO vs. CMO vs. Procurement — same product, totally different messaging)
- **The 5-prompt marketing workflow framework:** Brief → Audience Research → Content Draft → Personalize by Segment → Critique & QA
  - Each step is a standalone prompt that passes output to the next — creating a repeatable content production pipeline inside Claude
- **Prompt templates as reusable marketing assets:** Build a library: Campaign Brief Generator, Product Launch Sequence, Agency Brief, Competitor Takedown, Webinar Recap, Newsletter Edition, ABM Personalization

**2.3 Claude's Advanced Features for Marketing**
- **Projects:** Keep your brand playbooks, ICP definitions, messaging hierarchy, and competitive matrix in one project — every chat starts from your marketing truth
- **Custom instructions:** One-time setup so Claude knows your product category, brand voice (tone scale: "HubSpot casual" → "McKinsey formal"), target markets, and do-not-says — no need to re-state in every prompt
- **Artifacts:** Claude generates living campaign briefs, content calendars, and competitive battle cards — not just chat. Edit them collaboratively, export as markdown/HTML
- **200K context window in marketing:** Upload your entire past quarter's campaign data, competitor press releases, customer interview transcripts — Claude synthesizes instead of you reading 200 pages

### Part 3: Beyond the Chat UI — The API Layer (30 min)

- **What the API enables that chat can't for marketing:**
  - Batch generate 200 localized ad variants in 3 minutes — impossible in chat UI
  - Embed Claude inside your campaign automation (n8n triggers Claude API per lead enrichment)
  - Programmatic A/B testing: same brief, 5 prompt variants → API returns all 5 → team votes
- Conceptual walkthrough: "Here's what happens when a marketing automation platform calls Claude" — no code, just the request/response cycle visualized
- **Cost model for marketing execs:** "Generating 50 personalized email sequences per day costs ~$X in tokens. Compare that to a copywriter's hourly rate."
- **Decision framework — which Claude interface for which marketing job:**

| Marketing Task | Use This | Why |
|---|---|---|
| Draft one campaign brief | Claude.ai chat | Fast, iterative, free-form |
| Generate 100 local landing page variants | Claude API via n8n | Programmatic, batch, cheaper per unit |
| Analyze 50 customer interview transcripts | Claude.ai Project upload | Context window fits all 50 docs |
| Real-time lead enrichment from form submit | Claude inside n8n workflow | Sub-second, event-driven |
| Daily competitor monitoring brief | Claude as Hermes agent brain | Persistent, scheduled, autonomous |

### Part 4: Live Build — Marketing Brief Generator (60 min)

Build a reusable system that takes a product spec + target persona and produces a complete marketing brief — the kind a marketing exec typically spends 2–3 hours writing per campaign. Delivered as a Claude Project template with custom instructions + a reusable prompt library.

**Inputs (student provides):**
1. Product/feature name and 3-sentence description
2. Target buyer persona (or select from pre-built personas: B2B SaaS CTO, B2C DTC buyer, Enterprise procurement lead)
3. Campaign type (product launch, demand gen, thought leadership, event promotion, ABM 1:1)
4. Brand voice sample (a blog post, landing page, or email they'd say is "on brand")

**Outputs Claude produces:**
- **Positioning statement** — structured as: For [target persona] who [need], [product] is a [category] that [key benefit]. Unlike [competitor category], we [differentiator].
- **Messaging hierarchy** — hero message → 3 supporting messages → proof points for each → objection handlers
- **Channel-by-channel asset briefs:** which asset for which stage (TOFU blog post, MOFU webinar outline, BOFU case study brief)
- **Sample content for each channel:**
  - Blog: headline, H2 outline, key stat hook
  - LinkedIn: 3 post variants (thought leader, data-driven, customer story)
  - Email: Subject line + preheader for awareness, nurture, and conversion sequences
  - Paid ad: 5 headline × 2 description variants, with audience segment targeting notes
- **Success metrics recommendation** — which KPIs to track per channel, with benchmark ranges from industry data

**Deliverable:** A Claude Project template with custom instructions + a reusable prompt library. Students leave with a system they can adapt to any product or campaign — reducing brief creation from 3 hours to 20 minutes, with guaranteed brand consistency.

### Homework for Week 3
- Install Docker Desktop (if not already installed) — n8n runs in Docker
- Have access to at least 2 marketing tools you use daily (Gmail, Slack, Notion, Google Sheets, HubSpot, etc.)
- Bring 1 manual marketing workflow you do repeatedly that involves 3+ tools (e.g., "Every Monday I pull LinkedIn ad data, paste into a slide deck, add commentary, and email the team")

---

## Week 3: n8n — Workflow Automation That Connects Your Marketing Stack

**Session Length:** ~3 hours
**Objective:** Connect your entire marketing stack without a developer. Build automated workflows with AI nodes, error handling, and real tool integrations. Every demo and exercise is a real marketing workflow a marketing exec would run every week.

**Strictly marketing framing:** This session never shows a generic "hello world" workflow. Every build starts from a marketing problem — lead enrichment delays, content distribution fragmentation, reporting that takes 3 hours every Monday morning, social posting that requires 4 tools and a prayer.

### Part 1: Refresher + Vocabulary (15 min)
- Quick recap: what is an API? What is a webhook? (straight from Week 1)
- How n8n uses both to connect your marketing tools without code
- n8n v1.0: self-hosted (keep sensitive campaign data on your infra) vs. n8n Cloud (start in 5 minutes) — what each costs, when to use which for marketing ops

### Part 2: n8n Architecture in 25 Minutes (25 min)

- **The canvas — a marketing lens:** triggers (a form submit, a Notion page tagged "Ready", a scheduled Monday 9 AM report) → nodes (Gmail, HubSpot, Claude, Google Sheets, Slack, LinkedIn, Twitter) → data flow → output (post sent, email delivered, report shared, lead enriched)
- **Trigger types relevant to marketing:** webhook (form fill, CRM event, tool push), schedule/cron (weekly ad report, daily social queue), manual (click a button to approve and publish)
- **Node types:** action nodes (Gmail send, Slack message, Google Sheet append, HubSpot create contact), data transformation (format campaign data, remove duplicates, enrich with lookup), HTTP requests (call Claude API, fetch ad platform data), AI/LLM nodes (n8n v1.0 native Claude node)
- **Data passing in plain language:** "When a lead fills out a form, their name, company, and email travel through the workflow as a little JSON package. Each node can add to it, transform it, or pass it along. You can see the data at every step — no black boxes."
- **Error handling basics for marketing:** what happens when Claude API is busy, HubSpot rejects a contact, or an email bounces — design workflows that fail gracefully instead of falling silent

**Live demo:** Build a simple marketing workflow start-to-finish in 10 minutes. A lead form submission webhook → Claude enriches the lead with company industry and employee count → appends to a Google Sheet → notifies the team in Slack. Everyone sees the data flow in real time.

### Part 3: Marketing Workflows That Actually Save Time (50 min)

Walk through 4 real marketing workflows with live demos. Students follow along on their own n8n instances. Each workflow is named after a specific campaign scenario, not a generic function.

**Workflow 1: Social Content Repurposing Engine**
Campaign scenario: Your team published a 2,000-word thought leadership blog post on Monday. You need LinkedIn posts, Twitter threads, a newsletter blurb, and a Slack team summary — manually, this is 2 hours of reformatting.

- Trigger: RSS feed detects new blog post, or Notion page tagged "Published"
- Claude API node: reads full article → generates 3 LinkedIn post variants (one thought-leader angle, one data-driven, one customer-story), a Twitter thread (5-tweet structure), and a 3-sentence newsletter blurb
- Outputs: LinkedIn post via n8n's LinkedIn connector (draft/scheduled), Twitter thread via Twitter API, newsletter blurb appended to an "Upcoming Newsletter" Google Sheet row
- **Key learning:** trigger, multi-output from a single AI call, platform-specific content formatting
- **Marketing metric saved:** 2 hours/week per article × 4 articles/month = 8 hours/month reclaimed

**Workflow 2: Lead Enrichment & Routing Pipeline**
Campaign scenario: A whitepaper download form captures name + email only. Your sales team needs company size, industry, recent funding news, and a personalization hook within 5 minutes — or the lead goes cold.

- Trigger: Webhook from form submission (HubSpot form, Typeform, or manual webhook)
- Claude API node: takes company domain (from email) → web searches company profile, checks Crunchbase for funding, identifies recent news → returns structured enrichment: industry, employee count, funding stage, key product category, 3 personalization angles
- HubSpot node: creates/updates contact with enriched fields + lead score
- Slack node: posts to #sales-alerts with "High-value lead: [Name], [Company] — just raised $X Series Y — recommended angle: [personalization hook]"
- Conditional branch: if company > 200 employees AND recent funding → route to Enterprise sales Slack channel, otherwise → SDR queue
- **Key learning:** webhook triggers, AI enrichment, conditional routing, CRM integration
- **Marketing metric saved:** Lead response time from 2 hours → 2 minutes. Conversion lift from faster follow-up: documented industry benchmark is 7–10x

**Workflow 3: Content Operations — Notion Brief to Published Asset**
Campaign scenario: Your content marketing manager approves a brief in Notion. Then begins the manual chain: assign writer → wait for draft → edit → upload to CMS → create social variants → request review. Each handoff introduces delays.

- Trigger: Notion database status changes from "Brief Approved" to "In Production" (or manual webhook from your CMS)
- Claude API node 1 (Draft): takes the Notion brief content → produces full article draft, respecting brand voice and SEO keywords from the brief
- Google Docs node: creates a new Google Doc with the draft, shares it with the editor's email from Notion
- Claude API node 2 (Social): generates platform-specific variants (LinkedIn, Twitter, email excerpt)
- n8n Wait node: pauses for 24 hours (review time). Then checks if Google Doc status changed (manual human completion)
- Slack node: posts "Content in review: [Doc title] — please approve by EOD" to #content-team
- **Key learning:** tool integrations, conditional branches (human-in-the-loop delays), multi-stage AI processing, status checking
- **Marketing metric saved:** Content publication cycle from 5 days → 1.5 days. Predictable pipeline, no manual chases.

**Workflow 4: Automated Weekly Campaign Dashboard**
Campaign scenario: Every Monday, a marketing operations person spends 2 hours pulling data from Meta Ads, Google Ads, LinkedIn Campaign Manager, and HubSpot, pasting into a Google Sheet, writing commentary, and emailing stakeholders. By Wednesday, the data is already stale.

- Trigger: Schedule node — every Monday at 8 AM
- HTTP Request node 1: pulls campaign data from Meta Ads API (cost, impressions, CTR, conversions)
- HTTP Request node 2: pulls data from Google Ads API
- HTTP Request node 3: pulls data from LinkedIn Campaign Manager API
- Google Sheets node: appends all data to a master campaign tracker (one row per campaign per week)
- Claude API node: reads the sheet row → generates a 3-paragraph executive summary: "This week's top performer was [Campaign X] with a 3.2x ROAS. [Campaign Y] underperformed — recommended actions: pause, reallocate budget to [Channel Z], A/B test creative refresh"
- Email node (Gmail/SMTP): sends formatted report with tables and bullet-point recommendations to stakeholders
- **Key learning:** scheduled triggers, multi-source data aggregation, AI summarization, email delivery
- **Marketing metric saved:** Monday report from 2 hours → 5 minutes. Data is always fresh. Recommendations are actionable, not just numbers.

### Part 4: The Claude-n8n Bridge — AI-Powered Marketing Automation (30 min)

- Using n8n's HTTP node (or native Claude node in v1.0) to call the Claude API from any marketing workflow
- **Structured prompting inside marketing workflows:** passing dynamic data into prompts — "Lead company name: {{company}} → Claude generates a personalized email opening referencing their recent funding round"
- **Multi-step AI tasks for campaign execution:** Research (Claude reads competitor landing page) → Draft (Claude writes response campaign brief) → Personalize (Claude adapts for 3 audience segments) → QA (Claude reviews for brand voice compliance) — all in one automated pipeline
- **Real example — ABM personalization at scale:** n8n receives a list of 50 target accounts → loops through each → Claude researches each account → generates personalized outreach copy → HubSpot creates contact + logs note → n8n sends email via Gmail. All 50 done in under 5 minutes.
- **Cost awareness for marketing budgets:**
  - Each Claude API call in a workflow has a token cost — design workflows to batch requests rather than call per item
  - Use Haiku for enrichment/scoring (high volume, lower quality needs), Sonnet for content generation, Opus for strategic analysis only
  - Show a real cost calculation: "This lead enrichment workflow costs ~$0.03 per lead. At 200 leads/month, that's $6. A fraction of one hour of your ops person's time."
- **Error recovery for campaign-critical workflows:** what happens when Claude is down, rate-limited, or returns bad output — design fallback paths (retry with delay, use cached response, alert the team instead of failing silently)

### Part 5: Live Build — Automated Multi-Channel Campaign Distribution Pipeline (60 min)

Build a publish-ready workflow for a real campaign scenario: a product launch or major content piece that needs to hit 4+ channels with platform-optimized variants, all triggered from a single "Go" signal.

**Campaign scenario:** Your team is launching a new research report ("2025 State of B2B Marketing"). The report is done, the landing page is live. Now someone needs to: write the launch post for every channel, schedule them, and make sure nothing breaks.

Build this workflow:

1. **Trigger — Single "Launch" signal:** A new Notion page tagged "Ready to Publish" OR a manual webhook (click a bookmarklet, send a POST from your CMS) with the campaign name, report URL, and key stat
2. **Claude generates 4 channel-specific variants:**
   - LinkedIn post (thought leadership angle, 3-paragraph, 2,000 char limit)
   - Twitter thread (8-tweet arc: hook → findings → surprise stat → call to action)
   - Email announcement to newsletter list (subject line, preheader, 150-word body, CTA button)
   - Short-form video script (60-second script: hook → 3 key stats → CTA overlay)
3. **n8n social connectors:** Queue LinkedIn post, Twitter thread, and schedule email via Gmail/SMTP
4. **Google Sheets performance log:** Append a row with campaign name, timestamp, all channel URLs once posted, and a "Check back in 7 days" placeholder for metrics
5. **Slack team notification:** Post to #marketing-ops with a summary table of what was posted where, with direct links to each post
6. **Human-in-the-loop approval gate:** Before anything goes live, n8n sends a Slack message with preview links and a "👍 Approve / 🔁 Edit / ❌ Cancel" button — the workflow pauses until the marketing director clicks approve

**Deliverable:** A fully functional **Multi-Channel Campaign Distribution Pipeline** — ready to connect to the student's actual marketing accounts. Template provided so they can swap in their own tools (their HubSpot instead of generic CRM, their Mailchimp instead of Gmail, their brand's channel priorities).

### Homework for Week 4
- Install Hermes Agent (instructions provided: `pip install hermes-agent`)
- Have a Claude API key ready (guide provided for getting one)
- Think of 1 recurring marketing task you'd want an agent to handle autonomously — ideally something that currently consumes 2+ hours of your week (e.g., "Monday morning competitor briefing," "inbound lead qualification," "weekly content performance recap")

---

## Week 4: Hermes Agent — Autonomous Marketing Operations

**Session Length:** ~3 hours
**Objective:** Deploy a persistent AI agent that knows your brand, remembers past work, learns from feedback, and executes multi-step marketing tasks independently. Tie together everything from Weeks 1–3 into one autonomous marketing system.

**Strictly marketing framing:** This session is delivered as "You're hiring a new team member — one that never sleeps, never forgets, and costs a fraction of a junior hire. But like any new hire, they need onboarding: brand voice training, tool access, and defined responsibilities." Every concept, every demo, every skill is a marketing-specific scenario.

### Part 1: Refresher — From Workflows to Autonomous Marketing Agents (15 min)
- Quick recap: LLMs, APIs, webhooks, n8n workflows — the building blocks you now understand
- **The gap in a marketing context:** n8n workflows execute fixed paths perfectly. But marketing is full of judgment calls: "Is this competitor move significant enough to brief the CMO?" "Should I use the customer story angle or the data angle for this LinkedIn post?" "This campaign underperformed — what changed?" Agents reason, adapt, and learn. They handle the judgment calls; workflows handle the execution.
- How Hermes sits on top of everything we've covered: **Claude as the brain** (reasoning, content), **APIs as the limbs** (reach any tool), **webhooks as the senses** (agent hears about a new lead, a competitor launch, a campaign milestone), **n8n as the skeleton** (execution of multi-tool sequences the agent orchestrates)

### Part 2: What Hermes Agent Is and What It Changes for Marketers (30 min)

**2.1 Core Concepts — Marketing Edition**
- Hermes is an open-source agent framework by Nous Research
- It wraps any LLM (Claude API, GPT, DeepSeek, local models) with tools, memory, and multi-platform delivery
- It is NOT a separate model — it's a harness that turns any model into a marketing operations assistant that knows your business

**2.2 Key Capabilities for Marketing Execs**

- **Persistent brand memory:** Hermes learns your voice guides, buyer personas, messaging hierarchy, competitor intel, and past campaign performance — across all sessions. You never re-explain who you are.
  - *Marketing scenario:* You ran a Q2 demand gen campaign. In Q3, you ask "Hermes, tell me what messaging resonated best in Q2 and recommend the Q3 approach." It remembers the campaign data, the A/B test results, and your feedback from the post-mortem.
- **Skills — reusable marketing procedures:** Invoke by name with parameters. "Hermes, run competitor analysis on [company name]" executes a multi-step procedure: web search → Claude analysis → structured brief → saved to Notion. You don't rewrite the process every time.
- **Multi-platform delivery in a marketing team context:** Same agent on Slack (team asks questions in channel), email (forward a press release → agent processes → replies with briefing), terminal (your personal access), desktop app (always available)
- **Profiles for agency/multi-brand marketing:** Separate agents for each brand or campaign — each with its own memory, skills, and tool access. No cross-brand contamination.
- **Self-improvement loop:** You give feedback ("This brief was too long for the exec audience") → Hermes patches the skill → next execution is better. Like training a junior marketer, but the learnings persist in code, not in someone's memory.
- **Tool access for marketing research:** Web search (competitor intel, market trends), file system (read/write campaign docs, briefs, data files), APIs (call any marketing tool Hermes is connected to)

**2.3 What Changes for a Marketing Team**

- **Before:** Drafting every prompt from scratch. Losing context between sessions. No institutional memory. Every campaign brief starts from zero.
- **After:** "Hermes, run a Q3 product launch campaign retro" → agent knows the brand, has access to campaign performance data, produces a structured retro report with recommendations, saves it to the team's Notion campaign archive. Done in 3 minutes instead of a 2-hour meeting.

### Part 3: Setting Up Hermes for Marketing Operations (40 min)

**Live walkthrough — students follow along on their machines, building an agent configured for their actual marketing needs:**

1. **Installation & provider setup** (10 min)
   - Install Hermes (`pip install hermes-agent`)
   - Configure Claude as the reasoning engine (API key setup)
   - First run: chat with the agent — give it a real marketing task ("What do you know about my brand?" — it knows nothing yet. Shows why memory matters.)

2. **Configuring brand memory — onboarding your agent like a new hire** (10 min)
   - **Brand voice guidelines → memory:** "Upload" (via prompt or file) your brand voice doc. Claude stores it in persistent context. From now on, every piece of content Hermes generates is on-brand.
   - **Buyer personas → memory:** Add your 3 core ICPs with demographics, pain points, buying triggers, and channel preferences.
   - **Competitive landscape → memory:** Add your top 3 competitors, their positioning, your differentiators vs. each.
   - **Past campaign learnings → memory:** Add key takeaways from the last 2 campaigns (what worked, what bombed, why).
   - **Verification:** Ask "Hermes, what's our brand voice on pricing conversations?" — it should answer from memory, not guess.

3. **Building your first 3 marketing skills** (15 min)
   Skills are plain markdown files — editable, shareable, version-controllable. Students build alongside the instructor:

   - **Skill 1: Competitive Analysis Brief**
     Trigger: "Run competitive analysis on [company]"
     Procedure: Web search company → read landing page + latest blog/press → Claude writes structured competitive brief (positioning, strengths, weaknesses, messaging gaps, recommended counter-positioning) → saves to Notion campaign research database
     *Marketing use case:* Before a quarterly strategy meeting, brief the team on everyone in the landscape in 5 minutes.

   - **Skill 2: Content Brief Generator**
     Trigger: "Create content brief for [topic/product] targeting [persona]"
     Procedure: Search internal knowledge base for existing content → research topic (web search) → Claude writes positioning, messaging hierarchy, channel-specific asset briefs, SEO keywords, and success metrics → saves to Notion content calendar
     *Marketing use case:* A freelance writer needs a brief by 10 AM. You invoke this skill at 9:50 AM. Brief lands in their Notion before they ask.

   - **Skill 3: Campaign Retrospective**
     Trigger: "Run retro on [campaign name/period]"
     Procedure: Pull campaign data from specified source (n8n workflow that fetches ad platform data, or a Google Sheet with campaign KPIs) → Claude analyzes performance vs. goals, identifies what drove results, surfaces anomalies, writes action recommendations → saves to Notion campaign archive
     *Marketing use case:* Post-campaign debrief that actually produces action items instead of 45 minutes of "we should probably do more video."

4. **Multi-platform delivery for marketing teams** (5 min)
   - **Connect Hermes to Slack:** Marketing team posts "Hermes, what's the competitive landscape for our Q4 planning?" in #marketing-research → Hermes runs Competitor Analysis skill → posts structured brief as a thread -> team discusses in channel without leaving Slack
   - **Connect Hermes to email:** Forward a competitor's press release to hermes@yourdomain.com → Hermes processes → replies with a competitive response brief — before you've finished your coffee

### Part 4: Hermes + n8n — The Hybrid Marketing Automation Pattern (30 min)

- **The two integration patterns for marketing campaigns:**

  1. **n8n triggers Hermes — workflow hits an AI-heavy step that needs judgment:**
     *Example:* Lead enrichment workflow runs. Data is collected. But the AI enrichment step needs Hermes-level reasoning: "This lead is from a company that just announced a layoff — adjust the personalization angle to be empathetic." The n8n workflow fires a webhook to Hermes, Hermes reasons, returns the enriched output, n8n continues.

  2. **Hermes triggers n8n — agent decides it needs tool execution beyond its capabilities:**
     *Example:* Hermes is running a competitive monitoring skill. It finds a major competitor launch. It decides: "This needs immediate action." Hermes calls an n8n webhook → n8n workflow: creates an Asana task for the product marketing lead, writes a Slack alert to #war-room, drafts a CMO briefing email, and schedules a 30-min huddle on the team calendar. Hermes makes the decision; n8n executes the multi-tool response.

- **Live demo — End-to-end marketing campaign response:**
  Campaign scenario: A competitor launches a new feature that threatens your positioning.
  1. Hermes (monitoring skill) detects new product announcement via RSS/blog monitoring
  2. Hermes researches the feature (web search, competitor landing page, social reception)
  3. Hermes decides: "This is significant — escalate" and calls n8n webhook
  4. n8n workflow runs:
     - Creates Notion page "Competitor Threat: [Feature]" with Hermes' research as the brief
     - Posts to Slack #marketing-war-room: "Competitor X launched [Feature] — here's what it does, here's how our positioning holds up, recommended counter-play: [strategy]"
     - Sends email to product marketing lead with full briefing
     - Adds a task to Asana: "Draft competitive response campaign — due in 48 hours"
  5. Marketing director reviews in Slack, replies with feedback → next iteration begins

- **Decision framework for marketing execs: when to handle a step in n8n vs. in Hermes**

| Scenario | Handle In | Why |
|---|---|---|
| Post draft to social on schedule | n8n | Fixed execution, no judgment needed |
| What angle should this social post take? | Hermes | Requires brand knowledge, audience understanding, and campaign context |
| Send email when lead reaches score 80 | n8n | Deterministic trigger + action |
| Should we escalate this competitor move? | Hermes | Judgment call based on severity, brand risk, and campaign timing |
| Format and deliver weekly report | n8n | Predictable data aggregation and delivery |
| What story does this week's data tell? | Hermes | Requires synthesis, trend-spotting, strategic framing |

### Part 5: Compressed — Multi-Agent Orchestration & Production for Marketing (30 min)

**Orchestration — Why One Marketing Agent Isn't Enough for Growing Teams**
- **Specialization logic:** A researcher agent needs different context (competitor tracking, market trends, news) than a content agent (brand voice, audience segments, campaign history). Stuffing everything into one agent dilutes both.
- **The pattern — manager agent orchestrates specialists:**
  1. **Monitoring Agent:** Watches competitor blogs, press releases, social accounts, review sites — flags significant moves
  2. **Research Agent:** Takes a flag → deep-dives → produces structured brief (positioning change, feature gaps, messaging analysis)
  3. **Content Agent:** Takes the research brief → drafts response assets (blog, social, email sequence, sales enablement one-pager)
  4. **Distribution Agent:** Takes approved content → calls n8n workflows → schedules across channels → logs performance
  5. **Manager Agent:** Orchestrates the flow, decides when human review is needed, maintains the strategic lens
- **Marketing analogy:** This is exactly how a marketing department works — a CMO (manager), strategist (researcher), copywriter (content), and ops manager (distribution). You're building the AI equivalent.
- **Quick live demo:** Monitoring agent flags competitor blog post → researcher writes brief → content drafts response → posts to Slack for human approval. All within 8 minutes of the competitor publishing.

**Production — Making Marketing Automation Last**
- **Reliability in marketing operations:** What breaks (Claude API rate limits during peak campaign launches, n8n workflow timeouts on big data pulls, tool authentication expiring) and how to design around it — retries, fallback channels, alerting when a workflow falls over
- **Cost management for marketing budgets:**
  - Token budgeting per campaign: track what each campaign workflow costs in API calls
  - Model tiering by task: Haiku for enrichment/scoring (90% of volume, lowest cost), Sonnet for content generation, Opus for strategy and high-stakes messaging only
  - Show real budget projection: "$50/month in Claude API costs replaces ~$3,000/month of contractor hours on content generation"
- **Security — what a marketing exec must know:**
  - What data should never touch an external API (customer PII beyond what's needed, unreleased campaign strategy, board-level financial targets)
  - GDPR/CCPA for marketing automation: automated consent management, data retention, right-to-deletion workflows
  - Access control: who in the marketing org can trigger/modify automation, audit trails for campaign approvals
- **Team rollout strategy:**
  - Profiles per team member or per brand (agency scenario)
  - Shared skills library: the competitive analysis skill one person builds→ the whole team uses
  - Onboarding: new team member gets their own Hermes instance pre-loaded with brand memory and team skills

### Part 6: Live Build — Brand Intelligence Agent (60 min)

Students build their own production-ready marketing agent, configured for their actual brand, audience, and workflows.

1. **Deploy** — Hermes instance running with Claude as the brain
2. **Configure brand memory:**
   - Brand voice guidelines (tone, vocabulary, do-not-says, competitive positioning)
   - 2–3 buyer personas (demographics, pain points, buying triggers, channel preferences)
   - Competitive landscape (top 3 competitors, key differentiators, messaging gaps)
3. **Build 3 skills:**
   - **Skill 1: Competitive Analysis Brief** — company name → web research → structured brief → saved to Notion
   - **Skill 2: Content Brief Generator** — product/topic + persona → full marketing brief with positioning + per-channel assets → saved to content calendar
   - **Skill 3: Campaign Retrospective** — campaign name/period → performance analysis → recommendations → saved to campaign archive
4. **Connect at least one n8n workflow** — e.g., the lead enrichment pipeline from Week 3. When Hermes identifies a high-value lead during analysis, it triggers the n8n workflow to execute the multi-tool response.
5. **Test with a real scenario:** "Analyze our main competitor's latest product launch and brief the marketing team"
   - Instructor runs this live on their machine first, showing the full output
   - Students run it on their own agent with their own competitor
   - Debrief: what did the agent get right? What needs refinement? How do you give feedback to improve the skill?

**Deliverable:** A live **Brand Intelligence Agent** — fully configured with brand memory, 3 marketing skills, and n8n integration. Ready to handle real marketing workflows on Monday morning. Students leave with a working AI team member, not a theoretical concept.

---

## Course Arc Summary

```
Week 1: Foundations     → "I understand the AI stack — LLMs, APIs, webhooks, agents — 
                           and can map my marketing ops against it"
Week 2: Claude           → "I can produce structured marketing assets 10x faster
                           using Claude + prompt engineering"
Week 3: n8n              → "I can automate multi-tool marketing workflows 
                           without a developer"
Week 4: Hermes Agent     → "I have a persistent AI marketing assistant with brand
                           memory, skills, and tool integration"
```

## What the Student Walks Away With

| Week | Tangible Deliverable |
|------|---------------------|
| 1 | **Automation Readiness Map** — their entire marketing workload mapped against the AI stack with prioritized next steps |
| 2 | **Marketing Brief Generator** — Claude project template + reusable prompt library |
| 3 | **Multi-Channel Campaign Distribution Pipeline** — automated Notion → Claude variants → LinkedIn + Twitter + email → performance log |
| 4 | **Brand Intelligence Agent** — live Hermes instance with brand memory, 3 skills, and n8n integration |

### Knowledge Evolution

| Before | After |
|--------|-------|
| "AI" is a black box | Can explain what an LLM, API, webhook, and agent actually are |
| Uses ChatGPT for ad-hoc tasks | Has a persistent agent with brand memory, skills, and n8n integration |
| Manual handoffs between tools | End-to-end automated workflows connecting 200+ tools |
| Doesn't know what tools exist | Knows exactly which layer (chat, workflow, agent, orchestration) for which job |
| Depends on engineering for automation | Can build and deploy their own automation independently |
| No framework for evaluating AI | Clear decision criteria rooted in actual capabilities |

---

## Tool Coverage Summary

| Tool | Weeks | What the Student Can Do After |
|------|-------|-------------------------------|
| **LLM concepts** | 1, throughout | Explain what a model, API, webhook, token, and agent are — to stakeholders and vendors |
| **Claude** | 2, 3, 4 | Produce structured marketing content at scale; integrate into automated workflows; prompt engineer like a pro |
| **n8n** | 3, 4 | Build production-grade marketing workflows connecting 200+ tools; trigger AI steps; handle errors |
| **Hermes Agent** | 4 | Deploy autonomous agents with persistent memory, skills, and multi-platform reach |
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
