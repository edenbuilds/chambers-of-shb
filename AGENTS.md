# Chambers of SHB Agent Instructions

Use `skills/chambers-shb-orchestrator/SKILL.md` as the primary routing and safety policy for all Indian-law work.

Use `skills/bharat-courts/SKILL.md` when the task involves judgments, case status, orders, cause lists, or archival court research.

Use `skills/legal-lens-contract-review/SKILL.md` when the task is contract triage, clause review, or plain-language risk analysis.

## Repository Map

- `agents/`: specialist Indian-law personas.
- `commands/`: slash-command style legal workflows.
- `skills/`: reusable drafting, analysis, calculation, NCLT/NCLAT/IBC, and PDF workflows.
- `protocols/`: protocol reference library by legal domain.
- `company-drafting-agents/`: six-agent company-law drafting pipeline.
- `server/main.py`: local MCP server exposing search, retrieval, drafting, artifact, and DOCX tools.

## Legal Work Rules

- Do not invent law, citations, filing requirements, or facts.
- Flag uncertain/current-law points for verification.
- Use primary/current sources when the task depends on live law or recent amendments.
- Treat all client material as confidential.
- Keep drafts traceable to provided facts and source documents.

## Preferred Flow

1. Classify the legal domain and forum.
2. Load the relevant command, skill, agent, and protocol files.
3. Produce a structured answer or draft.
4. Run a verification pass.
5. Return open issues and filing checks.
