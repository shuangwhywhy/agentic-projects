# Classification Guide

## 1. First principle
Treat user input as a mixed bundle. Do not assume it is already a single task.

## 2. Common mixed-input patterns

### Pattern A: concept + requirement + implementation hint
Example:
- “we should treat input as first-class, not tasks. also draft the parsing structure.”

Suggested split:
- concept / belief
- requirement
- design or implementation task

### Pattern B: code artifact + upward abstraction request
Example:
- “here is a demo. tell me what its first-class concept should be.”

Suggested split:
- implementation artifact
- question
- goal

### Pattern C: abstract argument + concrete ask
Example:
- “we cannot skip layers. now rewrite the current plan.”

Suggested split:
- concept / belief
- constraint
- concrete task

## 3. Layer heuristics
- If the statement defines what the system fundamentally is or is not, lean layer 1.
- If it defines user-facing capability or responsibility, lean layer 2.
- If it organizes objects, interfaces, or validation flow, lean layer 3.
- If it specifies code, tests, runtime, deployment, or configuration, lean layer 4.

## 4. When to use secondary layer
Use a secondary layer only when the statement directly spans two levels.
Do not add secondary layers just to sound comprehensive.

## 5. Confidence guidance
- high: the layer is directly stated or strongly implied
- medium: the layer is inferred from context but stable
- low: the statement is ambiguous and may shift after focus selection
