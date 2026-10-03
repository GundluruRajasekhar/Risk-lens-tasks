# RiskLens tasks

## Phase 1: Prototype (done)
- [x] Single-file app with signal feed and question box
- [x] Keyword intent routing for fraud, AML, liquidity, credit, capital
- [x] Sample data and named rules (R-F, R-A series)
- [x] STR draft narratives
- [x] Audit record with SHA-256 hash, JSON download, print
- [x] Requirements, readme, task plan

## Phase 2: Real data and rules
- [ ] Define data contracts for transactions, KYC, ALM buckets, loan book, capital register
- [ ] Connect to a read-only data source (CSV or database first, then streams)
- [ ] Move rules into versioned config with owner and effective date
- [ ] Validate thresholds with compliance (structuring limits, LCR minimums, STR criteria)
- [ ] Track false-positive rate per rule

## Phase 3: LLM layer
- [ ] Replace keyword matcher with an LLM that calls approved tools only
- [ ] Keep all numbers in deterministic code, never model output
- [ ] Mask PII before any prompt
- [ ] Add a test set of 50+ questions with expected answers
- [ ] Refuse and log questions outside scope

## Phase 4: Audit and control
- [ ] Store audit records in an append-only log
- [ ] Record rule version and data snapshot ID in each record
- [ ] Add login and roles (analyst, reviewer, auditor)
- [ ] Add maker-checker approval before any regulatory submission
- [ ] Add an auditor view that replays any output from its record

## Phase 5: Regulatory outputs
- [ ] FIU-IND STR in the official file format
- [ ] Basel capital and liquidity return templates
- [ ] RBI asset classification and provisioning reports
- [ ] Scheduled reports with sign-off trail

## Phase 6: Launch
- [ ] Security review and penetration test
- [ ] Pilot with one team (suggest fraud analysts)
- [ ] Measure STR drafting time before and after
- [ ] Collect feedback, then expand to ALM and credit
