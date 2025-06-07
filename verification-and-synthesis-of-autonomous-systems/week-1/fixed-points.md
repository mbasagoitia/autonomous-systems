# Fixed Points

"Correct by construction"

Satisfactions and realizability of LTL form

Let S be a simple system (X, X0, U, F) with no blocking pair.

Let varphi be an LTL formula over AP.

Let L be a strict map (the labeling function).

Every element of the behavior (u, x) subset of B(S) induces a sequence w subset (2^AP)^omega (induces an infinite word over the alphabet)

Where:

w = L applied over (u, x) with w(t) = L(u(t), x(t))

P(varphi) is a property over 2^AP. We use L to define a property PL(varphi) over U x X:

PL(varphi)= {(u, x) subset (U x X)^omega | L applied over (u, x) subset P(varphi)}

We say that (u, x) satisfies varphi if (u, y) belongs to PL(varphi)

- S satisfies varphi under L if B(S) (behavior of the system) is subset of PL(varphi)
- varphi is realizable on S under L if PL(varphi) is realizable on S. In other words, there exists a system C (controller) which is feedback composable with S and B(C x S) is subset equal to PL(varphi)

LTL formula properties:

- Safety: varphi = always p
- Reachability: varphi = eventually p
- Persistence: varphi = eventually always p
- Recurrence: varphi = always eventually p
- Reactivity: always eventually p implies always eventually q

Depending on varphi, we derive an algorithm. The output of the algorithm is a set D subset of X

Two results:

- varphi is realizable on S under L iff X0 is subset of D
- If X0 is subset of D, then we derive a system C from D so that C x S (their feedback composition) satisfies varphi


## Fixed Point Algorithms

All algorithms are described by fixed point expressions

Central to the description is a monotone function: G: 2^x --> 2^x

A function is monotone if for Z, Z' subset of X, Z subset of Z' imples G(Z) is subset of G(Z')

A subset Z* subset of X is a fixed point of G if Z* = G(Z*)

A fixed point Z hat of G is called maximal fixed point of G if Z subset G(Z) implies Z subset of Z hat

A fixed point Z check of G is called minimal fixed point of G if G(Z) is subset of Z implies that Z check is subset of Z

nu (v) and mu (u) are used to denote the maximal and minimal fixed point of G, respectively

Z hat (maximal fixed point) = vZ.G(Z) and Z check (minimal fixed point) = uZ.G(Z)

## Computation of Fixed Points

Two types of iteration:

- Non-growing iterations
    - At iteration 0, we start from the whole state set X and then when we apply the fixed-point operation G, we start removings from the state set X. Eventually, you get a fixed point.
- Non-shrinking iterations  
    - At iteration 0, you start from an empty set and when you start applying the operator G, you add to the set until you get a fixed point.

### Theorem: Fixed Point Computation

Let G be a monotone function and X be finite. There exists integers i, j such that the maximal fixed point and the minimal fixed point all happen within a finite number of iterations. The maximal fixed point is going to be exactly the set which is constructed at iteration i and the minimal fixed point is exactly the set that is constructed at iteration j. This theorem is only valid if the state set X is finite. If X is not finite, we cannot guarantee termination of fixed point iteration.