# Repo Health - GitHub Copilot Plugin

A minimal source-loadable [GitHub Copilot CLI](https://docs.github.com/en/copilot/concepts/agents/about-copilot-cli) plugin. It demonstrates the Agent Plugins 1.0 manifest and a portable agent skill.

## Layout

```text
.
├── plugin.json
└── skills/
    └── repo-health/
        └── SKILL.md
```

## Install from source

From this repository:

```powershell
copilot plugin install .
```

Or install it from another directory with an absolute path:

```powershell
copilot plugin install C:\path\to\github-copilot-sample-plugin
```

Verify that it is installed:

```powershell
copilot plugin list
```

Start a new Copilot CLI session, then use the skill explicitly:

```text
Use the /repo-health skill to review this repository.
```

After editing the source plugin, restart the session or reload plugins so Copilot sees the changes. To remove it:

```powershell
copilot plugin uninstall repo-health
```

## Development notes

The plugin intentionally has no pre-approved shell tools. Copilot will request approval before running repository commands, which is safer for a source-loaded example.

The `homepage` and `repository` values in `plugin.json` are placeholders; replace them before publishing.

## License

MIT
