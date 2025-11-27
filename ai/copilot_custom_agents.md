# Copilot Custom Agents — Workspace Guide

This workspace has a shared set of GitHub Copilot Custom Agents installed for every repository under `~/Documents/GitHub`.

Use this guide to discover what’s available, how to invoke agents in Copilot Chat, and how to maintain them across repos.

## Agents available (10)

These files live in each repo at `.github/agents/*.agent.md` and are discovered automatically by Copilot Chat:

1. adr-generator.agent.md — Draft Architecture Decision Records (ADRs) from context
2. specification.agent.md — Turn ideas/issues into crisp, testable specs
3. plan.agent.md — High-level delivery plan from a spec or problem statement
4. implementation-plan.agent.md — Break work into tasks, estimate, order, and risks
5. task-planner.agent.md — Convert plans into granular, actionable tasks
6. refine-issue.agent.md — Improve/clarify an issue before grooming
7. technical-content-evaluator.agent.md — Review docs or PR descriptions for clarity and technical quality
8. code-tour.agent.md — Produce an annotated code tour of a repo/area
9. hlbpa.agent.md — High-level business process analysis (pre-existing)
10. meta-agentic-project-scaffold.agent.md — Agentic project scaffolding (pre-existing)

## How to use in Copilot Chat

- Open Copilot Chat in VS Code (View → Chat) or use the GitHub web chat.
- Type `@` and choose an agent by name (e.g., `@specification`), then give your prompt.
- Agents operate using repository context; open the target repo folder in VS Code to scope context.

Tips
- Start with `@refine-issue` → `@specification` → `@plan` → `@implementation-plan` → `@task-planner` for a smooth pipeline from idea to tasks.
- Use `@technical-content-evaluator` before sharing an ADR/spec/plan externally.
- Run `@code-tour` when onboarding or exploring unfamiliar areas.

## Maintenance and updates

A central directory acts as the source of truth: `~/.github/agents`.

- To propagate agents to every repo under `~/Documents/GitHub`, run:
  - `~/Documents/GitHub/sync-copilot-agents.sh`
- The script prints a per-repo summary (agent counts) and detects if there are any pending changes.
- Optional: Commit and push changes across repos using the script flags (see below).

### Script flags (after we enhanced it)

- `--dry-run`  : Show which repos would be updated and a summary; do not change files
- `--commit`   : After syncing, auto-commit changes in any repo with updates
- `--push`     : After committing, auto-push to the default remote (requires `--commit`)
- `--include name` : Only process repos whose folder name matches the given substring (can specify multiple)
- `--exclude name` : Skip repos whose folder name matches the given substring (can specify multiple)

Examples
- Dry run only: `~/Documents/GitHub/sync-copilot-agents.sh --dry-run`
- Sync and commit: `~/Documents/GitHub/sync-copilot-agents.sh --commit`
- Sync, commit, and push: `~/Documents/GitHub/sync-copilot-agents.sh --commit --push`
- Only repos with "Candle": `~/Documents/GitHub/sync-copilot-agents.sh --include Candle`
- Exclude archived repos: `~/Documents/GitHub/sync-copilot-agents.sh --exclude archive --exclude Old`

## Verify installation

- In any repo, check `.github/agents/` contains 10 `*.agent.md` files.
- In Copilot Chat, type `@` and search for one of the agent names above.

## Troubleshooting

- If an agent isn’t visible in Copilot:
  - Ensure you opened the repo folder in VS Code (so Copilot sees `.github/agents`).
  - Run the sync script to re-propagate from the central directory.
  - If you added new agents to the central source, try `--commit --push` to publish changes.
- If you work outside `~/Documents/GitHub`, copy `.github/agents` manually or update the script root.

## Change management

- Treat `~/.github/agents` as your source of truth. Update agents there, then sync.
- For new agents, add them to the central folder and update this document with a one-liner and suggested use.
- Commit/push across repos if you want the agents tracked in version control.
