# Source Map

This file records what was distilled from the original GStack repository and what was intentionally left out.

| Original file | Preserved methodology | Removed infrastructure/noise | Lite destination |
|---|---|---|---|
| `README.md` | Review/artifact workflow framing: think, plan, explore, review, test, ship; distinct specialist modes for product, engineering, design, QA | installation flow, marketing narrative, full skill catalogue, browser/runtime claims, telemetry/config/state references | `README.md`, all lite skill descriptions |
| `CLAUDE.md` | Platform-agnostic skill design principle: read project authority, avoid hardcoded project assumptions, ask when project-specific config is missing | contributor-only commands, eval harness, symlink/development workflow, gstack local state, browser daemon, model overlays, update/checkpoint machinery | `DISTILLATION_STANDARD.md`, `SKILL_WORKFLOW.md`, all `SKILL.md` hard rules |
| `ARCHITECTURE.md` | Explicit distinction between Markdown methodology and runtime/browser machinery; actionable error/reporting philosophy | Bun runtime, long-lived browser daemon, token auth, tunnel listeners, prompt-injection defense, logs, ref system, binary architecture | `DISTILLATION_STANDARD.md`, `SOURCE_MAP.md` |
| `docs/OPENCLAW.md` | Treat GStack as a methodology source rather than a ported codebase; prompt text can bridge methodology across harnesses | OpenClaw dispatch routing, ACP spawning, generated OpenClaw artifacts, env-based session detection | `SKILL_WORKFLOW.md`, `README.md` |
| `office-hours/SKILL.md(.tmpl)` | problem-before-solution discipline, mode-sensitive questioning, specificity pressure, status quo, narrowest wedge, premise gate, alternatives, design brief handoff | generated preamble, browser setup, GBrain, local design-doc writes under `~/.gstack`, WebSearch privacy ceremony, builder-profile state, AskUserQuestion machinery | `skills/gstack-lite-office-hours/SKILL.md` |
| `plan-ceo-review/SKILL.md(.tmpl)` | premise and scope challenge, user/operator impact, implementation alternatives, scope modes, NOT in scope, hidden assumptions, explicit decisions, clear verdict | generated preamble, telemetry, update checks, GBrain/artifact sync, `~/.gstack` plans, AskUserQuestion machinery, CEO persona bloat, large philosophy blocks | `skills/gstack-lite-ceo-review/SKILL.md` |
| `plan-eng-review/SKILL.md(.tmpl)` | Step 0 scope/existing-code check, architecture review, data/state review, failure map, test strategy, dependency/complexity review, unresolved decisions, readiness gate | generated preamble, review dashboard, review log, artifacts sync, GBrain, Codex optional review, forced interactivity, local GStack commands | `skills/gstack-lite-eng-review/SKILL.md` |
| `plan-design-review/SKILL.md(.tmpl)` | design completeness rating, user-flow review, interaction states, IA, AI-slop detection, design-system alignment, responsive/a11y, unresolved design decisions | gstack designer binary, mockup generation pipeline, comparison boards, generated preamble, review logs, dashboard, local artifact paths | `skills/gstack-lite-design-review/SKILL.md` |
| `design-shotgun/SKILL.md(.tmpl)` | standalone visual exploration, authority-grounded brief extraction, deliberate variant count, distinct design hypotheses, diversity axes, anti-generic design pressure, evaluation rubric, selection/synthesis, handoff notes | designer binary, `$D` commands, `$B` commands, parallel agents, comparison boards, feedback files, taste memory, `~/.gstack` output dirs, local artifact persistence | `skills/gstack-lite-design-shotgun/SKILL.md` |
| `design-html/SKILL.md(.tmpl)` | source/authority intake, visual-reference analysis, source-of-truth hierarchy, static/clickable/handoff modes, fidelity rules, responsive/a11y/state requirements, prototype-code reuse caution, handoff notes | Pretext-specific runtime requirement, framework-detection shell commands, browser/live-preview loop, designer prompt extraction, screenshot automation, `~/.gstack` finalized outputs, metadata writes, package installs | `skills/gstack-lite-design-html/SKILL.md` |
| `qa/SKILL.md(.tmpl)` | critical path QA, evidence-based testing, edge/broken/empty states, severity classification, reproduction steps, retest condition, ship/no-ship recommendation | browser daemon, `$B` commands, automatic source fixes, atomic commits, regression test generation, health-score machinery, local reports under `.gstack` | `skills/gstack-lite-qa-review/SKILL.md` |
| `review/SKILL.md(.tmpl)` | diff-aware structural review mindset, fix-first classification, verification before claims, checklist discipline | full PR review automation, Greptile handling, specialist agents, auto-fixes, GStack review logs | future `gstack-lite-code-review` backlog |

## Shared extracted spine

The lite pack preserves these cross-skill habits:

- start with scope and authority files;
- record evidence limits explicitly;
- check what already exists before recommending new work;
- produce alternatives before a strong recommendation when the source methodology requires it;
- separate required work from deferred work;
- name risks, failure modes, and unresolved decisions explicitly;
- use portable decision gates instead of GStack-specific `AskUserQuestion` machinery;
- produce a verdict with concrete next actions;
- avoid silent file changes;
- keep reports portable and readable outside GStack;
- keep artifact-generation skills standalone: they may suggest each other, but do not require a fixed design pipeline.

## Explicit non-goals

- no runtime dependency on GStack;
- no local state;
- no telemetry;
- no dashboards;
- no browser daemon assumptions;
- no proactive routing;
- no forced skill sequence;
- no cross-project learning logs;
- no project-specific workflow ownership;
- no automatic implementation, fixing, committing, or shipping.
