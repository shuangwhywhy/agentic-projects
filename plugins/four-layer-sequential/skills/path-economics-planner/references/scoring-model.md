# Qualitative Scoring Model

## 1. Why use qualitative scoring
Exact token counts and exact success probabilities are often unjustified at planning time.
Use structured estimates to make tradeoffs visible without faking precision.

## 2. Suggested 1 to 5 scale
- 1: very low
- 2: low
- 3: medium
- 4: high
- 5: very high

## 3. Cost-side cues
### Token or time cost
Increase the score when:
- more layer crossings are required
- more reversals or loops are required
- more source material must stay active
- more validation steps are mandatory

### Orchestration burden
Increase the score when:
- the route depends on many intermediate states
- multiple assumptions must be tracked
- earlier outputs constrain later steps tightly

## 4. Benefit-side cues
### Quality lift
Increase the score when the longer route:
- resolves upstream ambiguity that would otherwise poison downstream work
- produces a more coherent cross-layer answer
- makes hidden assumptions explicit

### Success lift
Increase the score when the longer route:
- materially improves the chance of satisfying the user's actual goal
- avoids a common failure mode of shorter routes

### Risk reduction
Increase the score when the longer route:
- prevents jump-layer decisions
- exposes contradictory assumptions earlier
- creates a better basis for later execution or review

## 5. Net judgment heuristic
A longer route is usually justified when:
- benefit rises by at least one full band on the user's real objective, and
- the additional cost does not break the current budget or responsiveness need.

A shorter route is usually justified when:
- the added traversal mostly increases rigor theater, not actual outcome quality.

## 6. Checkpoint design rule
Prefer routes that contain useful checkpoints.
A useful checkpoint can either:
- confirm enough to stop early, or
- reveal enough to justify paying for the next leg of the route.
