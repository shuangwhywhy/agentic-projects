---
name: four-layer-sequential
description: run four-layer-intake, then layer-path-locator, then path-economics-planner as one sequential workflow. use when the user needs a full four-layer analysis from raw mixed input through legal path selection to a resource-aware route recommendation.
---

# Four-Layer Sequential

## Overview
This is the orchestration entry point for the plugin.

Use it when the user wants the full chain instead of only one stage.
The workflow is strict:
1. intake first
2. legal path location second
3. path economics decision third

Use the user's language by default.

## Required input
Prefer to receive:
- the raw user input
- the user's goal or expected output
- any explicit budget, latency, or quality constraints

If the user has already selected a focus, honor it.
If not, infer the best current focus from the intake result and say that it was inferred.

## Workflow

1. Run `four-layer-intake` on the raw user input.
   Keep the structured intake report intact.

2. Select the downstream focus.
   - Prefer the user's explicit focus if one exists.
   - Otherwise use the intake report's recommended focus candidate.
   - If no stable focus emerges, stop after intake and explain why downstream routing would be premature.

3. Run `layer-path-locator` with:
   - the selected focus
   - the intake handoff
   - the user's goal or expected result

4. Run `path-economics-planner` with:
   - the selected focus
   - the identified start layer and target layer
   - the legal path options
   - any explicit or inferred budget, latency, or quality constraints

5. Reconcile the outputs.
   - If later-stage reasoning exposes a blocker or contradiction, say whether it requires looping back.
   - Do not silently rewrite upstream conclusions.

6. Produce one combined sequential report.
   Preserve the key decisions from each stage and end with a final recommendation.

## Guardrails
- Do not skip stages.
- Do not design the route before intake is complete.
- Do not optimize the route before legal path options are known.
- Do not hide uncertainty that materially changes the chosen route.
- Keep downstream reasoning traceable to upstream outputs.

## Output format
Always produce one structured combined report.

# Four-Layer Sequential Report

## 0. Request summary
- raw request summary:
- user goal:
- explicit constraints:

## 1. Intake stage
Include the key result from `four-layer-intake`:
- normalized input summary
- element map summary
- concrete questions
- concrete tasks
- recommended focus candidate
- critical ambiguity

## 2. Path location stage
Include the key result from `layer-path-locator`:
- selected focus
- whether focus was explicit or inferred
- start layer
- target layer
- mandatory route
- topology
- legal path options
- illegal shortcuts

## 3. Economics stage
Include the key result from `path-economics-planner`:
- decision context
- candidate routes considered
- cost-benefit comparison
- recommended route
- checkpoints
- expected outcome profile

## 4. Final recommendation
Include:
- chosen route sequence
- why this route is the best fit now
- what should happen next
- what would force re-planning

## Quality bar
A good output from this skill should let a later execution step say:
- "the raw input has already been normalized"
- "the legal route is already known"
- "the recommended route has already been justified against cost"
- "i know exactly what to do next without jumping layers"
