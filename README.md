# Partner Success Triage Copilot

A single-file, client-side tool that automates a payments support engineer's daily grind. Paste **one ticket** for an instant root cause + resolution + drafted merchant reply, or paste **the day's failed orders** to auto-triage every ticket into a prioritised, escalation-ready queue.

**Live:** https://tiwarivault.github.io/pse-ticket-triage-automator/

## What it does
- **One ticket:** paste an error/symptom → root cause, whose side it's on (customer / merchant-integration / bank-PSP), the resolution, and a ready-to-send **merchant reply**.
- **Daily batch:** upload the day's failed-orders CSV → every ticket is auto-classified and turned into:
  - a **money-weighted priority queue (P1/P2/P3)** — severity × volume, so you work the right thing first
  - **spike / outage detection** — if an issue clusters in one time window (e.g. "MID-not-active spiked at 14:00 for one merchant"), it's flagged as a possible outage to escalate now
  - **per-merchant impact** rollup
  - an **action plan** (do now / escalate / inform)
  - **three auto-drafted responses** per actionable cluster: a **merchant reply**, a **PSP escalation note** and an **internal (Jira-style) ticket**
  - an end-of-day summary + a priority-queue CSV export

## Deterministic engine vs AI layer
The classification, priority scoring, spike detection and drafted artifacts are all **deterministic** — reproducible, not model-generated. The **AI layer is optional** (bring your own Claude key) and sits on top to review the day, tailor a reply, or draft an escalation. In short: the engine triages and prioritises; the AI polishes and reasons.

## Privacy
Everything runs in your browser — the files never leave your machine. AI mode sends only the issue text / triage summary (never credentials or raw customer data).

## Note
Ships with fake sample data only (a planted outage spike for the demo). Portfolio project by Prashant Tiwari (payments support → AI).
