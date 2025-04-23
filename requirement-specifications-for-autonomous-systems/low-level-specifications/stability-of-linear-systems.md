# Stability of Linear Systems

Easier way to check linear systems for stability using eigenvalues.

Consider a simple autonomous system x(t + 1) = Ax(t), where A = an n by n matrix

Conditions for Stability:

Stable:

All eigenvalues must have an absolute value <=1 and eigenvalues with absolute value exactly 1 must have equal algebraic and geometric multiplicity.

To find **eigenvalues**, compute det(P - lambda * I) = 0
 
Globally Asymptotically Stable:

All eigenvalues must have an absolute value strictly less than 1.

Unstable:

If any eigenvalue has an absolute value greater than 1, the system is unstable.

**Algebraic mutliplicity**: The number of times an eigenvalue appears as a root of the characteristic polynomial (det(A - lambda * I) = 0)


If you solve for the eigenvalues and find (lambda - 1)^3 = 0, then lambda = 1 has an algebraic multiplicity of 3 (it appears three times).


**Geometric multiplicity**: The number of linearly independent eigenvectors associated with an eigenvalue

When you solve (A - lambda * I)v = 0 for v, how many independent solutions (eigenvectors) you find.

## Lyapunov Functions for Linear Systems

Choose V(x) = x transpose Px for some positive definite matrix P (any symmetric matrix whose eigenvalues are all positive). Remember that f(x) = Ax for some matrix A

- V(0) = 0 and V(x) > 0 for any nonzero x
- V(f(x)) - V(x) = A(x) transpose PAx - x transpose Px = x transpose (A transpose PA - P)x < 0 iff A transpose PA - P < 0 (all eigenvalues of the matrix are negative)

Theorem: Consider a simple autonomous system S = (Rn, Rn, {0}, F) with F(x, 0) = {f(x)}, where f(x)= A(x) for some matrix A. System S is globally asymptotically stable iff for any Q > 0 there exists P > 0 such that **A transpose PA - P = -Q**

- Choose any positive definite matrix Q (such as identity) and solve the above equation for matrix P. If P is also positive definite, this implies the system is globally asymptotically stable.

Simply plug in your chosen Q (such as identity), A, A transpose, and solve for P. To determine if the matrix P is positive definite, compute its determinant (ad - bc) and consider the first entry. If both are positive, it is positive definite.