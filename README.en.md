# Quota Handoff
English | [中文](README.md)

**Astra thinks, plans and directs creative work; suitable executors produce and verify deliverables.**

## Activation
Only activate when the user initially selects Astra for the task. When they select Sol, Luna or Terra, leave their normal workflow unchanged. Unknown selection is not permission to activate. Later model switches or stop-delegation requests take precedence. Assigned workers never recursively activate the planner workflow.

## Workflow
1. Consider requirements, budget, available models/tools, deadline, quality and privacy.
2. Produce one concise plan. Try Luna for bounded work, Sol for complex code and synthesis, and Terra for visual/screen work where available.
3. Default to one executor producing and testing the result. Code, writing, slides and video workflows are in scope; actual rendering or media generation requires separate tools and authorization.
4. Share usable files promptly and distinguish creation from verification. Avoid duplicated implementation and repeated planning. Environment failures do not trigger model upgrades; permit at most one scoped capability escalation.

The goal is lower total effort to pass acceptance, not a guaranteed minimum token count. Model names are not fixed cost/capability promises. Delegation is not an automatic parent-session model switch. Tokens, API pricing and Plus quota are different measures.

## Install
Clone [ouo-77/quota-handoff](https://github.com/ouo-77/quota-handoff) and place the entire `quota-handoff` folder (with `SKILL.md` at its root) in your configured Codex user skills directory, such as `~/.agents/skills/`. Back up custom versions before replacing them. Reload skills or restart, then invoke in an Astra conversation:

> $quota-handoff Plan an offline game, then hand implementation and testing to the lowest-overhead capable executor.

If the host cannot select execution models, the skill explains manual selection instead of pretending to switch.

## Evidence and limits
The [bilingual exploratory Snake comparison](snake-comparison.md) contains aggregate observations, not raw conversations or private files. It is not a controlled A/B test and does not establish savings for this revision.

MIT licensed. Independent community project, not an official OpenAI feature. No API client, background service or automatic billing component is included.
