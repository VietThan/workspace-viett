# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repo is

A personal workspace for Viet Than. It contains no runnable code of its own — it is a coordination layer that holds:

- **Submodules** — individual project repos pinned to `main`
- **`ai/`** — high-level planning documents for active projects

There are no build commands, tests, or dev servers at the workspace level.

## Submodules

| Path | Repo | Purpose |
|---|---|---|
| `nyc-adventure/` | `VietThan/nyc-adventure` | Linh's original frontend-only NYC activity tracker (single HTML file, no build). Reference only. |
| `our-adventures/` | `VietThan/our-adventures` | Full-stack rebuild of nyc-adventure. See its own `CLAUDE.md`. |
| `agent-cli-plugin/` | `VietThan/agent-cli-plugin` | Claude Code plugin (`viett` namespace). See its own `CLAUDE.md`. |

When working inside a submodule, commits and pushes must be made from within that submodule's directory. After committing there, update the pointer in this repo with `git add <submodule> && git commit`.

## Planning docs (`ai/`)

Each file follows the naming convention `YYYY-MM-DD.NN.plan-name.md`.

| File | Subject |
|---|---|
| `2026-04-11.00.viet-plugin-plan.md` | `agent-cli-plugin` architecture and skill format |
| `2026-04-11.01.our-adventures-plan.md` | `our-adventures` full-stack architecture, stack decisions, phased implementation plan |

Read the relevant plan doc before making structural decisions in a submodule — they capture the reasoning behind choices that aren't obvious from the code alone.

## Active project: `our-adventures`

The primary active project. Key decisions (all in `ai/2026-04-11.01.our-adventures-plan.md`):

- **Stack:** Next.js (server mode) + Fastify on EC2 t4g.nano, PostgreSQL on RDS, Auth.js + Google OAuth, AWS CDK for infra
- **Current phase:** Phase 0 — scaffolding (no application code exists yet)
- **Repo:** `VietThan/our-adventures` — public

## Commit conventions

Conventional commits. Co-author trailer on every commit:
```
Co-Authored-By: Claude Sonnet 4.6 <noreply@anthropic.com>
```
