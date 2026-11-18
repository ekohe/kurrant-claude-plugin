---
name: source-companies
description: Find startups that fit the user's investment thesis on Kurrant.ai, and go deep on the ones worth a second look. Use when the user wants to source or discover companies, asks what matches their thesis, asks for deal flow in a sector or geography, or wants a company researched or evaluated.
---

# Source companies against a thesis

Sourcing on Kurrant.ai runs against an **investment profile** — the saved thesis that defines
sectors, stages and geographies. Search without it and the results are generic.

## Source

1. Call `get_investment_profile` first. If the user describes a thesis that differs from the
   active one, check `list_investment_profiles` for a better fit and offer to
   `switch_investment_profile` rather than searching against the wrong thesis.
2. Call `sourcing_company_search` with the user's constraints on top of the profile.
   `search_organizations` is the plain keyword search — use it only when the user names what
   they want directly and the thesis is irrelevant.
3. Present results as a short table: company, stage, geography, and one line on why it matches.
   Lead with the fit, not the description.

If nothing matches, say so and suggest which constraint to loosen. Do not pad the list with
companies that do not fit.

## Go deep on one company

1. `resolve_organizations` to get the ID. If it returns several candidates, ask which one
   rather than guessing.
2. `get_organization` for the profile. It already includes the deep research report and the
   startup evaluation when they exist, so do not call the other tools first.
3. Only when the report or evaluation is missing:
   - `trigger_deep_research`, then `get_deep_research_report` after a minute or two
   - `trigger_startup_evaluation`, then `get_startup_evaluation`
4. `get_organization_events` and `search_news` for what has happened recently.

Summarize in the investor's terms — what the company does, traction, team, risks against this
thesis. Do not paste the whole report.

## Hand off

When a company is worth tracking, say so and offer the next step: add it to the pipeline
(`add_to_pipeline`), put it on a watchlist (`add_to_list`), or rate it (`rate_organization`).
Make the offer once; do not do it unasked.
