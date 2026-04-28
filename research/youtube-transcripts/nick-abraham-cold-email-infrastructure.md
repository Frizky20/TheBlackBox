# Nick Abraham: Cold Email Infrastructure and Deliverability

## Source
- Title: `Interview with Nick Abraham on Cold Email`
- Format: video summary / transcript extract
- URL: https://videohighlight.com/v/iRxyDhQ6qDA
- Why this source: high-signal operational detail on inbox setup, warm-up, domain rotation, sending limits, and account hygiene.

## Core Thesis
Nick Abraham's operating model is simple: treat deliverability as an infrastructure game, not just a copywriting game. Instead of trying to rescue every damaged setup, keep excess sending capacity warming in parallel and rotate aggressively when domain reputation drops.

## High-Signal Notes
1. Use `Google Workspace` or `Microsoft` inboxes rather than generic SMTP infrastructure when possible. The source argues these hold up better under modern spam filtering pressure.
2. Run redundant infrastructure. Keep roughly `2x` the domains/inboxes you actively need so one pool can send while another warms as backup.
3. Warm new infrastructure for `2-3 weeks` minimum before expecting production performance.
4. Start conservatively on volume. A working baseline mentioned is around `30 emails per inbox per day`, then increase carefully toward `50` only after positive engagement and stable health.
5. Reputation is increasingly tied to the `domain`, not just the individual inbox. That means domain portfolio management matters more than micro-optimizing one mailbox.
6. Low `bounce rate` and low `spam complaint rate` are treated as hard constraints, not secondary metrics.
7. If an environment underperforms after a campaign cycle, rebuild quickly instead of over-investigating a bad asset.
8. Keep account access stable. Logging into sending accounts from inconsistent locations/IPs can trigger shutdowns.
9. Domain aging matters. Old, generic domains can become a strategic reserve if providers get stricter with brand-new domains.
10. Message quality still matters, but poor infrastructure will cap results even if copy is good.

## Technical Deliverability Takeaways
- Build for replacement, not permanence. A healthy outbound system assumes some domains will decay.
- Separate `warm-up capacity` from `active capacity`.
- Prefer infrastructure that looks operationally normal to mailbox providers.
- Monitor engagement, bounce, and spam signals before increasing throughput.
- Protect admin logins and session consistency as part of deliverability ops.

## Implications for a B2B SaaS Pipeline
- Outbound pipeline quality is constrained by infrastructure quality at the top of funnel.
- Pipeline planning should include a "deliverability budget": spare domains, warm-up time, and inbox replacement cadence.
- Capacity planning should be based on safe inbox-level throughput, not total prospect volume alone.
