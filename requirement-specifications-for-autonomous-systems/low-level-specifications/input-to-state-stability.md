# Input to State Stability (ISS)

Measure for checking robustness of a system.

Consider a simple system S = (X, X, U, F) where F(x, u) = {f(x, u)}, where X and U are normed vector spaces. x = 0 is the equilibrium when u = 0; f(0, 0) = 0. This means that when system is at equilibrium and input is 0, it remains at equilibrium.

What if input is not 0?

S is said to be ISS if ||x(t)|| <= B(||x(0)||, t) + y(max ||u(tau)||) for any behavior (u, x) of S for some KL function B and K function y.

This means that the norm of the state of the system at any time t is bounded by these two terms/functions.
    - First term: as t goes to infinity, it vanishes (forgets effect of initial condition)
    - If input is bounded, norm of x(t) for any time remains bounded

- KL (B) function is a function with domain positive real numbers of the norm of the initial state of the system and t
    - In general form of KL function B(r, s), for any fixed s, the function is strictly increasing with respect to r, and for each fixed r that is not 0, the function is decreasing with respect to s.
- The K (y) function with domain positive real numbers and only depends on the norm of the input signal
    - The K function is strictly increasing and y(0) = 0; belongs to class K infinity if y(r) approaches infinity as r approaches infinity

Say S is globally asymptotically stable. If we apply a bounded input to the system, does it remain stable?

For **linear systems**, asymptotic stability of a zero input function implies ISS (robustness) of the state under bounded inputs. 

This is NOT the case for nonlinear systems!

## Lyapunov Theorem for ISS

A system being ISS implies:

- The zero input version is globally asymptotically stable
- u(t) (input trajectory) --> 0 as t --> infinity; x(t) (state trajectory) --> 0 as t --> infinity

How do we check ISS for nonlinear systems?

System S is ISS if there exists a K infinity functions alpha (underline), alpha (overline), k, and y, and a continuous function V whose domain is X such that:

- a (underline) (||x||) <= V(x) <= a (overline) (||x||)
- V(f(x, u)) - V(x) <= -k(V(x)) + y(||u||) for any x and u

Where V is the ISS Lyapunov function

## Stability of Series Interconnections

Consider two simples systems, S1 = (X1, X1, {0}, {f1}) and S2 = (X2, X2, X1, {f2}) (S1 is autonomous and S2 is not autonomous and whose input is the state of S1)

If x1 = 0 is globally asymptotically stable for S1 and the zero input version of S2 is globally asymptotically stable, can we conclude that (x1, x2) = 0 is also globally asymptotically stable for the series interconnection? Not necessarily!

If both systems are ISS with respect to their inputs, then their series interconnection is ISS with respect to inputs u.

## Stability of Feedback Interconnections

Consider two simples systems, S1 = (X1, X1, X2, {f1}) and S2 = (X2, X2, X1, {f2}) (both functions take each other's output as input)

If both systems are ISS with respect to their inputs, is the feedback interconnection globally asymptotically stable? Not necessarily! Because of circular dependency.

**Small gain theorem:**

If S1 is ISS as:

||x(t)|| <= B1(||x1(0)||, t) + y1 * max ||x1(tau)|| <-- note linear K infinity function

and if S2 is ISS as:

||x(t)|| <= B2(||x2(0)||, t) + y2 * max ||x2(tau)|| <-- note linear K infinity function

where y1 and y2 are both > 0,

if y1 * y2 < 1, then S1 x S2 (feedback interconnection) is globally asymptotically stable.