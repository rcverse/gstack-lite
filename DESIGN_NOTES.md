# Design Notes

## Methodology distillation, not a port

The original GStack skills combine two layers:

1. review methodology: how to think, what to inspect, what decisions to surface;
2. runtime harness: local config, browser daemon, dashboards, telemetry, update checks, review logs, artifact sync, and automation.

`gstack-lite` keeps the first layer and removes the second. The result is a small set of review skills that can travel between projects and agents without requiring GStack installation.

## Why exclude the full runtime

The full runtime is powerful, but it is intentionally not part of this package. The lite pack is for cases where the user wants the discipline without the weight: no `~/.gstack`, no daemon, no browser tooling, no dashboards, no generated preamble, no proactive routing, and no skill-owned workflow state.

This also makes the skills easier to audit. A reviewer can read one `SKILL.md` and understand exactly what it will do.

## Harness compatibility

These skills can be used with:

- Claude Code personal or project skills;
- Codex or other coding agents as plain review prompts;
- GSD or similar phased workflows as review checkpoints;
- Superpowers/TDD-style workflows as pre-implementation or pre-ship gates;
- manual research-tool, CLI, backend, frontend, or internal-tool projects.

They do not assume that GStack owns the workflow. The project authority files own the workflow.

## Token-bloat control

- Keep each `SKILL.md` compact.
- Put report structures in `templates/`.
- Use examples only as examples, not hidden requirements.
- Avoid repeating long philosophy blocks.
- Prefer operational checklists over persona prose.
- Add future skills as separate directories, not as one giant mega-skill.

## Preserving methodology without copying source

The lite skills preserve the shape of the original review work: scope challenge, existing-code reuse check, failure-mode review, explicit verdicts, and user decision capture. They deliberately restate these ideas in new, compact wording rather than pasting long source sections.

## Adding future lite skills

Use this pattern:

1. Identify the original skill source and any shared methodology blocks.
2. Write a `SOURCE_MAP.md` row before drafting.
3. Preserve the reasoning mode, not the runtime machinery.
4. Add a compact `skills/<name>/SKILL.md`.
5. Add one template or example only if it prevents repeated prose in the skill.
6. Audit for the quality bar in `README.md`.

Suggested backlog:

- `gstack-lite-code-review`: diff-aware structural review, no auto-fix by default.
- `gstack-lite-debug-investigation`: root-cause investigation before fixes.
- `gstack-lite-retro`: project/process retrospective with concrete improvement actions.
- `gstack-lite-release-check`: pre-release readiness, docs, tests, rollback, deploy plan.
