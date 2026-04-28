# Eric Nowoslawski: Step-by-Step Clay Workflow (Programmatic Enrichment)

## The Clay Workflow (operator-grade, step-by-step)

### Step 0 — Decide the “why them” signal (before you touch Clay)
- Pick 1–2 triggers to drive the entire build (examples: hiring for RevOps, new region page, pricing change, tech install).
- Output: a single sentence hypothesis: “If they have X, they likely need Y.”

### Step 1 — Seed list (accounts + personas)
- Import accounts from Apollo/CSV/CRM, or build inside Clay with a basic ICP filter.
- Add personas (titles) and keep role scope tight (e.g., Head of HR, People Ops, Talent).

### Step 2 — Normalize company + person fields
- Clean company names, website domains, and LinkedIn URLs.
- Normalize titles (CEO vs Chief Executive Officer) so personalization tokens don’t look robotic.

### Step 3 — Enrich firmographics (only what you’ll use)
- Add: headcount range, location, industry, funding stage, hiring velocity.
- Don’t enrich vanity fields unless they connect to the hypothesis.

### Step 4 — Trigger scraping (the “programmatic” part)
- Scrape pages that validate the trigger:
  - careers page (role hiring + location)
  - product/pricing page (plan changes)
  - integration/stack pages (tool adoption)
  - newsroom (announcements)
- Convert scrape output into structured fields (boolean triggers + short evidence strings).

### Step 5 — Verify contactability + risk
- Run email verification and store: valid / risky / catch-all.
- Route catch-alls to a separate sending pool (protects bounce rate).

### Step 6 — Generate a 1-line hook (constraint-driven)
- Use a strict template to avoid “AI SDR voice”:
  - “Saw {trigger evidence}. Usually teams do that to {initiative}. Curious if {pain} is on your radar?”
- Limit to 1–2 variables and cap token length.

### Step 7 — Create 2–3 angle variants (A/B/C)
- Angle A: pain/risk
- Angle B: speed/efficiency
- Angle C: compliance/trust (region-specific)
- Store each as separate fields so sending tools can test cleanly.

### Step 8 — QA gates (before export)
- Reject rows when:
  - key trigger evidence is missing
  - hook exceeds length threshold
  - token values look unnatural (ALL CAPS names, broken titles, etc.)

### Step 9 — Export to sending tool with deterministic mapping
- Export with fixed column names that match your sending tool variables.
- Keep one spreadsheet/schema per campaign so future updates don’t break tokens.

## 100Hires Application
100Hires can use this Clay workflow to generate *higher-quality* outbound at scale:
- **Better targeting**: trigger scraping creates “why now” relevance for HR buyers (hiring surge, expansion, compliance changes).
- **Deliverability protection**: catch-all routing + verification reduces bounces and preserves domain health.
- **Repeatability**: QA gates + deterministic exports prevent broken personalization from tanking reply rates and reputation.
