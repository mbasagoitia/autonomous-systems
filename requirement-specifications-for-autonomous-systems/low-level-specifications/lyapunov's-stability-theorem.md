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

## Lyapunov Functions for Linear Systems

Choose V(x) = x transpose Px for some positive definite matrix P (any symmetric matrix whose eigenvalues are all positive). Remember that f(x) = Ax for some matrix A

- V(0) = 0 and V(x) > 0 for any nonzero x
- V(f(x)) - V(x) = A(x) transpose PAx - x transpose Px = x transpose (A transpose PA - P)x < 0 iff A transpose PA - P < 0 (all eigenvalues of the matrix are negative)

Theorem: Consider a simple autonomous system S = (Rn, Rn, {0}, F) with F(x, 0) = {f(x)}, where f(x)= A(x) for some matrix A. System S is globally asymptotically stable iff for any Q > 0 there exists P > 0 such that **A transpose PA - P = -Q**

- Choose any positive definite matrix Q (such as identity) and solve the above equation for matrix P. If P is also positive definite, this implies the system is globally asymptotically stable.

Simply plug in your chosen Q (such as identity), A, A transpose, and solve for P. To determine if the matrix P is positive definite, compute its determinant (ad - bc) and consider the first entry. If both are positive, it is positive definite.