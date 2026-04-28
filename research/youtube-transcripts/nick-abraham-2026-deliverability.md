# Nick Abraham (2026): Cold Email Deliverability Stack (Timestamped)

## Source
- Video: `Cold Email Deliverability in 2026: The New Rules (Avoid Spam Folders)`
- Published: 2026-02-23
- URL: https://www.youtube.com/watch?v=h2j0gFz9RH4

## Latest 2026 Technical Setup (Timestamped)

### 00:00 — State of cold email in 2026 (what actually broke)
- Deliverability is harder because provider enforcement tightened; Nick uses **open-rate < 40%** as a practical “something is wrong” threshold (DNS, reputation, or warm-up).
- Scale context: mentions managing **~144,000 email accounts** (infrastructure assumptions must include failure + replacement).

### 01:45 — DNS/auth fundamentals (SPF/DKIM/DMARC) that must be correct
- Treat SPF/DKIM/DMARC as *table stakes*; if any are misconfigured, inboxing collapses.
- Practitioner check: **send a test email and inspect headers** *before* launching any campaign.

### 03:20 — Warm-up (why it can hurt you)
- Warm-up minimum Nick recommends: **2 weeks**, but performance improves materially when warm-up is **~1.5 months** (domains “last longer”).
- Tactical implication: if you’re building a long-lived pipeline, pay the warm-up time tax up-front; if you’re under time pressure, compensate with **more redundancy**.

### 05:10 — Volume limits (per domain / per setup)
- He frames volume as downstream of infra quality and targeting/offer performance.
- Keep campaigns **plain text** and avoid practices that create spam-filter signals at scale (he explicitly calls out avoiding open tracking).

### 07:30 — Rotation strategy (domains + inbox groups)
- Run **two sets of infrastructure per client** and rotate monthly (A/B infra pools).
- Use provider tooling to tag inboxes (e.g., Group A / Group B) so you can attribute performance changes to **offer/segment vs infra**.
- Keep a bank of **non-branded backup domains** for emergency swaps when primary infra degrades.

### 09:15 — Repair / replacement (what “fixing deliverability” really means)
- Treat deliverability management as **relentless execution of fundamentals** plus fast removal of underperforming assets.
- List hygiene: validate emails before sending; separate **valid vs catch-all** into different campaigns so a bounce spike doesn’t burn the entire program.
- Targeting hygiene: de-prioritize or isolate contacts behind heavy **email security gateways** (Nick mentions identifying Proofpoint/Barracuda/etc via DNS endpoints and sorting them to the bottom).

## Operator Checklist (Nick-style)
- **Accounts**: prefer Google/Microsoft sending accounts (he states SMTP setups tend to “burn” after major filter updates).
- **Domains**: have spares; age matters; expect burnout and rotate.
- **Warm-up**: 2 weeks minimum; ~6 weeks better.
- **Campaign rules**: plain text, no open tracking, normal business-hour patterns with small randomization, don’t panic-turn-off weekends/holidays if selling SMB/mid-market.
- **Data rules**: validate before launch; split catch-alls; keep bounces low.

## 100Hires Application
100Hires can use this to build an outbound engine that **doesn’t die during scaling**:
- **Reliability**: maintain rotating domain/inbox pools so recruiter outreach keeps landing even when an asset degrades.
- **Quality control**: implement header checks + list validation + catch-all segmentation to protect sender reputation.
- **Pipeline continuity**: “backup infra + swap fast” prevents hiring pipeline stalls during key campaigns (e.g., new client acquisition, new region pushes).
