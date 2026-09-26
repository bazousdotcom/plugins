<p align="center"><img src="assets/logo-1024.png" alt="Bazous" width="140"></p>

# Bazous pour Claude et ChatGPT

**Les réponses de votre foyer, sans avoir à trouver les questions.**
Bazous connaît les questions d’argent qui comptent (celles de l’expertise et de la [communauté](https://github.com/bazousdotcom/ui)) et y répond avec les données de votre foyer. Ces plugins apportent ces réponses dans Claude et ChatGPT.

Ce dépôt ne contient que des intégrations : manifestes, skills et logo. Il ne contient aucun code de l’application Bazous, et aucune donnée.

## Installer

### Claude Code

```
/plugin marketplace add bazousdotcom/plugins
/plugin install bazous@bazous
```

Lancez ensuite `/mcp`, choisissez `plugin:bazous:bazous` et connectez-vous à Bazous dans le navigateur.

### Claude (claude.ai, desktop, mobile)

**Paramètres → Connecteurs → Ajouter un connecteur personnalisé**, puis :

- Nom : `Bazous`
- URL : `https://bazous.com/mcp`

Cliquez sur **Se connecter** et autorisez l’accès avec votre compte Bazous.

### ChatGPT

Dans ChatGPT, ouvrez **Apps**, cherchez **Bazous** et cliquez sur **Connecter**. Tant que l’app n’est pas listée, un développeur peut la créer avec l’URL `https://bazous.com/mcp`, l’authentification OAuth et l’icône [`assets/icon-256-chatgpt.png`](assets/icon-256-chatgpt.png) (PNG de moins de 10 Ko, la limite de ChatGPT).

Partout, la connexion utilise votre compte Bazous (OAuth). L’assistant ne voit que les foyers auxquels votre compte a accès.

## Ce que fait le plugin Claude

| Élément | Rôle |
| --- | --- |
| [`claude/.mcp.json`](claude/.mcp.json) | Serveur MCP Bazous `https://bazous.com/mcp` |
| [`household-answers`](claude/skills/household-answers/SKILL.md) | Ce que le foyer doit savoir aujourd’hui, sans avoir à poser la question : les réponses de Bazous, le plus urgent d’abord |
| [`payday-review`](claude/skills/payday-review/SKILL.md) | Revue avant le salaire : factures, disponible, point bas |
| [`cashflow-what-if`](claude/skills/cashflow-what-if/SKILL.md) | Simulation d’un paiement déplacé, ajouté ou retiré, sans rien enregistrer |

Bazous n’accède pas automatiquement à vos comptes bancaires, n’exécute aucun paiement et ne donne pas de conseil en investissement.

## Contribuer

Les skills sont ouvertes : proposez une amélioration par pull request. Pour ajouter une **question** à laquelle Bazous répond, c’est dans le kit [bazousdotcom/ui](https://github.com/bazousdotcom/ui).

## Licence

MIT, voir [LICENSE](LICENSE). Le nom et le logo Bazous ne sont pas couverts par cette licence.

---

## English

**Your household's answers, without having to find the questions.** Bazous knows the money questions that matter, from experts and the [community](https://github.com/bazousdotcom/ui), and answers them with your household's data. These plugins bring those answers into Claude and ChatGPT. This repository only holds integrations (manifests, skills, logo), no Bazous application code and no data.

- **Claude Code**: `/plugin marketplace add bazousdotcom/plugins`, then `/plugin install bazous@bazous`, then `/mcp` to sign in.
- **Claude apps**: Settings → Connectors → Add custom connector → `https://bazous.com/mcp`.
- **ChatGPT**: Apps → Bazous → Connect.

MIT licensed; the Bazous name and logo are not.
