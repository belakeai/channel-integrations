# Contributing to Belake Channel Integrations

Thank you for contributing to the Belake channel integrations repository. This document explains how to propose new samples and submit pull requests in a way that keeps the project consistent and useful for all Belake clients.

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [How to Contribute](#how-to-contribute)
- [Repository Conventions](#repository-conventions)
- [Adding a New Channel](#adding-a-new-channel)
- [Adding a New Integration Type](#adding-a-new-integration-type)
- [Pull Request Process](#pull-request-process)
- [Sample Checklist](#sample-checklist)

## Code of Conduct

Be respectful and constructive. This repository serves multiple Belake clients and partners.

## How to Contribute

1. **Open an issue** — For new channels or integration types, open an issue first to discuss scope and approach.
2. **Fork and branch** — Create a branch from `main` using the naming convention below.
3. **Follow the structure** — Use the templates in `_templates/` as a starting point.
4. **Submit a PR** — Fill out the pull request template and ensure the checklist is complete.

## Repository Conventions

### Naming

- **Channels**: `kebab-case` (e.g., `microsoft-teams`, `slack`, `web-chat`)
- **Integration types**: `kebab-case` (e.g., `deploy-app`, `copilot-studio-agent`, `messaging-extension`)
- **Branches**: `channel/{channel-name}/{integration-type}` or `channel/{channel-name}` for new channels  
  Examples: `channel/microsoft-teams/deploy-app`, `channel/slack/bot`

### File Structure

Each integration sample must include:

```
channels/{channel-name}/{integration-type}/
├── README.md          # Required: step-by-step guide in English
├── (optional)         # Scripts, configs, manifests, assets
```

### Documentation

- All content must be in **English**.
- READMEs should include:
  - **Overview** — What this integration does and when to use it.
  - **Prerequisites** — Required accounts, tools, and Belake setup.
  - **Steps** — Numbered, reproducible instructions.
  - **Configuration** — Environment variables, secrets, and settings.
  - **Troubleshooting** — Common issues and solutions (if applicable).

## Adding a New Channel

1. Create `channels/{channel-name}/README.md` with:
   - Channel description
   - List of available integration types with links
   - Links to official channel documentation
2. Add the channel to the main [README.md](./README.md) "Supported Channels" table.
3. Use `_templates/sample-template/` as a base for your first integration.

## Adding a New Integration Type

1. Create `channels/{channel-name}/{integration-type}/` directory.
2. Add a `README.md` following the [sample template](./_templates/sample-template/README.md).
3. Update the channel's `README.md` and the main `README.md` table.

## Pull Request Process

1. Ensure your sample works end-to-end before submitting.
2. Use the PR template and complete all checklist items.
3. Keep PRs focused — one channel or one integration type per PR when possible.
4. Request review from maintainers.

## Sample Checklist

Before submitting, verify:

- [ ] README is in English
- [ ] Naming follows `kebab-case`
- [ ] Prerequisites are clearly listed
- [ ] Steps are numbered and reproducible
- [ ] No hardcoded secrets or credentials
- [ ] Main README table updated (if adding new sample)
- [ ] Channel README updated (if adding new integration to existing channel)
