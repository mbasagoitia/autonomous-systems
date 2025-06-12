# Computation of Abstractions

Let's say that X2 is a cover of X1; in other words, X2 is a set of non-empty subsets of X1 and the union of all members of X2 covers all of X1.

- Every cell x2 inside of X2 is a subset of X1
- The quantizer Q is the set membership relation
- For a given x1 of X1, the quantizer Q picks x2 inside of X2 in a non-deterministic fashion so that x1 is inside of x2

Let Si = {Xi, Xi0, Ui, Fi} be two systems i = {1, 2} and X2 be a cover by non-empty sets of X1.

Theorem: Computation of Abstractions

The set membership relation is a feedback refinement relation from S1 to S2 iff:

1. x1 is an initial state in the original system S1, and if x1 belongs to a cover element x2, then x2 has to be an initial state in S2.
2. State input set of S2 is subset equal input set of S1, and if a point x1 belongs to a cover element x2, that implies that the admissible of cover element x2 in S2 has to be subset equal of admissible input at state x1 in S1.
3. Start from a cover element x2, apply an input u which is admissible at cover element x2. Now, you must compute the set of all successors in S1 when you start from the cover element x2 under u. That will be a set inside of X1. The intersection of that set with other cover elements inside the state set of S2. If that intersection is non-empty in the abstract domain, you have to put a transition from cover element x2 to those other cover elements which are intersecting with this reachable set under input u.

Regarding the third condition, computing F1(x2, u) requires computation of reachable sets