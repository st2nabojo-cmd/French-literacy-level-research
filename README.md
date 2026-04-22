# Children's Book Research Wiki

A collaborative, LLM-maintained research knowledge base for creating a children's book targeting French readers aged 8–12. Built on the [LLM Wiki pattern](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f) by Andrej Karpathy.

---

## How It Works

You drop raw sources (articles, PDFs, transcripts) into `raw/`. An LLM agent (Claude Code) reads them and compiles a structured, interlinked wiki in `wiki/`. The knowledge compounds — every new source makes the wiki smarter. You never write the wiki yourself; the LLM does all the summarizing, cross-referencing, and bookkeeping.

**Obsidian** is the viewing interface. **Claude Code** is the engine. **The wiki** is the output.

---

## Vault Structure

```
vault/
├── CLAUDE.md                  # Schema — the LLM's operating manual
├── README.md                  # This file
│
├── raw/                       # Layer 1: Immutable sources (NEVER edited by LLM)
│   ├── articles/              #   Blog posts, web clips (markdown)
│   ├── papers/                #   Research papers, academic PDFs
│   ├── transcripts/           #   YouTube/podcast transcripts
│   ├── github/                #   Auto-pulled from collaborators via Git
│   └── assets/                #   Images, diagrams, book covers
│
├── wiki/                      # Layer 2: LLM-generated knowledge (LLM-owned)
│   ├── sources/               #   One summary page per ingested source
│   ├── entities/              #   People, publishers, tools, books
│   ├── concepts/              #   Ideas, theories, techniques
│   ├── comparisons/           #   Side-by-side analyses
│   ├── index.md               #   Master catalog of all pages
│   ├── log.md                 #   Chronological operations record
│   └── overview.md            #   High-level research synthesis
│
├── templates/                 # Page templates (used by the LLM during ingest)
│   ├── source-template.md
│   ├── entity-template.md
│   ├── concept-template.md
│   └── comparison-template.md
│
└── .claude/
    └── commands/              # Slash commands for Claude Code
        ├── ingest.md          #   /ingest <filepath> — process a source
        ├── ingest-github.md   #   /ingest-github — process new Git-pulled files
        ├── query.md           #   /query <question> — ask the wiki
        ├── lint.md            #   /lint — health-check the wiki
        ├── overview.md        #   /overview — regenerate synthesis
        └── save.md            #   /save — persist a query answer as a page
```

---

## Getting Started

### Prerequisites

- [Obsidian](https://obsidian.md/) installed
- [Claude Code](https://docs.anthropic.com/en/docs/claude-code) installed (`npm install -g @anthropic-ai/claude-code`)
- Git installed
- An Anthropic API key set as `ANTHROPIC_API_KEY` in your environment

### Step 1: Open the Vault in Obsidian

Open Obsidian → "Open folder as vault" → select this `vault/` directory.

### Step 2: Configure Obsidian Git Plugin

1. Go to Settings → Community plugins → Browse → search "Obsidian Git" → Install → Enable
2. In Obsidian Git settings:
   - **Auto pull interval (minutes):** `5` (pulls collaborator changes every 5 min)
   - **Auto push interval (minutes):** `10` (pushes your changes)
   - **Pull on startup:** Enabled
   - **Push on save:** Disabled (let the interval handle it)
   - **Commit message format:** `wiki: {{date}} auto-commit`

### Step 3: Connect to GitHub

```bash
cd /path/to/vault
git init
git remote add origin https://github.com/YOUR-ORG/YOUR-REPO.git
git add .
git commit -m "init: vault structure"
git push -u origin main
```

### Step 4: Start Claude Code

```bash
cd /path/to/vault
claude
```

Claude Code will read `CLAUDE.md` automatically. You're ready to go.

---

## Daily Workflow

### Adding a source yourself

1. Save the file into the appropriate `raw/` subfolder
2. In Claude Code: `/ingest raw/articles/my-article.md`
3. Claude processes it, creates wiki pages, updates the index

### When a collaborator pushes a source

1. Obsidian Git auto-pulls the new file into `raw/github/`
2. In Claude Code: `/ingest-github`
3. Claude finds and processes all new files

### Asking a research question

```
/query What vocabulary level is appropriate for 10-year-old French readers?
```

Claude searches the wiki and synthesizes an answer with citations.

### Maintaining wiki health

```
/lint
```

Claude reports contradictions, orphan pages, stale content, and research gaps.

---

## For Collaborators

If you're contributing sources to this wiki:

1. Clone the repo: `git clone https://github.com/YOUR-ORG/YOUR-REPO.git`
2. Add your files to `raw/github/` — any format works (PDF, markdown, text, URLs in a .md file)
3. Commit and push:
   ```bash
   git add raw/github/
   git commit -m "add: [brief description of source]"
   git push
   ```
4. The wiki maintainer will run `/ingest-github` to process your contribution

**Rules:**
- Never edit anything in `wiki/` — that's the LLM's domain
- Never edit anything already in `raw/` — sources are immutable
- Only add NEW files to `raw/github/`

---

## Recommended Obsidian Plugins

- **Obsidian Git** — GitHub sync (required)
- **Dataview** — query frontmatter across pages (tables, lists)
- **Graph View** (built-in) — visualize wiki connections
- **Web Clipper** (browser extension) — save web articles as markdown directly to `raw/articles/`
- **Templater** — use the templates in `templates/` when manually creating pages

---

## Research Themes

1. **Creative AI Writing in French** — LLM capabilities, stylistic control, failure modes
2. **Literacy Levels in France (8–12)** — benchmarks, vocabulary, curriculum standards
3. **What Makes a Children's Book** — genre conventions, structure, illustration
4. **How Children Learn Through Storybooks** — pedagogy, cognitive development
5. **Market & Publishing** — publishers, trends, comparable titles
