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

JetBrains AI Assistant currently consumes the skill in this repository through
an external skill registry. In **Settings | Tools | AI Assistant | Skills**,
open **Skills Settings → Manage External Registries**, add this repository, and
then install the `repo-health` skill from the list:

```text
https://github.com/vikrampatel5/copilot-plugins
```

Choose the IDE or Project installation scope as appropriate. Do not use
**Install Plugin from Source** in the JetBrains GitHub Copilot plugin; that
route does not load this marketplace manifest.

### VS Code

Open **GitHub Copilot → Agent Plugins** and add the marketplace or source
repository above.

### Copilot CLI

The repository is a root plugin, so it can be installed directly:

```powershell
copilot plugin install https://github.com/vikrampatel5/copilot-plugins
```

For a local checkout, use the repository root:

```powershell
copilot plugin install "C:\Users\vikra\IdeaProjects\github-copilot-sample-plugin"
```

The same checkout can also be registered as a marketplace:

```powershell
copilot plugin marketplace add "C:\Users\vikra\IdeaProjects\github-copilot-sample-plugin"
copilot plugin install repo-health@vikram-copilot-plugins
```

## Adding future plugins

1. Add a directory under `plugins/<plugin-name>/`.
2. Add its `plugin.json`, README, and plugin-specific skills.
3. Register the plugin in `.github/plugin/marketplace.json` with a relative
   `source` path.
4. Keep plugin files self-contained and document safe usage and checks.

## License

MIT
