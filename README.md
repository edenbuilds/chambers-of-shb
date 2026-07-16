# Chambers of SHB

Indian legal research, drafting, court-data access, and contract triage in one
portable repo.

Built and maintained by `edenbuilds`.

## What It Does

Chambers of SHB combines three legal workflows into one repository:

- Indian legal drafting and routing
- Indian court-data lookup and research
- Fast contract review and risk triage

It is designed to work as a local prompt pack, skill bundle, and MCP-backed
assistant resource for:

- Claude Code
- Claude Desktop
- Codex
- Gemini
- ChatGPT and other chat apps

## Why It Is Useful

This repo reduces the usual friction of legal assistant setup:

- one place for drafting rules, court data, and research workflows
- one repo that can be loaded into multiple assistants
- plain-language setup instructions for non-technical users
- reusable legal workflows instead of one-off prompts
- court-data support that can handle judgments, case status, orders, and cause
  lists when paired with `bharat-courts`

For legal work, the main value is consistency: the assistant follows the same
routing, citation, and verification rules every time instead of improvising.

## What Is Included

- `skills/chambers-shb-orchestrator/` - primary routing and safety rules for
  Indian legal work.
- `skills/bharat-courts/` - court-data skill for judgments, case status,
  orders, cause lists, and historical archive queries.
- `skills/legal-lens-contract-review/` - contract risk review, plain-English
  summaries, and legal-aid orientation.
- `agents/`, `commands/`, and `protocols/` - the broader Indian-law drafting and
  research library.
- `server/main.py` - local MCP server for search, prompt retrieval, and
  drafting helpers.

## Quick Start

```bash
git clone https://github.com/edenbuilds/chambers-of-shb.git
cd chambers-of-shb
uv sync
```

If you want live and historical Indian court data, install the court engine:

```bash
pip install "bharat-courts[ocr,archive]"
```

## How To Use It

### 1. Open the repo in your assistant workspace

Point your assistant at the repo root.

### 2. Read the main routing skill first

Start with:

```text
skills/chambers-shb-orchestrator/SKILL.md
```

That file tells the assistant how to route Indian-law requests to the correct
agent, command, skill, protocol, or local tool.

### 3. Use the court-data skill when you need Indian case research

Read:

```text
skills/bharat-courts/SKILL.md
```

Use it for:

- finding judgments
- checking live case status
- downloading orders
- getting cause lists
- querying the historical archive

### 4. Use the contract-review skill for quick triage

Read:

```text
skills/legal-lens-contract-review/SKILL.md
```

Use it for:

- contract red-flag review
- plain-English summaries
- deadline extraction
- jurisdiction and forum checks
- missing clause checks

### 5. Use the local MCP server when your assistant supports it

The repo includes `server/main.py` and `.mcp.json`.

That gives compatible assistants access to local tools for:

- protocol search
- command retrieval
- specialist agent lookup
- drafting workflows

## Assistant-Specific Notes

### Claude Code

Load the repo, then tell Claude to read `skills/chambers-shb-orchestrator/SKILL.md`.
For court data, also load `skills/bharat-courts/SKILL.md`.

### Claude Desktop

Use `CLAUDE.md` as the entry file and connect the repo’s local MCP/server
configuration if needed.

### Codex

This repo includes `.codex-plugin/plugin.json`, so it can be used as a local
plugin folder.

### Gemini

Use `GEMINI.md` as the entry file and treat the repo as your local legal
reference base.

### ChatGPT and other chat apps

The most reliable pattern is:

1. run the local tool or server
2. copy the JSON, draft, or extracted text into the chat
3. ask the assistant to summarize, compare, redline, or rewrite

## Example Prompts

```text
Draft a legal notice for breach of contract from these facts.
```

```text
Check limitation, jurisdiction, and maintainability for this dispute.
```

```text
Find the latest Supreme Court judgments on this topic.
```

```text
Review this contract for hidden risks and give me a plain-English summary.
```

```text
Show me the cause list for tomorrow and the latest status of this case.
```

## Safety

This repository is a legal drafting and research aid. It does not replace an
advocate's judgment.

Always verify:

- current statutes and amendments
- court rules and registry practice
- limitation periods
- citations
- fees, affidavits, and annexures
- filing requirements for the relevant forum

## More Setup Notes

For deeper installation instructions and platform-specific notes, see
[docs/install/README.md](docs/install/README.md).

