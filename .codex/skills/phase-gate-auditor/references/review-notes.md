# review notes

Use these reminders while auditing projects.

## 1. Distinguish issue count from blocking count
A project may have many open issues and still move forward if all remaining issues are downstream refinements.

The blocking test is:
- does this issue rewrite the current layer's backbone?
- does this issue force the next stage to redefine upstream content?

If yes, classify it as Must resolve now.

## 2. Common signals that an issue is backbone-level

### layer 1
- the project's core purpose is still moving
- repo 1 / repo 2 or stage responsibilities are still unstable
- major principles still conflict

### layer 2
- core object or target boundary is still moving
- success condition is still moving
- critical semantics are not yet fixed

### layer 3
- core object model is still open
- module boundary is still open
- state flow is still open
- governance or audit structure is still open

### layer 4
- the project is still deciding what should exist rather than how to build it
- architecture outputs required for implementation still do not exist

## 3. Common signals that an issue may be carried forward
- local design choice within a fixed module boundary
- interface shape optimization after the object model is fixed
- storage or execution strategy that does not rewrite architecture backbone
- implementation sequencing, rollout strategy, or internal refactor planning

## 4. Scope discipline
Always say whether the finding is:
- full-project, or
- limited to the reviewed materials

Never generalize from a topic packet to whole-project maturity unless the reviewed content itself explicitly claims full-project coverage.
