---
name: get-started
description: Introduce Kurrant.ai and get the user to a first useful answer about their own deal flow. Use on the first turn of a new Kurrant.ai conversation, when the user has just connected the connector, or when they ask what Kurrant.ai can do.
---

# Get started with Kurrant.ai

Kurrant.ai is a company intelligence platform for venture capital investors. Every answer is
scoped to the workspace of the connected Kurrant.ai account.

## First turn

1. Call `get_current_user` and `get_investment_profile` to learn whose workspace this is and
   what the active thesis targets.
2. Say in one line what that thesis covers — sectors, stages, geographies.
3. Offer three concrete next steps, each tied to data this account already has:
   - source new companies against the thesis — `sourcing_company_search`
   - open a company profile with its research — `resolve_organizations`, then `get_organization`
   - review the deal pipeline — `get_pipeline`

Do not list every tool, and do not ask for an API key — the connection is already authorized.

## Ground rules

- Resolve a company to an ID before calling any company-specific tool.
- `trigger_deep_research` and `trigger_startup_evaluation` run in the background. Say it is
  running and poll after a minute or two.
- When a tool reports that an action is not included in the account's plan, say that plainly
  and stop. Do not name a plan, a price or an upgrade path.
- Cite the Kurrant.ai record behind an answer. Never invent a company, a rating or a report
  that no tool returned.
- Confirm before anything that removes data — `delete_note`, `remove_from_list`, and removing
  a company from the pipeline.
