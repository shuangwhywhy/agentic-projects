# Path Topologies

## 1. Same-layer
Use when both the starting problem and the desired resolution live in the same layer.
Example:
- compare two concepts without requesting product, architecture, or implementation work.

## 2. Descent
Use when an upper-layer statement must eventually become lower-layer output.
Example:
- concept -> product -> architecture -> implementation.

## 3. Reverse-trace
Use when a lower-layer artifact is given, but the user wants a higher-layer explanation or reframing.
Example:
- code -> architecture -> product -> concept.

## 4. V-shape
Use when the route must go one direction, hit a blocker, then turn after re-grounding.
Example:
- product -> architecture, realize concept is underspecified, return to concept, then descend again.

## 5. Multi-pass
Use when more than one turning point is structurally necessary.
Reserve this label for cases where a single V-shape is not enough.

## 6. Start vs source material
The start layer is where the active reasoning must begin, not merely where the evidence was found.
A product question may cite code, but still start in layer 2 if product boundary is the first unresolved issue.
