# Setup Guide & Prerequisites

**Course:** AI Automation for Marketing Executives
**Format:** 4 live sessions × ~3 hours each

---

## Already Set Up

✅ **Claude account** - You already have this. We'll use Claude.ai (web) and the Claude API during the course.

---

## What to Read Before Week 1

These concepts will come up repeatedly. You don't need to master them - just know what they are so the first session isn't overwhelming.

### 1. Terminal / Command Line

The terminal is how you talk to your computer directly - no mouse, no windows, just text commands. You'll use it to run scripts, install tools, and launch agents.

**What to know:**
- What a terminal is and how to open it (Mac: Spotlight → "Terminal")
- Basic commands: `ls` (list files), `cd` (change directory), `mkdir` (create folder), `pwd` (where am I?)
- Running a command and reading its output
- What "path" means (absolute vs relative paths - `/Users/you/folder` vs `./folder`)

**Resource:** Read the first 5 minutes of any "command line for beginners" guide. That's enough.

### 2. Scripts

A script is a text file containing instructions your computer runs automatically. Like a recipe - a list of steps to follow in order.

**What to know:**
- What a script is (a file with commands that run in sequence)
- The difference between a script and typing commands manually
- Simple script structure: commands, variables (named values like `NAME="Claude"`), comments (notes for humans)
- That scripts can pass data between steps - the output of step 1 becomes the input of step 2

**Resource:** A 5-minute read on what scripts are. No need to write one.

### 3. Markdown

Markdown is a simple way to format text - like Word without the buttons. You'll use it to build your Brand Context Vault (Week 2).

**What to know:**
- Headings: `# Title`, `## Section`, `### Subsection`
- Bold: `**bold text**`
- Lists: `- item` for bullets, `1. item` for numbered
- Links: `[text](url)`
- Code: backticks for inline code, triple backticks for code blocks
- What YAML frontmatter is (the `---` block at the top of a file with metadata)

**Resource:** Read any "markdown cheat sheet" - takes 3 minutes.

### 4. JSON

JSON is how data moves between tools. When Claude Code reads your vault, when Composio talks to Meta, when your harness writes a report - a lot of it is structured data shaped like JSON.

**What to know:**
- What JSON looks like: `{"name": "value", "list": [1, 2, 3]}`
- Key-value pairs
- Arrays (lists in square brackets)
- Objects (groups in curly braces)
- That JSON is just structured data - same as a table or a form

**Resource:** A 3-minute skim of "what is JSON."

### 5. An Agent Harness (Claude Code)

A harness is the software that wraps a model with everything it needs to do a job without you in the room. In Weeks 3 and 4 you use Claude Code as the harness: it reads your vault as local files, runs a skill you install, and can be scheduled to run weekly.

**What to know:**
- Claude Code is a terminal tool from Anthropic that runs an agent on your own machine
- It reads and writes files in a folder (your vault), and you can give it reusable "skills"
- You do NOT need to install Docker or a separate server for this course
- Composio plugs into Claude Code so it can call Instagram and Facebook through managed OAuth (no API keys in your files)

**Resource:** Just understand the concept. Install instructions come in Week 3.

### 6. Environment Variables

An environment variable is a named value stored outside your code - like a sticky note on your computer that says "API_KEY = abc123." Your tools read these notes instead of you typing sensitive info directly.

**What to know:**
- What they are (named values your system remembers)
- Why they matter (you store API keys, tokens, and config here - never in your code)
- That Composio manages its own connection secrets for you, so you will rarely set these by hand in this course

**Resource:** A 2-minute read on "what are environment variables." No action needed.

### 7. File System Structure (Optional but Useful)

The folder structure of your Brand Context Vault (Week 2) will look like this:

```
brand-context-vault/
├── 01-voice/
├── 02-personas/
├── 03-competitive/
├── 04-product/
├── 05-campaigns/
├── 06-messaging/
```

Understanding how folders and files are organized - and how tools navigate them via paths - will make Weeks 2–4 smoother.

---

## Software to Install (By Week)

### Before Week 1
- Nothing. Show up with your laptop.

### Before Week 2
- **Obsidian** (free) - [obsidian.md](https://obsidian.md) - for building your Brand Context Vault
- Or any text editor if Obsidian isn't your preference (VS Code, Notepad++, even Notes)

### Before Week 3
- **Claude Code** (free to start) - [claude.com/claude-code](https://claude.com/claude-code) - the harness that runs your weekly report
- A **Composio** account (free tier) - [composio.dev](https://composio.dev) - connects Claude Code to Instagram and Facebook
- An **Instagram Business or Creator account** linked to a **Facebook Page**, under one Meta Business Manager (needed for real data)
- No Docker, no server, no Hermes install

### Before Week 4
- Your Week 3 harness already built (Claude Code + Composio + a weekly schedule)
- No extra install required; Week 4 expands the same system
- Python 3 only if you want to run a small alert wrapper (optional, most students skip it)

---

## Accounts to Create

| Service | Why | When | Cost |
|---------|-----|------|------|
| Claude.ai | Web interface for Claude (you already have this) | Week 2 | $20/mo |
| Claude Code | The local harness that runs your weekly report | Week 3 | Free to start |
| Composio | Connects Claude Code to Instagram Business and your Facebook Page | Week 3 | Free tier |
| honcho.dev | Optional persistent session memory for agents | Week 4 | Free tier available |
| GitHub (optional) | Access course materials, clone example vaults | Any time | Free |

---

## Mindset

This course doesn't assume you can code. It assumes you can:
- **Read** a terminal command (you don't need to write one from scratch)
- **Follow** a folder path (`~/vault/personas/buyer-persona.md`)
- **Edit** a text file
- **Copy and paste** when instructed

If you can do those three things, you have everything you need.

---

## Course Materials

The full course outline and weekly breakdowns are at:
**https://femiofafrica.github.io/ai-automation-course/**

Bookmark this - it's your reference throughout the 4 weeks.
