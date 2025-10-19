# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Claude Skills Marketplace repository that serves as a centralized hub for Claude Code skills and plugins. The marketplace makes it easy to discover, install, and manage useful extensions for development workflows.

## Repository Structure

- `.claude-plugin/marketplace.json`: Main marketplace configuration file containing plugin metadata
- `README.md`: Documentation for the marketplace including installation and contribution guidelines

## Marketplace Configuration

The marketplace is configured via `.claude-plugin/marketplace.json` which contains:
- Marketplace metadata (name, owner, description)
- Array of available plugins with each plugin containing:
  - `name`: Unique plugin identifier
  - `source`: GitHub repository reference
  - `description`: Clear explanation of functionality
  - `version`: Semantic version
  - `tags`: Array of relevant tags for discoverability
  - `author`: Plugin author name

## Plugin Management Commands

To use this marketplace in Claude Code:
```bash
/plugin marketplace add adrianpuiu/claude-skills-marketplace
```

To install plugins from this marketplace:
```bash
/plugin install project-planner-skill@claude-skills-marketplace
```

## Adding New Plugins

To add a new plugin to the marketplace:
1. Fork the repository
2. Update `.claude-plugin/marketplace.json` following the existing plugin format
3. Submit a pull request

Ensure plugins follow semantic versioning and include clear, concise descriptions with relevant tags for discoverability.