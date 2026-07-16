---
name: legal-lens-contract-review
description: Analyze contracts, notices, and pasted text for Chambers of SHB. Use for risk triage, plain-language summaries, missing-clause checks, jurisdiction/forum checks, deadline extraction, and legal-aid orientation when the user needs a fast contract health check.
---

# Chambers of SHB Contract Review

Use this skill when the user uploads or pastes a contract, notice, email thread, or informal agreement and wants a fast legal triage.

## Operating Rules

1. Extract the parties, document type, governing law, forum, deadlines, payment terms, termination rights, indemnities, IP clauses, and dispute resolution terms.
2. Summarize the document in plain English before giving legal analysis.
3. Assign a simple risk score from 0 to 10:
   - 0 to 2: low risk
   - 3 to 5: moderate risk
   - 6 to 8: serious risk
   - 9 to 10: urgent review needed
4. Flag blanks, inconsistent dates, missing signatures, unsigned annexures, jurisdiction mismatches, automatic renewals, one-sided indemnities, exclusive forum clauses, harsh limitation periods, and hidden assignment / IP transfer terms.
5. If the user asks for a citizen-help answer, include a short legal-aid / DLSA orientation note and tell them to confirm the correct local authority for their jurisdiction.
6. If the text is not in English, translate first and then analyze.
7. Never invent missing facts. If the document omits something material, say exactly what is missing.

## Output Format

Return results in this order:

1. One-sentence plain-English summary.
2. Risk score with one-line rationale.
3. Key clauses and red flags.
4. Missing information and follow-up questions.
5. Practical next steps.

## Suggested Prompts

- "Review this contract for hidden risks and give me a score."
- "Translate this agreement into plain English and flag the bad clauses."
- "Tell me which deadlines and notice periods I need to watch."
- "I need a lawyer-friendly summary and a citizen-friendly summary."

