# AI Agent Config

Conservative, safety-focused configuration and instruction templates for AI coding agents.

This repository currently contains a reusable configuration for Codex.

## Goals

The configuration in this repository is designed around a conservative approach to agent-assisted development:

- Restrict the agent to the current project whenever possible.
- Require explicit approval before creating, modifying, renaming, or deleting files.
- Treat Git operations such as staging, committing, and pushing as separately restricted actions.
- Require approval before installing, updating, or removing dependencies.
- Allow non-destructive inspection, testing, linting, and similar development tasks where appropriate.
- Keep agent actions narrowly scoped to the user's request.

These instructions are intended to reduce unintended changes while still allowing Codex to assist with normal development work.

## Security

Do not store secrets, credentials, passwords, API keys, access tokens, private keys, or other sensitive information in this repository.

Configuration templates should use placeholders or environment-variable references instead of real secret values.

Agent instruction files are not a security boundary. Rules defined in `AGENTS.md` guide Codex behavior, but they do not replace sandboxing, operating-system permissions, or other technical access controls.

## Codex Configuration

Codex instructions are defined in `AGENTS.md`.

The current configuration includes policies for:

- File access restrictions
- Sensitive information
- Change approval
- Git operation restrictions
- Command execution restrictions

## Usage

Treat `AGENTS.md` as a reusable template.

Copy it into the root of another repository and adapt any project-specific sections as needed.

Keeping a separate copy in each project allows the project to customize its rules independently and preserves the exact instructions used for that project in version control.

## Disclaimer

This configuration is intended to encourage conservative Codex behavior, but it does not guarantee isolation or prevent all unintended actions.

Use appropriate sandboxing, filesystem permissions, operating-system security controls, and version control in addition to agent-level instructions.
