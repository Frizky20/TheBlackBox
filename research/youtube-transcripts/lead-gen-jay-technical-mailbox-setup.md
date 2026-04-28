# Lead Gen Jay: Cold Email Mailbox Setup (Practitioner Breakdown, Timestamped)

## Source
- Video: `How I Setup My Cold Email Mailboxes [Makes Me $600K/mo]`
- URL: https://www.youtube.com/watch?v=DJbLvafsCx4
- Note: Published 2024-06-14; the mechanics below are still directly applicable to operating outbound in 2026 (providers changed, but the infra constraints did not).

## Latest “2026-usable” Technical Setup (Timestamped)

### 00:00 — The hierarchy: server → domain → mailbox (what you’re really buying)
- Deliverability is constrained top-down:
  - **Server/IP reputation** (Google/Microsoft vs fresh VPS/AWS servers)
  - **Domain reputation + age** (he calls out ≥ 30 days domain age as a baseline)
  - **Mailbox reputation**
- Tactical idea: diversify domains/mailboxes so a single failure doesn’t nuke throughput.

### 01:30 — Domain buying strategy (reputation + operational control)
- Prefer buying domains in ways that preserve trust and controllability.
- Practitioner baseline: buy **many domains** (portfolio mindset) vs betting on one.

### 03:30 — DNS records that maximize trust (SPF / DKIM / DMARC)
- Treat DNS authentication as non-negotiable: SPF, DKIM, DMARC must be correct.
- He emphasizes “one wrong setting and everything lands in spam” → operationalize a repeatable DNS checklist.

### 06:00 — Mailbox provider selection (Google vs Microsoft vs mailbox automation)
- Provider matching matters: **Google tends to deliver better to Google**, Microsoft to Microsoft.
- Cautions against “mailbox automation” vendors that spin up fresh VPS/AWS servers:
  - cheap + easy, but lower trust; beginners burn infra fast.
  - one bad campaign can blacklist the underlying server and cascade failures across dependent domains.

### 08:00 — Account configuration (tracking domains + sending behavior)
- Key operational requirement: **custom tracking domain** if you ever track or include unsubscribe/link tracking (otherwise the default tracking domain is an instant cold-email tell).
- Sending behavior must look human: time gaps, ramping, and conservative per-mailbox limits.

### 10:00 — Warm-up timeline (domain age + mailbox warm-up)
- Warm domains/mailboxes for weeks; don’t rush a brand new domain into production.
- Treat warm-up as risk reduction, not a nice-to-have.

### 12:00 — Connecting to Instantly (how infra meets campaigns)
- Infrastructure should be easy to move between sending tools (avoid vendor lock-in where possible).
- Ensure your infra provider gives you ownership/control of domains + mailbox credentials.

### 14:00 — Sending limits + rotation (what prevents spam folder death)
- Keep daily volumes per mailbox conservative; rotate across mailboxes/domains.
- If a domain/mailbox degrades, remove it from rotation quickly to protect the rest of the pool.

### 16:00 — Scaling to 50+ mailboxes (portfolio math)
- Scaling is mainly:
  - more domains
  - more mailboxes
  - tighter list hygiene
  - stricter sending constraints
- You scale by adding infra, not by pushing unsafe volume through fewer assets.

### 17:30 — Common mistakes (what burns the whole program)
- Using low-trust server infrastructure (fresh VPS/AWS) with weak list/copy control.
- Skipping domain age/warm-up, misconfiguring DNS, over-sending early.

## Practitioner Defaults (copy/paste into SOP)
- **Domain age**: prefer ≥ 30 days before serious volume.
- **DNS**: SPF/DKIM/DMARC verified on every domain.
- **Tracking**: custom tracking domain if any tracking/unsub links are used.
- **Volumes**: conservative per mailbox; scale by adding mailboxes/domains.
- **Rotation**: treat domains as consumables; remove degraded ones quickly.

## 100Hires Application
100Hires can use this to run outreach that stays deliverable while scaling:
- **Infrastructure discipline**: portfolio of domains/mailboxes prevents a single deliverability event from stopping recruiter outreach.
- **Regional scaling readiness**: provider-matching + rotation helps when expanding into markets where Outlook/Google mix differs.
- **Operational safety**: DNS + tracking-domain SOP reduces silent deliverability failure that would otherwise destroy pipeline throughput.
