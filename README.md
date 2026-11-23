# Kurrant.ai

Company intelligence for venture capital investors, in a conversation with Claude.

[Kurrant.ai](https://www.kurrant.ai) is a company intelligence platform for venture capital
investors. This plugin connects Claude to your Kurrant.ai workspace and teaches it how to
work the way an investor does: source startups against your investment thesis, open a full
company profile with its deep research report and startup evaluation, and keep your deal
pipeline, watchlists, ratings and notes up to date without leaving the conversation.

## What you get

- **A connector** to the Kurrant.ai MCP server, which gives Claude your workspace's tools
- **Skills** that tell Claude when and how to use those tools — which one to reach for,
  what order to call them in, and what a good answer looks like

## Install

In Claude Code 2.1.275 or later:

```
/plugin install kurrant-ai --marketplace ekohe/kurrant-claude-plugin
```

## Use it

Add the plugin, then connect the Kurrant.ai connector from the plugin's **Connectors** tab
and sign in with your Kurrant.ai account. Claude then works inside that account's workspace.

Things to ask for:

- "Find seed-stage fintech startups in Japan that match my investment thesis."
- "Show me the full Kurrant.ai profile for ElevenLabs, including the deep research report."
- "What is in my pipeline right now?"
- "Add ElevenLabs to my AI watchlist and rate it love."

## Requirements

A Kurrant.ai account on a paid plan. Sign up at [kurrant.ai](https://www.kurrant.ai).

## Data

The plugin itself stores nothing and contains no credentials. Your prompts and the tool
arguments Claude generates are sent to the Kurrant.ai MCP server at `app.kurrant.ai`, which
answers from your own workspace and records the call for auditing. Everything Claude can
read or change is scoped to the connected account — the plugin cannot do anything that
account cannot already do on the platform. See the
[privacy policy](https://www.kurrant.ai/en/privacy) and the
[terms of service](https://www.kurrant.ai/en/terms).

## Support

[kurrant.ai/en/contact](https://www.kurrant.ai/en/contact)
