# Codex Efficient Model Switching Skill
English | [中文](README.md)

**In short:** this is a Codex Skill for planning work with Astra and routing production to a capable, economical executor. It activates only when the user initially chooses Astra for the task.

## What it is for

Complex tasks benefit from planning, but repeatedly asking a high-capability model to plan, implement, revise, and test can duplicate effort. This Skill separates those responsibilities: Astra interprets the request and makes a concise plan; a suitable executor creates the code, document, slide deck, or other deliverable; then the result is checked against the request.

Use it when you want to manage total task effort without sacrificing acceptance quality. Typical workflows include coding and small games, writing and editing, presentations, and video projects. Actual slide or video production requires the host to provide the relevant tools; this Skill coordinates work but does not include a media-generation engine.

## What it does

- **Respects the activation gate:** activate only when the user initially selects Astra. If they start with Sol, Luna, or Terra, leave their workflow alone. An unknown selection is not permission to activate.
- **Plans against real constraints:** consider the requested outcome, acceptance checks, budget, deadline, available tools, privacy, and quality requirements before choosing an executor.
- **Routes by task fit:** try Luna for bounded work, Sol for complex coding or synthesis, and Terra for visual or screen-based work when available. Choose from actual available capabilities; model names are not fixed performance or pricing guarantees.
- **Keeps production focused:** normally one executor creates and tests the deliverable, avoiding parallel duplicate implementations.
- **Controls rework and escalation:** reuse usable work, distinguish creation from verification, and do not upgrade models just because the environment failed. Escalate capability at most once and only when a real capability gap remains.
- **Reports switching honestly:** delegation does not automatically switch the parent session's model. If the host cannot select an executor model, explain the manual step instead of claiming an automatic switch.

## Workflow

1. Astra clarifies the task's goal, acceptance criteria, constraints, and available tools.
2. Astra produces a short plan and selects the lowest-overhead executor that can meet the criteria.
3. The executor creates the deliverable and runs appropriate checks.
4. Share usable files promptly and state what was created, what was verified, and what remains uncertain.

## What it does not promise

The objective is lower **total effort to pass acceptance** and better throughput, not a guaranteed minimum token count, Plus quota saving, or fixed cost. Delegation, API billing, and product quota are different measures. The Skill does not override the user's model choice, silently activate when they start with Sol/Luna/Terra, or replace a code runtime, CAD tool, or media-generation service.

## Install

Clone [ouo-77/codex-efficient-model-switching-skill](https://github.com/ouo-77/codex-efficient-model-switching-skill) and place the folder containing the root `SKILL.md` in your configured Codex user skills directory, such as `~/.agents/skills/`. Back up custom versions before replacing them. Reload Skills or restart Codex, then invoke it in an Astra conversation:

> $quota-handoff Plan an offline game, then hand implementation and testing to the lowest-overhead capable executor.

The Skill's internal invocation name remains `$quota-handoff` for compatibility.

## Experiment and license

The [bilingual Snake exploration](snake-comparison.md), [redacted transcript excerpts](transcript.redacted.md), and [usage counters](usage.json) document one observed workflow. This was not a controlled A/B test and does not prove that this revision saves quota. No coursework files, credentials, or private identity data are included.

MIT licensed. An independent community project, not an official OpenAI feature. It includes no API client, background service, or automatic billing component.
