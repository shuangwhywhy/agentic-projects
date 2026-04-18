---
name: four-layer-intake
description: decompose raw user input into analyzable elements before planning or answering. use when the user provides mixed input such as background, beliefs, requirements, specs, questions, assumptions, ideas, commands, code, demos, or documents and chatgpt must identify concrete questions, candidate tasks, focus candidates, and primary or secondary four-layer placement without classifying the input as simple vs complex.
---

# Four Layer Intake

## Overview
Treat the **user input itself** as the first-class object.

Do not start by assuming the input is a single clean task. First normalize the input, split it into distinct elements, identify which parts are material vs problem vs requested action, and assign each element to the most relevant four-layer location.

Use the user's language by default.

## Workflow

1. Normalize the raw input.
   - Preserve the user's core meaning.
   - Strip only obvious repetition or formatting noise.
   - Keep mixed inputs mixed until they are explicitly separated.

2. Split the input into atomic elements.
   - Prefer the smallest units that are still meaningful.
   - Do not merge unrelated statements just because they appear in one paragraph.
   - Keep one element per materially distinct claim, ask, assumption, method, or artifact reference.

3. Classify each element.
   Use one or more of these labels as needed:
   - background
   - concept / belief
   - requirement
   - goal
   - spec
   - question
   - assumption
   - idea
   - command
   - guess
   - design
   - method
   - constraint
   - evidence / material
   - implementation artifact
   - evaluation / acceptance signal

4. Assign four-layer placement.
   - **Layer 1: concept / philosophy** for identity, principles, non-negotiables, abstract framing, value ordering.
   - **Layer 2: product / prd** for user-facing responsibility, capability, boundary, delivery shape, interaction contract.
   - **Layer 3: architecture** for objects, modules, state, interfaces, control flow, validation loops, structural constraints.
   - **Layer 4: implementation** for code, config, tests, runtime, instrumentation, deployment, integration specifics.

   For every element, provide:
   - primary layer
   - optional secondary layer
   - one-sentence reason

5. Distinguish problem space from execution space.
   Separate:
   - concrete questions that need answering
   - concrete tasks that need doing
   - supporting materials that are only evidence or context
   - unresolved ambiguity that blocks clean intake

6. Nominate focus candidates.
   Rank the 1 to 3 most likely current focus items.
   Each focus candidate must be a clearly governable unit, not a vague topic cloud.

7. Surface what is still unclear.
   Only include ambiguity that materially changes later path design or execution quality.

## Guardrails
- Do **not** classify the input as simple vs complex.
- Do **not** design the path yet.
- Do **not** estimate token cost, time cost, or answer quality tradeoffs here.
- Do **not** collapse different elements into one pseudo-task merely for neatness.
- Do **not** force everything into “task” language. Some inputs are questions, materials, contradictions, or implicit assumptions.
- When evidence is weak, mark the placement as tentative instead of pretending certainty.

## Output format
Always produce one structured intake report.

# Four-Layer Intake Report

## 0. Input scope
- source:
- language:
- raw input summary:
- obvious artifacts provided:

## 1. Normalized input
Write a compact paraphrase of the user's input without changing its meaning.

## 2. Element map
Use a table with these columns:

| id | element | type label | primary layer | secondary layer | why this placement | confidence |
|---|---|---|---|---|---|---|

## 3. Concrete questions
List only real questions implied or stated by the input.

## 4. Concrete tasks
List only real tasks implied or stated by the input.

## 5. Materials and evidence
List inputs that are context or artifacts rather than questions/tasks.

## 6. Focus candidates
Rank up to 3 focus candidates.
For each one, include:
- title
- why it is a distinct focus
- what would count as resolving it

## 7. Critical ambiguity
List only ambiguity that would materially change later path selection or answer quality.

## 8. Handoff for downstream skills
Include:
- recommended focus candidate
- elements most relevant to that focus
- any unresolved ambiguity that downstream skills must respect

## Quality bar
A good output from this skill should make a later planner say:
- “i know what the user actually gave me”
- “i know which parts are concept vs product vs architecture vs implementation”
- “i know what the likely focus is”
- “i am not yet pretending to know the path or the final answer”
