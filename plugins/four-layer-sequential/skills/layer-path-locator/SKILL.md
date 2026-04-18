---
name: layer-path-locator
description: identify the legal four-layer route for a selected focus. use when a concrete question or task has already been isolated and chatgpt must determine the start layer, target layer, mandatory intermediate layers, turning points, and path topology such as same-layer, downward, reverse trace, v-shape, or multi-pass, without yet optimizing for token cost, time cost, or execution convenience.
---

# Layer Path Locator

## Overview
Treat complexity as a **path property**, not as a static task label.

Given one selected focus, determine where the reasoning starts, where a satisfactory answer must land, which layers must be traversed, and what legal route shapes are available.

Use the user's language by default.

## Required input
Prefer to receive:
- a selected focus item
- the upstream intake output
- the user's goal or expected result

If the focus is not explicitly selected, infer the best current focus and say that it is inferred.

## Workflow

1. Define the focus precisely.
   - Rewrite the current focus as one governable problem.
   - Separate the focus from surrounding material.

2. Identify the **start layer**.
   Ask: where does the current problem actually begin?
   Common signals:
   - abstract principle debate → layer 1
   - product boundary or responsibility debate → layer 2
   - object/state/interface issue → layer 3
   - code/demo/runtime/config issue → layer 4

3. Identify the **target layer**.
   Ask: at which layer would the user's goal count as satisfied?
   Do not confuse source material with destination.

4. Determine mandatory traversals.
   - If start and target are the same, keep the route in-layer unless a return loop is required.
   - If descending, pass layer by layer without skipping.
   - If ascending, reverse-trace layer by layer without skipping.
   - If the problem requires validation, revision, then re-descent, represent that as a V-shape or multi-pass route.

5. Detect turning points.
   Turning points are moments where the route must change direction, pause, or re-ground assumptions.
   Examples:
   - an unresolved layer 1 principle blocks lower-layer design
   - implementation evidence forces abstraction to be revised upward
   - architecture cannot proceed until product boundary is re-clarified

6. Enumerate legal path options.
   Prefer a short list of plausible legal routes rather than a single premature answer.

7. Mark illegal shortcuts.
   Explicitly name any tempting but invalid jump-layer move.

## Guardrails
- Do **not** optimize for token usage or speed here.
- Do **not** score answer quality or success probability here.
- Do **not** jump layers.
- Do **not** treat “same topic mentioned at multiple layers” as permission to skip intermediate layers.
- When start or target is ambiguous, show alternatives instead of faking precision.

## Path topology vocabulary
Use these labels when helpful:
- **same-layer**: start and target are in the same layer.
- **descent**: move from higher layer to lower layer step by step.
- **reverse-trace**: move from lower layer upward step by step.
- **v-shape**: descend or ascend, then turn and traverse back after a required re-grounding step.
- **multi-pass**: more than one directional change is likely required.

## Output format
Always produce one structured path-location report.

# Layer Path Location Report

## 0. Focus definition
- selected focus:
- whether focus was explicit or inferred:
- what counts as solving this focus:

## 1. Start layer
- start layer:
- why this is the start:
- evidence:

## 2. Target layer
- target layer:
- why this is the target:
- evidence:

## 3. Mandatory route
List the legal layer sequence.
Examples:
- layer 1 -> layer 2 -> layer 3 -> layer 4
- layer 4 -> layer 3 -> layer 2 -> layer 1
- layer 2 -> layer 3 -> layer 2 -> layer 3 -> layer 4

## 4. Path topology
- topology label:
- why this topology fits:
- expected turning points:

## 5. Legal path options
For each option, include:
- route name
- exact layer sequence
- what each step must accomplish
- where the key turning point sits

## 6. Illegal shortcuts to avoid
List any likely jump-layer errors.

## 7. Handoff for downstream planning
Include:
- preferred legal options to evaluate next
- ambiguities that still affect route choice
- information gaps that could change start/target judgment

## Quality bar
A good output from this skill should make a later planner say:
- “i know where the problem starts”
- “i know where the answer must land”
- “i know which layer transitions are mandatory”
- “i know which shortcuts are illegal”
