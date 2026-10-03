# RiskLens: Risk and Regulatory Copilot

A prototype copilot for Banking and NBFC teams. Ask a question in plain language and get fraud, AML, liquidity, credit and capital answers with an audit record attached.

## What it does

- **Signal feed:** ranked fraud, AML, liquidity, credit and capital alerts.
- **Natural language questions:** "Show suspicious transactions above 10 lakh", "Draft an STR for structuring cases", "What is our LCR?"
- **Explained flags:** each transaction shows the rule that triggered it.
- **Audit-ready output:** every answer carries an ID, timestamp, question, rules, data source and SHA-256 hash. Download as JSON or print.

## Run it

No install needed. Open `index.html` in a browser.

## Files

| File | Purpose |
|---|---|
| `index.html` | The working app (single file, no dependencies) |
| `requirements.html` | Users, functional and non-functional requirements |
| `readme.md` | This file |
| `tasks.md` | Build plan and checklist |

## How it works

1. A keyword matcher maps your question to a risk domain.
2. Deterministic functions compute the answer from sample data.
3. The app builds an audit record and hashes it with the Web Crypto API.

## Limits of this prototype

- All data is fake sample data defined in `index.html`.
- Question matching is keyword based, not an LLM.
- Regulatory thresholds are illustrative. Confirm with compliance.
- The hash proves a record was not changed after creation, but it is not stored anywhere. Production needs an immutable log.
- STR drafts are for analyst review. Nothing is filed.

## Next step: production architecture

Core banking and transaction streams feed a rules and metrics engine. An LLM turns questions into calls to approved tools only, so numbers always come from deterministic code. Outputs go through maker-checker approval and are written to an append-only audit store.
