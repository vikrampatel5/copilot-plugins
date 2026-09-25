# Repo Health

## Name

Repo Health

## Description

Repo Health is a GitHub Copilot plugin that reviews a repository's structure,
documentation, development workflow, and Git hygiene, then reports
evidence-based findings and actionable recommendations.

## Capabilities

The `repo-health` skill can:

- Identify the repository's language, framework, package manager, and build system.
- Review README quality and project organization.
- Inspect Git hygiene, including ignored artifacts and committed secrets.
- Find existing build, test, lint, and format commands without inventing commands.
- Run only safe checks already defined by the repository.
- Distinguish confirmed findings from recommendations and cite evidence and file paths.

## Installation

The plugin is available from the
[Vikram Copilot Plugins marketplace](https://github.com/vikrampatel5/copilot-plugins).
When installing from source, use:

```text
https://github.com/vikrampatel5/copilot-plugins
```

The plugin path is:

```text
plugins/repo-health
```

In JetBrains IDEs, open **Settings | Tools | AI Assistant | Skills**, select
**Skills Settings → Manage External Registries**, and add the repository URL.
Install `repo-health` from the discovered skills list at the IDE or Project
scope. The marketplace structure is also available in clients that support
Agent Plugin marketplaces.

## Usage

Ask Copilot:

```text
Review the health of this repository.
```

or:

```text
Use the repo-health skill to audit this repository.
```

## Expected output

The skill returns:

- **Summary**: an overall assessment of repository health.
- **Findings**: prioritized evidence, affected paths, and recommendations.
- **Checks**: only the commands that were actually run and their results.
- **Next steps**: up to three concrete actions.
