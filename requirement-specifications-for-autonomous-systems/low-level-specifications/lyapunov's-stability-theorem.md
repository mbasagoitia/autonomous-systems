# Lyapunov's Stability Theorem

Formal verification approach for stability of simple autonomous systems

Given a simple autonomous system with a state transition function f(x), the equilibrium point is f(0) = 0. If the system starts at 0, it stays at 0. The domain D is an open subset of n-dimensional Euclidean space containing the origin x = 0.

A Lyapunov Function V(x) must satisfy the following conditions:

- V(0) = 0 <- at the equilibrium point, the function value is exactly 0
- V(x) > 0 for all x != 0 in D <- positive definite; away from equilibrium, V is positive
- V(f(x)) - V(x) <= 0 for all x in D <- Negative semi-definite; value of V doesn't increase along system trajectories

A system is **stable** if:

- V(f(x)) - V(x) <= 0 for all x

**Asymptotically stable** if:

- V(f(x)) - V(x) < 0 for all x for all x != 0

**Globally asymptotically stable** if:

- Asymptotically stable
- D = R^n (entire space)
- ||x|| --> infinity implies V(x) --> infinity (radially unbounded)
