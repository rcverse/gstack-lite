# Self-Audit

This audit applies `DISTILLATION_STANDARD.md` to the current lite skill pack.

## Summary

The first pass was too short and risked becoming generic checklists. The revision pass restored operational pressure through evidence ledgers, alternatives, gates, failure maps, verdict criteria, and explicit no-edit/no-silent-decision rules.

A later independent fidelity pass identified several small but important over-compression risks: office-hours needed a stronger second-push rule, CEO review needed scope trajectory capture, engineering and design review needed explicit NOT-in-scope/deferred-decision outputs, design review needed review-mode separation, and QA needed explicit pass-scope labeling. Those patches have now been applied.

The design artifact pass added standalone visual exploration and static-reference/prototype/handoff skills while preserving the repo's decoupling rule: skills may recommend each other, but no skill requires another by default.

Current status: production-usable as a planning, visual-exploration, design-reference, design-review, engineering-readiness, and QA review pack, but not yet a complete pre-merge/release workflow pack. The new artifact-generation skills are not yet battle-tested on real visual artifacts.

## Skill scores

Scale: 1-5. Production target: average >= 4.0, no score below 3.

| Skill | Source fidelity | Runtime independence | Operational pressure | Project generality | Token discipline | Safety/governance | Average |
|---|---:|---:|---:|---:|---:|---:|---:|
| `gstack-lite-office-hours` | 4 | 5 | 4 | 5 | 4 | 5 | 4.5 |
| `gstack-lite-ceo-review` | 4 | 5 | 4 | 5 | 4 | 5 | 4.5 |
| `gstack-lite-eng-review` | 4 | 5 | 5 | 5 | 4 | 5 | 4.7 |
| `gstack-lite-design-shotgun` | 4 | 5 | 4 | 5 | 4 | 5 | 4.5 |
| `gstack-lite-design-html` | 4 | 5 | 4 | 5 | 4 | 5 | 4.5 |
| `gstack-lite-design-review` | 4 | 5 | 5 | 5 | 4 | 5 | 4.7 |
| `gstack-lite-qa-review` | 4 | 5 | 5 | 5 | 4 | 5 | 4.7 |

## What improved in the revision pass

- Added `DISTILLATION_STANDARD.md` as the governing quality bar.
- Added office-hours as a first-class lite skill.
- Restored evidence ledgers in every skill.
- Added decision gates or readiness gates in every skill.
- Added alternatives where the source methodology requires them.
- Added a structured failure map to engineering review.
- Added design completeness rating and design-decision gate to design review.
- Added tested/inspected/reported/not-tested/blocked distinction to QA.
- Updated `SOURCE_MAP.md` to include office-hours and the revised methodology spine.
- Added examples that show the expected output pressure.

## What improved in the fidelity patch pass

- Strengthened `gstack-lite-office-hours` with an explicit second-push rule and a harder premise-gate stop before alternatives.
- Added future-state / scope trajectory mapping and an explicit scope decision table to `gstack-lite-ceo-review`.
- Added conditional implementation-shape alternatives and explicit NOT-in-scope output to `gstack-lite-eng-review`.
- Added review-mode separation, a distinct visual hierarchy pass, and deferred design-decision capture to `gstack-lite-design-review`.
- Added explicit QA scope levels to `gstack-lite-qa-review` so smoke, critical-path, standard, exhaustive, and user-specified passes do not imply the same confidence.
- Clarified in `README.md` that the current pack is production-usable for planning/review/QA but not yet a complete pre-merge or release workflow pack.

## What improved in the design artifact pass

- Added `gstack-lite-design-shotgun` as a standalone visual-direction exploration skill with deliberate variant-count discipline, authority grounding, anti-generic rules, evaluation rubric, and synthesis/handoff output.
- Added `gstack-lite-design-html` as a standalone static reference / lightweight clickable prototype / implementation handoff skill with source-of-truth hierarchy, visual-reference handling, prototype-code reuse warnings, and responsive/accessibility rules.
- Clarified in `README.md` that each skill is independently invocable and that suggested workflows are examples, not required pipelines.
- Updated `SOURCE_MAP.md` to document what was preserved and removed from the original `design-shotgun` and `design-html` sources.
- Updated `DESIGN_NOTES.md` to define the artifact-generation boundary and the design-skill decoupling principle.

## Remaining concerns

1. **No real-world visual-artifact run yet.** The new design artifact skills should be tested on at least one screenshot-driven UI reference, one authority-doc-driven prototype, and one visual-direction exploration.
2. **No code-review lite skill yet.** The pack will feel incomplete for pre-merge workflows until `gstack-lite-code-review` exists.
3. **No release-check lite skill yet.** The current QA skill can support release decisions, but it does not replace a dedicated release-readiness audit covering tests, docs, rollback, versioning, distribution, and final go/no-go.
4. **No debug-investigation lite skill yet.** The original GStack investigation methodology is valuable enough to distill, especially the no-fix-without-root-cause rule.
5. **No automated validation.** There is no script checking YAML frontmatter, forbidden strings, line-length/token discipline, or required operational-pressure sections yet.
6. **No license file for this new repo yet.** `NOTICE.md` attributes GStack, but the repo should still choose its own license before publication.

## Forbidden-runtime audit

Checked by content design and manual string review, not an automated script yet:

- no `~/.gstack` dependency in skills;
- no telemetry;
- no update checks;
- no dashboard dependency;
- no browser daemon dependency;
- no `$B` or `$D` commands in skills;
- no comparison-board or feedback-file dependency in the new artifact skills;
- no proactive auto-routing;
- no forced skill sequence;
- no automatic implementation, fixing, committing, or shipping;
- explicit no-file-modification rule in every skill.

## Recommendation

Use the current seven-skill pack as a production-usable methodology layer for early shaping, scope review, visual exploration, static reference/prototype handoff, design review, engineering readiness, and evidence-based QA.

Before treating `gstack-lite` as a fuller GStack-methodology replacement, add at least:

1. `gstack-lite-code-review` for diff-aware pre-merge structural review;
2. `gstack-lite-release-check` for release readiness, rollback, docs, tests, distribution, and final go/no-go;
3. a lightweight validation script for frontmatter, forbidden runtime strings, and required operational-pressure sections.
