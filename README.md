# Claude Less Market

A marketplace of Claude Code plugins.

## Plugins

| Plugin | Description |
|--------|-------------|
| [spec-driven-dev](plugins/spec-driven-dev/) | A structured workflow for going from idea to implementation — brainstorm, spec, plan, and build step by step. |

## Installation

Add the marketplace and install plugins:

```shell
/plugin marketplace add Ven109/claude-less-market
/plugin install spec-driven-dev@claude-less-market
```

Or add locally for development:

```shell
/plugin marketplace add ./path/to/claude-less-market
```

## Adding a Plugin

Each plugin lives in its own folder under `plugins/` with the following structure:

```
plugins/
└── your-plugin-name/
    ├── .claude-plugin/
    │   └── plugin.json
    ├── skills/
    │   └── your-skill/
    │       └── SKILL.md
    └── README.md
```

The marketplace catalog is defined in `.claude-plugin/marketplace.json`. Add your plugin entry there after creating the plugin directory.
