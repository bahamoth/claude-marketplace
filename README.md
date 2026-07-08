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
| [fact-checker](https://github.com/bahamoth/claude-fact-checker) | Automatic and manual document fact-checking against codebase and external sources | bahamoth/claude-fact-checker |
| [dev-tools](https://github.com/bahamoth/cc-dev-tools) | Modern development conventions and toolchain enforcement — Python, Rust, TypeScript and more | bahamoth/cc-dev-tools |
| [nc-pptx-theme](https://github.com/bahamoth/claude-nc-pptx-theme) | Generate NC(NCSOFT) branded PPTX presentations with CI-compliant colors, fonts, and layouts | bahamoth/claude-nc-pptx-theme |
| [tone-fix](https://github.com/bahamoth/tone-fix) | Remove AI-sounding phrasing and translationese from Korean documents, infographics, and slide decks | bahamoth/tone-fix |

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
