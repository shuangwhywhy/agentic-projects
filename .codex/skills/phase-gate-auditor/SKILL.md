---
name: phase-gate-auditor
description: analyze a project against a four-layer phase model and produce a strict stage-gate review in simplified chinese. use when the user wants to judge whether a project can move to the next stage, whether work should stay in repo 1 versus move into repo 2, or whether remaining uncertainty is still upstream. support current project context first, then a specified repo, then uploaded files, then pasted text. always list the full issue inventory visible in the provided materials, label each issue as either must solve now or may carry into the next stage, explain each label from complete content, state any scope limits, give a preliminary overall judgment when content is incomplete, and end with concrete next actions.
---

# phase gate auditor

Use this skill to perform a strict project phase-gate review under a four-layer model:

- layer 1: concept
- layer 2: product definition
- layer 3: architecture / system design
- layer 4: implementation

Do not start with a high-level verdict. First build the issue inventory from the available content, then classify each issue, then conclude.

## Source priority

Use sources in this order whenever available:

1. current project context already available in the active agent/system context
2. the repo or repos explicitly specified by the user
3. uploaded files in the conversation
4. text pasted directly by the user

If multiple source types are available, prefer the higher-priority source for authoritative statements and use lower-priority sources only to supplement or fill gaps.

## Core rule

Classify every visible issue into exactly one of two buckets:

- **Must resolve now**
- **May carry into next stage**

No third bucket.

Use this test:

### Mark as Must resolve now when
The unresolved issue would change any of the following if its answer changes:

- what the project fundamentally is solving
- the product object, target boundary, or success condition
- the architecture backbone, core object model, module boundary, state flow, governance structure, or audit structure
- the phase-gate decision itself

Also mark it as Must resolve now when the next stage would be forced to redefine upstream content instead of only inheriting and refining it.

### Mark as May carry into next stage when
The unresolved issue affects only one or more of the following:

- local optimization
- implementation strategy
- interface or storage shape
- internal module refinement
- execution sequencing
- details that do not rewrite the current layer's backbone

## Review workflow

Follow this sequence every time.

### Step 1: declare scope
State exactly what content you reviewed and what you did not review.

Always say whether the result is:

- a full-project judgment, or
- a judgment limited to the reviewed scope

### Step 2: extract the full visible issue inventory
List every issue that is materially visible from the reviewed content.

Do not jump straight to "key issues". Start with the full visible inventory for the current scope.

Treat these as issue sources:

- explicit open questions
- future-work items
- items that the content says must still be answered
- missing but required definitions or decisions
- contradictions between constraints
- gates, red lines, or required outputs that are not yet satisfied

Do not manufacture issues that are not supported by content.

### Step 3: classify every issue
For each issue, decide exactly one label:

- Must resolve now
- May carry into next stage

The label must be based on content impact, not on the emotional tone of the documents.

### Step 4: justify every classification from content
For each issue, provide:

- the specific reason it belongs in that bucket
- the direct supporting content
- the consequence if it is left unresolved

When citing content, prefer complete, direct statements over impressions.

### Step 5: determine the phase-gate result
After classifying all issues, apply this rule:

- if any **Must resolve now** issue remains open, do **not** approve movement into the next stage
- if zero **Must resolve now** issues remain within the reviewed scope, approve movement into the next stage within that scope

For repo 1 vs repo 2 style reviews, the default interpretation is:

- unresolved upstream backbone issues -> stay in repo 1
- only downstream refinement and implementation issues remain -> may move into repo 2

### Step 6: give concrete next actions
End with a concrete action list ordered by dependency.

For each next action, say:

- what to resolve
- why it comes now
- what artifact or decision should be produced
- what stage movement it unlocks

## Incomplete-content rule

When content is incomplete, do not pretend to have a full-project judgment.

Instead, you must output both:

1. a **specific statement on inability to judge**
2. an **overall preliminary analysis** based only on the reviewed scope

In that case:

- still build the visible issue inventory for the current scope
- still classify each visible issue
- explicitly list which missing materials prevent a full judgment
- clearly separate scoped findings from whole-project claims

## Output format

Use this structure in simplified chinese.

# Phase Gate Audit Review

## 1. Review Scope
- Reviewed content:
- Unreviewed but related content:
- Conclusion type: Full-project judgment / Scoped judgment

## 2. Full Issue Inventory
For each issue use this template:

### Issue N: <Issue Name>
- Classification: Must resolve now / May carry into next stage
- Layer: L1 / L2 / L3 / L4
- Content-based evidence:
- Rationale for classification:
- Consequences if unresolved:
- Blocks next stage movement: Yes / No

## 3. Phase Conclusion
- Approved for next stage movement: Yes / No
- Conclusion rationale:
- If limited scope, state exactly why only a scoped judgment is possible

## 4. Concrete Next Actions
Use an ordered list.
For each action include:
- Action
- Target artifact
- Resolves which issue
- Unlocks what

## Non-negotiable behavior

- Do not start with a verdict before listing the issue inventory.
- Do not collapse the inventory into only "top issues" unless the user explicitly asks for a shorter version after the full review.
- Do not use vague buckets like "depends" or "maybe later".
- Do not treat the mere existence of a template, file, or gate as proof that the underlying issue is resolved.
- Do not confuse topic-level maturity with whole-project maturity.
- Do not hide scope limits. State them explicitly.
- Do not invent certainty when source coverage is incomplete.

## Good review style

Be strict but not rigid.

A complex project is allowed to carry dynamic issues forward. The key question is not whether open issues exist, but whether any open issue would rewrite the current layer's backbone. Use that distinction consistently.
