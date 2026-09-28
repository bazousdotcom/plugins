<p align="center"><img src="assets/logo-1024.png" alt="Bazous" width="140"></p>

# Bazous for Claude and ChatGPT

[Français](README.fr.md)

**Your household's answers, without having to find the questions.** · [▶ Watch the 2-minute demo](https://bazous.com/demo)
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

Bazous is in review for Claude's connector directory. Until it is listed, add it yourself: **Settings → Connectors → Add custom connector**, then:

- Name: `Bazous`
- URL: `https://bazous.com/mcp`

Click **Connect** and authorise access with your Bazous account.

### ChatGPT

Bazous is in review for ChatGPT's app directory. Until it is listed, turn on developer mode in ChatGPT and create an app with the URL `https://bazous.com/mcp`, OAuth authentication and the icon [`assets/icon-256-chatgpt.png`](assets/icon-256-chatgpt.png) (a PNG under 10 KB, ChatGPT's limit). Once it is approved, open **Apps**, search for **Bazous** and click **Connect**.

Everywhere, sign-in uses your Bazous account (OAuth). The assistant only sees the households your account has access to.

## What the Claude plugin does

| Item | Role |
| --- | --- |
| [`claude/.mcp.json`](claude/.mcp.json) | The Bazous MCP server, `https://bazous.com/mcp` |
| [`household-answers`](claude/skills/household-answers/SKILL.md) | What the household needs to know today, without having to ask: Bazous's answers, most urgent first |
| [`payday-review`](claude/skills/payday-review/SKILL.md) | A review before payday: bills, what is available, the low point |
| [`cashflow-what-if`](claude/skills/cashflow-what-if/SKILL.md) | Simulating a payment moved, added or removed, without saving anything |

Bazous does not connect to your bank accounts automatically, makes no payment and gives no investment advice.

## Learn more

- [Documentation](https://bazous.com/docs): the access Bazous asks for, its nine tools and questions to try
- [Budgeting apps you can use inside ChatGPT and Claude](https://bazous.com/guides/budgeting-in-chatgpt-and-claude): a dated, sourced comparison, Bazous included
- Official MCP registry: `com.bazous/bazous`

## Contributing

The skills are open: suggest an improvement with a pull request. To add a **question** Bazous answers, head to the kit, [bazousdotcom/ui](https://github.com/bazousdotcom/ui).

## License

MIT, see [LICENSE](LICENSE). The Bazous name and logo are not covered by this license.
