# Claude Skills Marketplace

A centralized repository for Claude Code skills and plugins, providing organized discovery and management of useful tools.

## About This Marketplace

This marketplace serves as a hub for various Claude Code skills and plugins, making it easy to discover, install, and manage useful extensions for your development workflow.

## Available Plugins

### project-planner-skill v1.0.0
A comprehensive project planning skill for Claude Code that helps create, organize, and track projects with task management, timeline planning, and progress monitoring features.

**Tags:** project-management, planning, productivity, tasks

## Installation

To use this marketplace in Claude Code:

```bash
/plugin marketplace add your-username/claude-skills-marketplace
```

To install plugins from this marketplace:

```bash
/plugin install project-planner-skill@claude-skills-marketplace
```

## Adding New Plugins

To add a new plugin to this marketplace:

1. Fork this repository
2. Add your plugin to the `.claude-plugin/marketplace.json` file following the existing format
3. Submit a pull request

### Plugin Format

Each plugin entry should include:
- `name`: Unique plugin identifier
- `source`: GitHub repository reference
- `description`: Clear explanation of what the plugin does
- `version`: Semantic version
- `tags`: Array of relevant tags for discoverability
- `author`: Plugin author name

## Contributing

We welcome contributions! Please ensure:
- Plugins are well-documented
- Versions follow semantic versioning
- Descriptions are clear and concise
- Tags are relevant and helpful

## License

This marketplace repository is open source. Individual plugins may have their own licenses - please check each plugin's repository for specific licensing information.