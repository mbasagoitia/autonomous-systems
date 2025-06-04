# Verification of Regular Safety Properties

## Checking Regular Safety Properties

Linear time properties

- An LT property over AP is a language P of infinite words over the alphabet 2^AP
- If S is a simple system without any blocking state, then S satisfies the LT property P under an appropriate labeling map iff L(B(S)) = P
    - A labeling map takes a state and maps it to the symbols of the alphabet (which are subsets of AP)

Regular safety properties

Let P be a regular safety property over AP and bad(P) = set of all bad prefixes of P, which is subset 2^AP

P is called **regular safety** iff bad(P) is regular, i.e. bad(P) = L(A) for some NFA A over the alphabet 2^AP

In other words, if bad(P) (set of all bad prefixes of P) can be recognized using a NFA, then P is a regular safety property

## Verifying Regular Safety Properties

Given a finite simple system S without blocking states and a regular safety property P (represented by an NFA for its bad prefixes), the question is: does S satisfy P? 

Method: relies on an analogy between these tasks:

- Checking language inclusion for NFA
- Model checking regular safety properties

Safety checking involves invariant checking between the product between the system S and the NFA accepting all bad(P), known as A: 

If the final state of the product never gets visited, this implies the system satisfies the original safety property P.

Any path on the product that reaches the accepting state is a counterexample of why the system violates P.

**Does S product A satisfy "never final state?**

## Product of a System

Consider a simple system S = (X, X0, U, F) together with a labeling map L and an NFA A = (Q, 2^AP, delta, Q0, F)

Their product system is **S product A = (X product Q, X0', U, F')**

where:

x' is subset of F(x, u) and q' is subset delta(q, L(x')) / (x', q') is subset F'((x, q), u)

### State Transtion of Product System

We need to define how the state transition map is defined for the product system: starting from a state in the product (x, q), under input u, we go to new state pairs (x', q'), iff in the original system S, starting from x under u, I go to x' AND inside the NFA, starting from q, under the label of x' I go to q'.

### Initial States of Product System

The set of initial states for the product is the set of all pairs (x0, q) in which x0 is an initial state of the original system S AND q is the successor in the NFA if you start from any initial states in the NFA and under the label of x0.