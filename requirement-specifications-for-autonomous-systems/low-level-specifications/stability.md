# Stability

## Normed Vector Spaces

A **norm** is a function that takes a vector x and returns a non-negative real number.

Norms help define how far the system is from its desired state (e.g., equilibrium). If the norm is small, the system is close to the target. Stability, then, is about whether the norm stays small or gets smaller over time.

State set X is a normed vector space if there exists a real-valued norm ||⋅|| satisfying:

- ||x|| >= 0 (norm of any state x belonging to X is always greater than 0); ||x|| = 0 iff x = 0
- ||x + x'|| <= ||x|| + ||x'|| for any x and x' belonging to X (triangle inequality)
- ||ax|| = |a| * ||x|| (norm of a * x, where a is a real number and x is a state vector inside of X, equals the absolute value of a * ||x||)

The equilibrium x = 0 is **stable** if for each e > 0, there exists q > 0 such that ||x(0)|| <= q --> ||x(t)|| <= e for all future time.

Interpretation: Small initial deviations (within a "ball" of radius q) stay small (within radius e) for all time

The equilibrium x = 0 is **asymptotically stable** if it is stable and ||x(t)|| --> 0 as t --> infinity for all x(0) in an open neighborhood of x = 0.

Interpretation: Trajectories not only stay close to equilibrium but actually converge to it.

It is **globally asymptotically stable** if it is stable and x(t) --> 0 for every x(0) (any initial condition in the state space X).