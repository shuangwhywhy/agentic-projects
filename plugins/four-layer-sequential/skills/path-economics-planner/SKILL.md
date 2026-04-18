---
name: path-economics-planner
description: evaluate legal four-layer path options and recommend a resource-aware route. use when the start layer, target layer, and candidate legal paths are already known and chatgpt must weigh path length, turning points, token or time cost, expected answer quality, and goal attainment probability to choose a sensible route for the current context instead of relying on habit or a single preference.
---

# Path Economics Planner

## Overview
Treat path design as a decision problem.

Do not assume that more backtracking is always better, or that the shortest legal path is always best. Estimate whether extra path length, extra turning points, and extra validation steps are worth their resource cost under the current goal, context, and quality bar.

Use the user's language by default.

## Required input
Prefer to receive:
- one selected focus
- start layer and target layer
- legal path options from upstream analysis
- current goal and quality expectation
- any budget or latency constraints if known

If no explicit budget is given, estimate comparatively rather than pretending exact limits.

## Planning model
Evaluate each path option on two sides.

### Cost side
Estimate these dimensions using qualitative bands or 1 to 5 scores:
- layer span: how far apart start and target are
- transition count: total number of layer crossings
- turning-point count: reversals, backtracks, or re-grounding loops
- context mass: amount and heterogeneity of material that must stay active
- verification burden: how much checking or re-checking the route requires
- orchestration burden: how hard it is to maintain state across the route

### Benefit side
Estimate these dimensions using qualitative bands or 1 to 5 scores:
- quality lift: expected improvement in answer quality vs the shortest legal path
- success lift: expected improvement in the chance of actually solving the user's goal
- risk reduction: reduction in wrong-layer reasoning, silent contradictions, or premature commitment
- reuse value: whether the extra route creates a more reusable answer or structure
- robustness under ambiguity: whether the route handles uncertain upstream assumptions better

### Decision rule
Choose the route with the best **net value under current goals**, not the route with the highest abstract rigor.

In practice:
- favor the shortest legal path when extra traversal adds little quality or success lift
- pay for extra backtracking when upstream ambiguity makes a short path fragile
- pay for a V-shape or multi-pass only when the expected lift materially exceeds the extra cost
- prefer checkpoints that allow early stop if the goal is reached sooner than expected

## Guardrails
- Do **not** fake exact token counts, exact probabilities, or pseudo-mathematical certainty.
- Do **not** recommend an illegal shortcut even if it looks cheaper.
- Do **not** optimize only for elegance; optimize for context-specific value.
- Do **not** assume the most rigorous route is automatically the best route.
- Make assumptions explicit whenever the user has not supplied budget, latency, or quality targets.

## Output format
Always produce one structured path-economics decision report.

# Path Economics Decision Report

## 0. Decision context
- selected focus:
- current goal:
- quality target:
- budget or latency constraints:
- explicit assumptions:

## 1. Candidate routes
List the legal routes under consideration.

## 2. Cost-benefit table
Use a table with these columns:

| route | layer sequence | token/time cost band | orchestration burden | expected quality lift | expected success lift | risk reduction | net judgment |
|---|---|---|---|---|---|---|---|

Use qualitative bands such as very low / low / medium / high / very high, or small integer scores with a legend.

## 3. Recommended route
For the chosen route, include:
- why it is worth its cost in this context
- why shorter legal routes are insufficient or sufficient
- why longer legal routes are not worth it yet, if applicable

## 4. Planned checkpoints
Define the checkpoints where the route may stop, continue, or re-plan.
For each checkpoint, include:
- what should be learned or confirmed
- what would justify continuing
- what would justify stopping early
- what would justify re-planning

## 5. Expected outcome profile
State the expected:
- answer quality band
- goal attainment confidence band
- resource consumption band
- main failure mode still remaining

## 6. Execution handoff
Include:
- the chosen route sequence
- what each step is supposed to produce
- where to be careful not to jump layers

## Quality bar
A good output from this skill should make an execution skill say:
- “i know which legal route to follow”
- “i know why this route is worth its cost”
- “i know where to checkpoint or stop early”
- “i am not pretending to know exact token math that i cannot justify”
