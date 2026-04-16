# Privacy Policy — delphi-ag-dev

> 🇺🇸 [English](privacy-policy.md) · 🇧🇷 [Português](privacy-policy.pt-BR.md) · 🇪🇸 [Español](privacy-policy.es.md)

**Last updated:** April 2026

---

## Overview

**delphi-ag-dev** is an open-source plugin for the [Antigravity](https://github.com/mrschuster1/delphi-ag-dev) multi-agent AI system. This document explains what data the plugin handles, how it is processed, and your rights as a user.

---

## What Data the Plugin Processes

The **delphi-ag-dev** plugin operates entirely within the context of your local development environment and the AI agent session. It does **not** have any backend service, database, or external API of its own.

The plugin may process the following types of data **within your AI session only**:

| Data Type | Purpose | Stored Externally? |
|---|---|---|
| Source code files (`.pas`, `.dfm`, etc.) | Code review, audit, test generation | ❌ No |
| Project file names and structure | Spec generation, architecture analysis | ❌ No |
| Natural language descriptions you provide | Generating new code via `/delphi-write` | ❌ No |

---

## How Data is Handled

- All data processing occurs **locally within your AI agent session**.
- The plugin does **not** send, store, or transmit any of your source code or project data to external servers.
- The only data that leaves your machine is what is sent to the **AI model provider** (e.g., Anthropic, Google, etc.) as part of the normal AI session — governed by their own privacy policies.
- This plugin is purely a configuration layer (Skills + Workflows) — it has no executable code, no network calls, and no data persistence of its own.

---

## Third-Party AI Providers

When you interact with an AI agent that has this plugin loaded, your prompts and any code you share are processed by the underlying AI model provider. Please review their privacy policies:

- [Anthropic Privacy Policy](https://www.anthropic.com/privacy)
- [Google Privacy Policy](https://policies.google.com/privacy)

---

## Data You Share Voluntarily

This is an open-source project hosted on GitHub. If you:

- **Open an issue** or **submit a pull request**, your GitHub username and the content you submit will be visible publicly on GitHub, subject to [GitHub's Privacy Policy](https://docs.github.com/en/site-policy/privacy-policies/github-privacy-statement).
- **Star or fork** the repository, this activity is also public on GitHub.

---

## No Analytics or Telemetry

**delphi-ag-dev** does **not** collect any telemetry, usage statistics, or analytics data. There is no tracking whatsoever.

---

## Children's Privacy

This plugin is intended for use by software developers. It is not designed for, and does not knowingly process data from, children under the age of 13.

---

## Changes to This Policy

This privacy policy may be updated periodically. Changes will be reflected by the "Last updated" date at the top of this document. Continued use of the plugin after changes constitutes acceptance of the updated policy.

---

## Contact

For questions or concerns regarding this privacy policy, please open an issue on the GitHub repository:

👉 [https://github.com/mrschuster1/delphi-ag-dev/issues](https://github.com/mrschuster1/delphi-ag-dev/issues)
