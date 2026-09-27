<p align="center"><img src="assets/logo-1024.png" alt="Bazous" width="140"></p>

# Bazous for Claude and ChatGPT

[Français](README.fr.md)

**Your household's answers, without having to find the questions.**
Bazous knows the money questions that matter (from experts and from the [community](https://github.com/bazousdotcom/ui)) and answers them with your household's data. These plugins bring those answers, with their pictures, into Claude and ChatGPT.

This repository only holds integrations: manifests, skills and logo. It contains no Bazous application code and no data.

## Install

### Claude Code

```
/plugin marketplace add bazousdotcom/plugins
/plugin install bazous@bazous
```

Then run `/mcp`, pick `plugin:bazous:bazous` and sign in to Bazous in the browser.

### Claude (claude.ai, desktop, mobile)

**Settings → Connectors → Add custom connector**, then:

- Name: `Bazous`
- URL: `https://bazous.com/mcp`

Click **Connect** and authorise access with your Bazous account.

### ChatGPT

In ChatGPT, open **Apps**, search for **Bazous** and click **Connect**. Until the app is listed, a developer can create it with the URL `https://bazous.com/mcp`, OAuth authentication and the icon [`assets/icon-256-chatgpt.png`](assets/icon-256-chatgpt.png) (a PNG under 10 KB, ChatGPT's limit).

Everywhere, sign-in uses your Bazous account (OAuth). The assistant only sees the households your account has access to.

## What the Claude plugin does

| Item | Role |
| --- | --- |
| [`claude/.mcp.json`](claude/.mcp.json) | The Bazous MCP server, `https://bazous.com/mcp` |
| [`household-answers`](claude/skills/household-answers/SKILL.md) | What the household needs to know today, without having to ask: Bazous's answers, most urgent first |
| [`payday-review`](claude/skills/payday-review/SKILL.md) | A review before payday: bills, what is available, the low point |
| [`cashflow-what-if`](claude/skills/cashflow-what-if/SKILL.md) | Simulating a payment moved, added or removed, without saving anything |

Bazous does not connect to your bank accounts automatically, makes no payment and gives no investment advice.

## Contributing

The skills are open: suggest an improvement with a pull request. To add a **question** Bazous answers, head to the kit, [bazousdotcom/ui](https://github.com/bazousdotcom/ui).

## License

MIT, see [LICENSE](LICENSE). The Bazous name and logo are not covered by this license.
