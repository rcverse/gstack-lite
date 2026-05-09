# Source Map

This file records what was distilled from the original GStack repository and what was intentionally left out.

| Original file | Preserved methodology | Removed infrastructure/noise | Lite destination |
|---|---|---|---|
| `README.md` | Review-pipeline framing: think, plan, review, test, ship; distinct specialist modes for product, engineering, design, QA | installation flow, marketing narrative, full skill catalogue, browser/runtime claims, telemetry/config/state references | `README.md`, all lite skill descriptions |
| `CLAUDE.md` | Platform-agnostic skill design principle: read project authority, avoid hardcoded project assumptions, ask when project-specific config is missing | contributor-only commands, eval harness, symlink/development workflow, gstack local state, browser daemon, model overlays, update/checkpoint machinery | `DESIGN_NOTES.md`, all `SKILL.md` hard rules |
| `ARCHITECTURE.md` | Explicit distinction between Markdown methodology and runtime/browser machinery; actionable error/reporting philosophy | Bun runtime, long-lived browser daemon, token auth, tunnel listeners, prompt-injection defense, logs, ref system, binary architecture | `DESIGN_NOTES.md` |
| `docs/OPENCLAW.md` | Treat GStack as a methodology source rather than a ported codebase; prompt text can bridge methodology across harnesses | OpenClaw dispatch routing, ACP spawning, generated OpenClaw artifacts, env-based session detection | `DESIGN_NOTES.md`, `README.md` |
| `plan-ceo-review/SKILL.md(.tmpl)` | Scope challenge, problem/user impact review, implementation alternatives, mode discipline, NOT in scope, hidden assumptions, explicit decisions, clear verdict | generated preamble, telemetry, update checks, GBrain/artifact sync, `~/.gstack` plans, AskUserQuestion machinery, CEO persona bloat, large philosophy blocks | `skills/gstack-lite-ceo-review/SKILL.md` |
| `plan-eng-review/SKILL.md(.tmpl)` | Step 0 scope/existing-code check, architecture review, data/state review, test strategy, failure modes, dependency/complexity review, unresolved decisions | generated preamble, review dashboard, review log, artifacts sync, GBrain, Codex optional review, forced interactivity, local GStack commands | `skills/gstack-lite-eng-review/SKILL.md` |
| `plan-design-review/SKILL.md(.tmpl)` | Design completeness rating, user-flow review, interaction states, IA, AI-slop detection, design-system alignment, responsive/a11y, unresolved design decisions | gstack designer binary, mockup generation pipeline, comparison boards, generated preamble, review logs, dashboard, local artifact paths | `skills/gstack-lite-design-review/SKILL.md` |
| `qa/SKILL.md(.tmpl)` | Critical path QA, evidence-based testing, edge/broken/empty states, severity classification, reproduction steps, fix verification, ship/no-ship recommendation | browser daemon, `$B` commands, automatic source fixes, atomic commits, regression test generation, health-score machinery, local reports under `.gstack` | `skills/gstack-lite-qa-review/SKILL.md` |
| `review/SKILL.md(.tmpl)` | Diff-aware structural review mindset, fix-first classification, verification before claims, checklist discipline | full PR review automation, Greptile handling, specialist agents, auto-fixes, GStack review logs | future `gstack-lite-code-review` backlog |

## Shared extracted spine

The lite pack preserves these cross-skill habits:

- start with scope and authority files;
- check what already exists before recommending new work;
- separate required work from deferred work;
- name risks, failure modes, and unresolved decisions explicitly;
- produce a verdict with concrete next actions;
- avoid silent file changes;
- keep reports portable and readable outside GStack.

## Explicit non-goals

- no runtime dependency on GStack;
- no local state;
- no telemetry;
- no dashboards;
- no browser daemon assumptions;
- no proactive routing;
- no cross-project learning logs;
- no project-specific workflow ownership.
