# Setup Guide & Prerequisites

**Course:** AI Automation for Marketing Executives
**Format:** 4 live sessions × ~3 hours each

---

## Already Set Up

✅ **Claude account** — You already have this. We'll use Claude.ai (web) and the Claude API during the course.

---

## What to Read Before Week 1

These concepts will come up repeatedly. You don't need to master them — just know what they are so the first session isn't overwhelming.

### 1. Terminal / Command Line

The terminal is how you talk to your computer directly — no mouse, no windows, just text commands. You'll use it to run scripts, install tools, and launch agents.

**What to know:**
- What a terminal is and how to open it (Mac: Spotlight → "Terminal")
- Basic commands: `ls` (list files), `cd` (change directory), `mkdir` (create folder), `pwd` (where am I?)
- Running a command and reading its output
- What "path" means (absolute vs relative paths — `/Users/you/folder` vs `./folder`)

**Resource:** Read the first 5 minutes of any "command line for beginners" guide. That's enough.

### 2. Scripts

A script is a text file containing instructions your computer runs automatically. Like a recipe — a list of steps to follow in order.

**What to know:**
- What a script is (a file with commands that run in sequence)
- The difference between a script and typing commands manually
- Simple script structure: commands, variables (named values like `NAME="Claude"`), comments (notes for humans)
- That scripts can pass data between steps — the output of step 1 becomes the input of step 2

**Resource:** A 5-minute read on what scripts are. No need to write one.

### 3. Markdown

Markdown is a simple way to format text — like Word without the buttons. You'll use it to build your Brand Context Vault (Week 2).

**What to know:**
- Headings: `# Title`, `## Section`, `### Subsection`
- Bold: `**bold text**`
- Lists: `- item` for bullets, `1. item` for numbered
- Links: `[text](url)`
- Code: backticks for inline code, triple backticks for code blocks
- What YAML frontmatter is (the `---` block at the top of a file with metadata)

**Resource:** Read any "markdown cheat sheet" — takes 3 minutes.

### 4. JSON

JSON is how data moves between tools. When Claude talks to n8n, when n8n talks to your CRM, when your agent reads the vault — it's all JSON.

**What to know:**
- What JSON looks like: `{"name": "value", "list": [1, 2, 3]}`
- Key-value pairs
- Arrays (lists in square brackets)
- Objects (groups in curly braces)
- That JSON is just structured data — same as a table or a form

**Resource:** A 3-minute skim of "what is JSON."

### 5. Docker

Docker lets you run software in isolated containers — think of it as a clean, disposable environment that doesn't mess up your computer. n8n runs in Docker.

**What to know:**
- What Docker is and why it's useful (runs software without installing dependencies directly on your machine)
- That you'll install Docker Desktop (free) before Week 3
- The difference between Docker vs. installing software directly

**Resource:** Just understand the concept. Installation instructions will be provided in the course.

### 6. Environment Variables

An environment variable is a named value stored outside your code — like a sticky note on your computer that says "API_KEY = abc123." Your tools read these notes instead of you typing sensitive info directly.

**What to know:**
- What they are (named values your system remembers)
- Why they matter (you store API keys, tokens, and config here — never in your code)
- That you'll set a few during the course (Claude API key, n8n config)

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

Understanding how folders and files are organized — and how tools navigate them via paths — will make Weeks 2–4 smoother.

---

## Software to Install (By Week)

### Before Week 1
- Nothing. Show up with your laptop.

### Before Week 2
- **Obsidian** (free) — [obsidian.md](https://obsidian.md) — for building your Brand Context Vault
- Or any text editor if Obsidian isn't your preference (VS Code, Notepad++, even Notes)

### Before Week 3
- **Docker Desktop** (free for personal use) — [docker.com/products/docker-desktop](https://www.docker.com/products/docker-desktop/)
- A **Claude API key** — [console.anthropic.com](https://console.anthropic.com) — (sign up, add credits, generate a key)

### Before Week 4
- **Python 3** (already installed on most Macs — verify with `python3 --version` in terminal)
- **Hermes Agent** — installed during the session (`pip install hermes-agent`)

---

## Accounts to Create

| Service | Why | When | Cost |
|---------|-----|------|------|
| Claude.ai | Web interface for Claude (you already have this) | ✅ Done | $20/mo |
| Anthropic API | API key for n8n and Hermes integrations | Week 3 | Pay-as-you-go (~$5-10 for the course) |
| Docker Hub | Download Docker Desktop (free account required) | Week 3 | Free |
| honcho.dev | Persistent session memory for agents | Week 4 | Free tier available |
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

Bookmark this — it's your reference throughout the 4 weeks.
