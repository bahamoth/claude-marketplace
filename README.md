# cc-marketplace

A curated collection of Claude Code plugins.

## Usage

```bash
/plugin marketplace add bahamoth/claude-marketplace
```

## Plugins

| Plugin | Description | Source |
|--------|-------------|--------|
| [linear-workflow](https://github.com/bahamoth/claude-linear-workflow) | Linear issue-tracked development workflow | bahamoth/claude-linear-workflow |

## Adding a Plugin

Edit `.claude-plugin/marketplace.json`:

```json
{
  "plugins": [
    {
      "name": "your-plugin",
      "source": {
        "source": "github",
        "repo": "owner/repo"
      },
      "description": "What your plugin does"
    }
  ]
}
```

## Documentation

- [Plugin Marketplaces](https://code.claude.com/docs/en/plugin-marketplaces)
- [Plugins Reference](https://code.claude.com/docs/en/plugins-reference)
