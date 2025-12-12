# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

**cc-marketplace** is a Claude Code plugin metadata registry. It manages both first-party plugins and third-party contributions from the community.

Official documentation: https://code.claude.com/docs/en/plugin-marketplaces

## Plugin Metadata Management

Metadata is managed in `.claude-plugin/marketplace.json`.

### marketplace.json Schema

```json
{
  "name": "cc-marketplace",
  "owner": {
    "name": "<owner-name>",
    "email": "<optional-email>",
    "url": "<optional-url>"
  },
  "plugins": [...]
}
```

### Plugin Entry Schema

Each plugin entry requires `name` and `source`. Other fields are optional.

```json
{
  "name": "<plugin-name>",
  "source": "<source-object-or-path>",
  "description": "<concise description>",
  "version": "<optional>",
  "author": { "name": "<name>", "email": "<email>", "url": "<url>" },
  "category": "<optional>",
  "tags": ["<optional>"],
  "strict": true
}
```

### Source Types

The `source` field varies by type:

**GitHub** (for GitHub repositories):
```json
{
  "source": {
    "source": "github",
    "repo": "owner/repository"
  }
}
```

**Git** (for GitLab, Gitea, self-hosted Git):
```json
{
  "source": {
    "source": "git",
    "url": "https://gitlab.com/team/plugin.git"
  }
}
```

**Local path** (for development only):
```json
{
  "source": "./plugins/my-plugin"
}
```

### Marketplace-Specific Fields

- `strict`: When `true` (default), marketplace entry supplements the plugin's own manifest. When `false`, marketplace entry serves as the complete manifest if no plugin.json exists
- `category`: Plugin classification
- `tags`: Array of tags for discoverability

## Writing Plugin Descriptions

- **Single line**: Explain only what the plugin does
- **Action-oriented**: Use patterns like "Generate ~", "Automate ~", "Integrate ~"
- **Be specific**: Name the target service or technology (e.g., "Linear", "GitHub", "Slack")
- **No redundancy**: Don't repeat information already in the plugin name

Good examples:
- `"Linear issue-tracked development workflow"`
- `"Generate complete API endpoints with tests and docs"`
- `"GitHub PR review automation with AI feedback"`

Bad examples:
- `"A plugin for linear"` (too vague)
- `"This is a workflow plugin"` (not specific)

## Writing Plugin README.md

Each plugin repository should include a README.md with the following structure:

### Required Sections

1. **Title and one-line description**: Plugin name with the same description from marketplace.json
2. **Installation**: Commands to install the plugin in Claude Code
3. **Usage**: Basic usage examples and key commands
4. **Configuration**: Required environment variables or API key setup

### Optional Sections (when applicable)

- **Requirements**: External services or accounts needed
- **Examples**: Real-world usage scenarios
- **Limitations**: Known constraints or caveats

### README Writing Principles

- Enable users to go from installation to first use within 5 minutes
- Provide copy-pasteable commands in code blocks
- Use screenshots or GIFs only for demonstrating core features
- Minimize unnecessary badges or decorations

## Keeping Documentation in Sync

When adding or removing plugins in `marketplace.json`, always update the "Plugins" section in `README.md` to reflect the current plugin list.
