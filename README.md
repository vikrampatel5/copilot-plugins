#Copilot Plugins

This repository is a GitHub Copilot Agent Plugin marketplace by Vikram Patel.
It contains installable plugins that extend Copilot with reusable skills for
repository and development workflows.

## Marketplace structure

The marketplace definition is at `.github/plugin/marketplace.json`. Plugins
live under `plugins/` and keep their manifests, documentation, and skills
together:

```text
.github/plugin/marketplace.json
plugins/
└── repo-health/
    ├── plugin.json
    ├── README.md
    └── skills/
        └── repo-health/
            └── SKILL.md
```

## Available plugins

### repo-health

Reviews repository structure, documentation, Git hygiene, project tooling, and
safe existing checks, then reports confirmed findings separately from
recommendations.

See [the plugin documentation](plugins/repo-health/README.md) for capabilities,
installation, and usage.

## Installation

### JetBrains IDE

In **GitHub Copilot → Agent Customizations → Plugins**, choose **Install Plugin
from Source** and select or enter this repository:

```text
https://github.com/vikrampatel5/copilot-plugins
```

### VS Code

Open **GitHub Copilot → Agent Plugins** and add the marketplace or source
repository above.

### Copilot CLI

Install the source repository with the Copilot CLI:

```powershell
copilot plugin install https://github.com/vikrampatel5/copilot-plugins
```

For a local checkout, use the repository path instead:

```powershell
copilot plugin install .
```

## Adding future plugins

1. Add a directory under `plugins/<plugin-name>/`.
2. Add its `plugin.json`, README, and plugin-specific skills.
3. Register the plugin in `.github/plugin/marketplace.json` with a relative
   `source` path.
4. Keep plugin files self-contained and document safe usage and checks.

## License

MIT
