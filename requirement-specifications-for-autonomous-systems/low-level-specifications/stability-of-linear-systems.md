# Stability of Linear Systems

Easier way to check linear systems for stability using eigenvalues.

Consider a simple autonomous system x(t + 1) = Ax(t), where A = an n by n matrix

Conditions for Stability:

Stable:

All eigenvalues must have an absolute value <=1 and eigenvalues with absolute value exactly 1 must have equal algebraic and geometric multiplicity.

Globally Asymptotically Stable:

All eigenvalues must have an absolute value strictly less than 1.

Unstable:

If any eigenvalue has an absolute value greater than 1, the system is unstable.

**Algebraic mutliplicity**: The number of times an eigenvalue appears as a root of the characteristic polynomial

**Geometric multiplicity**: The number of linearly independent eigenvectors associated with an eigenvalue