# Installation Guide

Chambers of SHB by edenbuilds is designed to be easy to load into common assistant surfaces.

## 1. Local repo setup

```bash
git clone https://github.com/edenbuilds/chambers-of-shb.git
cd chambers-of-shb
uv sync
```

If you want the court-data capability, also install the upstream engine:

```bash
pip install "bharat-courts[ocr,archive]"
```

## 2. Claude Code

Open the repo in the project folder you use for Claude Code and ask it to read:

```text
skills/chambers-shb-orchestrator/SKILL.md
```

For court data, also load:

```text
skills/bharat-courts/SKILL.md
```

If you want the upstream skill installed in a separate folder for a specific matter, run:

```bash
bharat-courts install-skills
```

## 3. Claude Desktop

Use `CLAUDE.md` as the primary entry file and point Claude Desktop at this repo's skill or MCP files.

The local MCP server entry is:

```text
server/main.py
```

## 4. Codex

This repo includes `.codex-plugin/plugin.json`, so you can treat the repo as a local plugin directory.

Start with:

```text
skills/chambers-shb-orchestrator/SKILL.md
```

## 5. ChatGPT and other chat apps

The most reliable approach is:

1. run the local command or server
2. paste the structured output into the chat
3. ask the assistant to summarize, compare, or rewrite

For court research, use `bharat-courts` and paste the JSON output.

## 6. Gemini

Read `GEMINI.md` and use the repository as the prompt pack plus local reference base.

## 7. Public repo publication

If you want this as a public GitHub repository under `edenbuilds`, create or push the GitHub repo at:

```text
https://github.com/edenbuilds/chambers-of-shb
```

The files in this repository are already branded for that destination.
