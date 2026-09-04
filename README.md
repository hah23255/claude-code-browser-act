# claude-code-browser-act

A [Claude Code](https://claude.com/claude-code) plugin providing BrowserAct skills for browser automation and reusable website-skill generation via the [`browser-act` CLI](https://pypi.org/project/browser-act-cli/).

Homepage: <https://www.browseract.com>

## Skills

| Skill | Purpose |
|---|---|
| `browser-act` | Runs a browser to extract rendered website data, interact with pages, and capture screenshots. |
| `browser-act-skill-forge` | Creates reusable website automation Skills with browser-act after authorized exploration. |

`browser-act` uses the BrowserAct CLI to extract rendered website data, perform page interactions, and capture screenshots. It loads the matching runtime workflow with:

```bash
browser-act get-skills core --skill-version 2.0.2
```

`browser-act-skill-forge` explores a website's implementation path and generates reusable, site-specific Skill packages. Its `references/` directory is part of the Skill and defines the exploration procedures and output format.

## Requirements

- Python 3.12
- [`uv`](https://docs.astral.sh/uv/)
- `browser-act-cli`

Install the CLI when it is not already available:

```powershell
uv tool install browser-act-cli --python 3.12
```

## Install

Add the marketplace:

```text
/plugin marketplace add browser-act/claude-code-browser-act
```

Then install the plugin:

```text
/plugin install browser-act@browseract
```

## Update

```text
/plugin marketplace update browseract
```

The current plugin version is `0.1.0`. Versioning follows [semver](https://semver.org/) via the `version` field in `plugins/browser-act/.claude-plugin/plugin.json`.

## Repository contents

- `.claude-plugin/marketplace.json` defines the Claude Code marketplace.
- `plugins/browser-act/.claude-plugin/plugin.json` defines the plugin metadata.
- `plugins/browser-act/skills/browser-act/` contains the browser automation Skill.
- `plugins/browser-act/skills/browser-act-skill-forge/` contains the reusable website-Skill generation workflow and its required references.
- `README.md` and `LICENSE` document the package and license.

## License

MIT — see [LICENSE](LICENSE).
