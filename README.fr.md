<p align="center"><img src="assets/logo-1024.png" alt="Bazous" width="140"></p>

# Bazous pour Claude et ChatGPT

[English](README.md)

**Les réponses de ton foyer, sans avoir à trouver les questions.** · [▶ Regarde la démo (2 min)](https://bazous.com/fr/demo)
Bazous connaît les questions d’argent qui comptent (celles de l’expertise et de la [communauté](https://github.com/bazousdotcom/ui)) et y répond avec les données de ton foyer. Ces plugins apportent ces réponses dans Claude et ChatGPT.

Ce dépôt ne contient que des intégrations : manifestes, skills et logo. Il ne contient aucun code de l’application Bazous, et aucune donnée.

## Installer

### Claude Code

```
/plugin marketplace add bazousdotcom/plugins
/plugin install bazous@bazous
```

Lance ensuite `/mcp`, choisis `plugin:bazous:bazous` et connecte-toi à Bazous dans le navigateur.

### Claude (claude.ai, desktop, mobile)

**Paramètres → Connecteurs → Ajouter un connecteur personnalisé**, puis :

- Nom : `Bazous`
- URL : `https://bazous.com/mcp`

Clique sur **Se connecter** et autorise l’accès avec ton compte Bazous.

### ChatGPT

Dans ChatGPT, ouvre **Apps**, cherche **Bazous** et clique sur **Connecter**. Tant que l’app n’est pas listée, un développeur peut la créer avec l’URL `https://bazous.com/mcp`, l’authentification OAuth et l’icône [`assets/icon-256-chatgpt.png`](assets/icon-256-chatgpt.png) (PNG de moins de 10 Ko, la limite de ChatGPT).

Partout, la connexion utilise ton compte Bazous (OAuth). L’assistant ne voit que les foyers auxquels ton compte a accès.

## Ce que fait le plugin Claude

| Élément | Rôle |
| --- | --- |
| [`claude/.mcp.json`](claude/.mcp.json) | Serveur MCP Bazous `https://bazous.com/mcp` |
| [`household-answers`](claude/skills/household-answers/SKILL.md) | Ce que le foyer doit savoir aujourd’hui, sans avoir à poser la question : les réponses de Bazous, le plus urgent d’abord |
| [`payday-review`](claude/skills/payday-review/SKILL.md) | Revue avant le salaire : factures, disponible, point bas |
| [`cashflow-what-if`](claude/skills/cashflow-what-if/SKILL.md) | Simulation d’un paiement déplacé, ajouté ou retiré, sans rien enregistrer |

Bazous n’accède pas automatiquement à tes comptes bancaires, n’exécute aucun paiement et ne donne pas de conseil en investissement.

## Contribuer

Les skills sont ouvertes : propose une amélioration par pull request. Pour ajouter une **question** à laquelle Bazous répond, c’est dans le kit [bazousdotcom/ui](https://github.com/bazousdotcom/ui).

## Licence

MIT, voir [LICENSE](LICENSE). Le nom et le logo Bazous ne sont pas couverts par cette licence.
