# Chambers of SHB

**Chambers of SHB by Pragadish5207** is a combined legal-assistant repo that pulls together:

- the drafting and routing system from `arya-ai`
- the Indian court-data workflow from `bharat-courts`
- the contract-scanning and legal-aid orientation ideas from Legal-Lens Pro

It is designed to be dropped into Claude Code, Claude Desktop, Codex, Gemini, or any other assistant that can read a prompt pack, a skill bundle, or a local MCP server.

## What Is Included

- `skills/chambers-shb-orchestrator/` - primary routing and safety rules for Indian legal work.
- `skills/bharat-courts/` - court-data skill for judgments, case status, orders, and cause lists.
- `skills/legal-lens-contract-review/` - contract risk triage, plain-language summaries, and legal-aid orientation.
- `commands/`, `agents/`, and `protocols/` - the broader drafting and research library inherited from the original legal pack.
- `server/main.py` - local MCP server for protocol search, prompt retrieval, and drafting helpers.

## Fast Start

```bash
git clone https://github.com/pragadish5207/chambers-of-shb.git
cd chambers-of-shb
uv sync
```

If you want live and historical Indian court data, install the upstream court engine too:

```bash
pip install "bharat-courts[ocr,archive]"
```

That gives the court skill access to live eCourts portals plus the historical archive.

## Add It To Your Assistant

### Claude Code

Open the repo in your work folder and point Claude Code at the repo root. Start with:

```text
Read `skills/chambers-shb-orchestrator/SKILL.md` first.
```

If you also want the court-data helper in a separate project folder, install the upstream skill bundle with:

```bash
bharat-courts install-skills
```

### Claude Desktop

Use the repo as your local skill and MCP source:

```text
Read `CLAUDE.md`
```

Then add the local MCP server from `server/main.py` or use the repo paths directly in the Skills setting.

### Codex

Codex can read the repo as a local plugin folder because it includes `.codex-plugin/plugin.json`.

Open with:

```text
Read `skills/chambers-shb-orchestrator/SKILL.md`
```

### ChatGPT and other chat apps

The most reliable pattern is:

1. run the local tool or MCP server
2. paste the JSON, draft, or extracted text into the chat
3. ask the assistant to summarize, redline, or rewrite

For court searches, the `bharat-courts` CLI plus pasted JSON is the safest path.

### Gemini

Read `GEMINI.md` and use the repo as a prompt pack plus local reference base.

## Platform Guide

For the full step-by-step install instructions, see [docs/install/README.md](docs/install/README.md).

## Why This Repo Exists

Pragadish5207 wanted one public repository that:

1. keeps the Indian-law drafting workflows in one place
2. makes court-data access easy to add to Claude Code, Codex, ChatGPT, Gemini, and Claude
3. keeps contract analysis, legal research, and local MCP support together
4. is easy to publish as a separate public repo under the Pragadish5207 profile

## Safety

This repo is a legal drafting and research aid. It does not replace an advocate's judgment. Verify current statutes, court rules, fees, limitation, citations, and local filing practice before relying on any output.

