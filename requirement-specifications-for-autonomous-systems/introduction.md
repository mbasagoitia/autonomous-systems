# Introduction

We use **linear temporal logic** or **automata** on (in)finite strings to express the high-level description of the expected system behavior. This is a formal, unambiguous way of describing complex properties of interest for autonomous systems.

## Notation

- □ : always
- ◇ : eventually
- ¬ : negation
- → : implication  

## Temporal Property Types

- Safety properties: □ ¬B (the system should never enter the bad set B)
- Reachability: ◇T (Eventually reach a target)
- Persistence: ◇□T (Eventually reach T and stay there)
- Recurrence: □◇T (Visit T repeatedly)
- Reactive property: □◇A → □◇G (If A is always eventually true, G must be too)
- Stable response: ◇□A → ◇□G (If A eventually becomes always true, G must also eventually become always true)