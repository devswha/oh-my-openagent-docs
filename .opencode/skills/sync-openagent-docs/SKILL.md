---
name: sync-openagent-docs
description: Synchronize this documentation site with upstream code-yeongyu/oh-my-openagent README, docs, package metadata, and harness behavior.
---

# Sync OpenAgent Docs

Use this skill whenever editing this repository's OmO/OpenAgent documentation based on upstream `code-yeongyu/oh-my-openagent`.

## Required Sources

Before changing content, inspect the current versions of these upstream sources when available:

- `README.md`
- `package.json`
- `docs/guide/installation.md`
- `docs/guide/overview.md`
- `docs/guide/orchestration.md`
- `docs/reference/features.md`
- `docs/reference/configuration.md`
- `docs/reference/cli.md`
- `docs/manifesto.md`
- Relevant upstream `.opencode/skills/*/SKILL.md` files when documenting skills or harness behavior.

Prefer a local clone under `/tmp/opencode/oh-my-openagent-source` if present. If it is stale or absent, use `gh` or a fresh clone outside the workspace.

## Naming Rules

- Product/site identity: Oh My OpenAgent, OmO.
- Upstream repository: `code-yeongyu/oh-my-openagent`.
- Published install command may still be `bunx oh-my-opencode ...`; do not rewrite it to `oh-my-openagent` unless upstream package metadata and installer docs confirm the rename.
- Explain the transition clearly: OpenAgent is the product identity; `oh-my-opencode` may remain the package/compatibility command.
- Do not invent model names or provider priorities. Prefer upstream docs, package metadata, and generated config/schema facts.

## Content Workflow

1. Compare current docs against upstream README/docs/source facts.
2. Update English and Korean pages first.
3. Keep Japanese and Chinese routes navigable; if not fully localized, use concise English fallback content rather than leaving routes empty.
4. Prefer tables and checklists for reference material.
5. Use Mermaid only for high-value architecture or lifecycle diagrams. Remove decorative diagrams from detail pages.
6. When adding a new section, update all relevant `meta*.json` files.
7. Keep examples executable and copy-safe.

## Harness Documentation Checklist

Cover these topics when they change upstream:

- Install flags and provider authentication.
- `doctor` diagnostics behavior.
- Agent catalog and role boundaries.
- Category + skill delegation rules.
- Continuation mechanisms: todos, Ralph/ulw loops, boulder state, background tasks.
- Tool surfaces: LSP, AST-Grep, tmux/browser/manual QA, Context7/web/GitHub search.
- Hook families: routing, continuation, recovery, tool integration, context injection.
- Config paths, model overrides, variants, `fallback_models`, environment variables.
- Telemetry opt-out variables and privacy notes.

## Verification

After editing docs:

- Check for excessive `<Mermaid` usage.
- Check for stale package-name claims.
- Run `npm run lint`.
- Run `npm run build`.
- Smoke changed routes locally or in the browser.
- If deploying, smoke the same routes on `https://omo.vibetip.help`.

## Output

Report:

- Which upstream sources were used.
- Which pages changed.
- What verification passed.
- Any upstream ambiguity that remains.
