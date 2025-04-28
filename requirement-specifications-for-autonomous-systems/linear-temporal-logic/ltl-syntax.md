# Linear Temporal Logic (Syntax)

## Propositional formulas

Let AP be a finite set of atomic propositions. AP introduces the alphabet, which is the powerset of atomic propositions. We can use negation and disjunction to construct propositional formulas. An alphabet letter w subset equal to AP satisfies a propositional formula v if (w, v) is an element of the satisfaction relation, which is defined as follows:

Let p be subset equal to AP and q, v be two propositional formulas.

- w satisfies p if p is inside w
- w satisfies NOT q if w does not satisfy q
- w satisfies q OR v if w satisfies q or v

Abbreviations:

- true: NOT p OR p
- q --> v: NOT q OR v
- q AND v: NOT(NOT q OR NOT v)

## Linear Temporal Logic Syntax

- ◯: next
- U: until
- □ : always/globally
- ◇ : eventually/finally
- ¬ : negation
- → : implication  

Abbreviations:

- ◇q = true until q
- □q = NOT ◇ NOT q

◯ (next) and □ (always) must not be preceded by any LTL formulas; they must be the first argument

U must be preceded by an LTL formula (something until something else)

## Semantics

Let q be an LTL formula over AP and w is an infinite word of the powerset (alphabet). We say that q satisfies q at time t denoted by w, t satisfies q if (w(t), q) is an element of the satisfaction relation.

- w, t satisfies p if p is inside w(t)
- w, t satisfies ◯q if w, t+1 satisfies q

We say that w satisfies q if w satisfies q at time t = 0; w satisfies q = w, 0 satisifes q

The set of all satisfying sequences is denoted by P(q)