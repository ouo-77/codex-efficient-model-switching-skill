---
name: quota-handoff
description: Astra-only planning and creative coordination with economical Luna, Sol or Terra execution. Do not activate when the user starts with Sol, Luna or Terra.
---

# Quota Handoff

## Activation gate (first)
Activate only when the user selected Astra for this task. Sol, Luna or Terra selected by the user means this skill is inactive: work normally without extra planning or delegation caused by this skill. If the selection is unknown, do not assume Astra. An executor assigned by Astra is a worker, not a new planner; do not recursively activate this workflow. A user's later model switch or request to stop delegation takes precedence.

## Planner declaration
When active, state briefly: "Astra handles thinking, planning and creative direction; a suitable execution model produces and tests the deliverable." Astra may inspect necessary context, make decisions, review results and communicate. It does not produce implementation code, patches, scripts or final creative artifacts. It must not silently take over production when execution is unavailable. Simple conversational answers need no worker.

## Choose for the user's conditions
Use known task scope, available models/tools, budget, quality requirements, deadline and privacy restrictions. Ask only for material missing constraints. Optimize total work to an acceptable result, not raw token count alone. Prefer the lowest capable available execution option, without claiming a provable minimum.

| Execution need | Trial starting point |
|---|---|
| Clearly specified, bounded code edits, simple tools, routine formatting | Luna, low reasoning where supported |
| Coupled modules, complex code/debugging, substantial synthesis | Sol, low/medium reasoning as needed |
| Image interpretation, visual layouts, screen workflows | Terra where available and appropriate |
| PPT, documents, video and other creative artifacts | Route by the difficult part above; verify required authoring/rendering/media tools separately |

Names are routing hints, not guaranteed capabilities or fixed price rankings. Verify actual available model IDs; do not substitute a different version silently. A language-model assignment does not grant video rendering, media generation, tool access or additional spending permission.

## Minimal handoff and delivery
1. Output one short numbered plan with scope, creative/layout decisions if needed, and observable acceptance conditions. No duplicate planning document or code.
2. Use a supported model-switch interface if actually available; otherwise explicitly delegate to one executor by default. Say "delegated", not "switched", if the parent stays Astra. Pass only needed paths, constraints and acceptance checks; avoid forking the whole history.
3. The executor creates files and verifies them using available domain skills/tools. Share usable files promptly, separating "created" from "verified". The planner reviews the result without duplicating implementation or passed tests.
4. An environment or permission failure is not evidence for a stronger model. Try one bounded low-cost verification alternative. For an actual capability failure, preserve the failing case and patch, then allow at most one scoped escalation within the user's limits. If blocked, retain the plan and explain manual model selection; do not claim completion or silently use Astra for production.

## Measurement
Run extra comparisons only when requested. Use the same task, inputs, acceptance tests and comparable starting context, isolate outputs and record model IDs, retries and verification coverage. Sum parent and worker task usage once using session deltas, avoiding child double counting. Report input (including cached input), cached input, output and total; do not add cached/reasoning subcategories twice. Mark missing usage or failed delivery explicitly. Different context lengths, cache, host and test coverage confound comparisons. Tokens, API prices and Plus quota deductions are not interchangeable; never promise a saving percentage without controlled evidence.
