---
name: deal-pipeline
description: Review and update the Kurrant.ai deal pipeline, watchlists, ratings and notes. Use when the user asks what is in their pipeline, wants to move a deal between stages, add or remove a company from a list, rate a company, or write up a meeting or call.
---

# Work the pipeline

The pipeline, lists, ratings and notes all belong to the connected workspace and are shared
with the team.

## Review

`get_pipeline` returns every card with its current rating, the last team note and the most
recent headline — one call, no follow-ups needed for a review. Filter by stage when the user
names one: `new`, `active`, `diligence`, `won`, `missed`, `passed`.

Group by stage and lead with what changed or what is stalling. Do not dump every field.

## Update

Resolve the company first with `resolve_organizations`, then:

- `add_to_pipeline` to start tracking a deal
- `update_pipeline_card` to move a stage or change the card
- `rate_organization` to set a rating, `get_organization_rating` to read the current one

Confirm the stage change back to the user in one line, naming the company and the new stage.

## Lists

`list_my_lists` for what exists, `get_list_organizations` for one list's contents,
`add_to_list` and `remove_from_list` to change it, `create_list` for a new one.

Check `list_my_lists` before creating — the list the user means usually exists under a
slightly different name. Confirm before `remove_from_list`.

## Notes

`get_organization_notes` to read, `add_organization_note` to write, `update_note` to revise,
`delete_note` to remove.

When the user recounts a meeting or a call, offer to write it up as a note and show the text
before saving it. A note is for the team, so write it as a record, not as a chat reply.
Confirm before `delete_note`, and remember a user can only delete notes they authored.

## Reporting

`get_quarterly_summary` for one period, `list_reporting_summaries` for what exists,
`generate_quarterly_reports` and `refresh_quarterly_report` to produce or rebuild one. These
run in the background — say so and check back rather than waiting.
