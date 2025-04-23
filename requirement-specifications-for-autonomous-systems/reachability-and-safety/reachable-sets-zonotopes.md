# Computation of Reachable Sets via Zonotopes

Consider a simple system S = (X, X, U, F). We denote Reach(S) the reachable set of states in S (the set of all of its reachable states).

A direct approach to safety verification problems is the computation of an over-approximation of the reachable set.

We want to show that this over-approximation W does not intersect with B (bad set), and conclude that Reach(S) also does not intersect with B.

To provide efficient computation of the reachable set or the over-approximation W, we can use **zonotopes** to represent all the sets appearing in the computations of reachable sets because of their nice properties.

A zonotope is a convex polytope that is the image of the unit hypercube under an affine transformation. It is a set Z in the set of Rn described by:

Z = {x set of all points in Rn | (where) x = c + summation from i = 1 to k of lambdai * vi, where -1 <= lambda i <= 1}

In other words, Z is a set in Rn described by this set of points in Rn in which x = c (a vector) plus the linear combination of k vectors vi with coefficients (lambda i) between -1 and 1.

Where c, vi ... vk are vectors in Rn, c is the center of the zonotope, and v1 ... vk are called the generators of the zonotope.

## Properties of Zonotopes

We denote the zonotope Z by its center and its set of generators: V = (c, < v1 ... vk >) where point c is the center of the zonotope.

The Minkowski sum of two sets Z and W subset of Rn is the set:

Z + W = {x subset of Rn | x = z + w for some z subset of Z and w subset of W}

The class of zonotopes is closed under linear transformations and Minkowski sum.

Consider two zonotopes Za = (ca, < va1 ... vak >) and Zb = (cb, < vb1 ... vbl >) in Rn and let g(x) = Gx be a linear transformation. The following holds:

- Za + Zb = (ca + cb, < va1 ... vak, vb1 ... vbl >)
- g(Za) = (Gca, < Gva1 ... Gvak >)

## Computing Over-Approximation of Reachable Set

Let's start with an autonomous linear system S = (Rn, Rn, {0}, {f}) where f(x) = Ax

Rt(Z) is the set of points reached at t time steps by state trajectories of S starting in Z:

Rt(Z) = {x subset of Rn | x = A^t * x0, for some x0 subset of Z}

and by R[0; T](Z) is the set of points reached at time t subset of [0; T] (this is an interval; points reachable in this interval 0 to T) by state trajectories S starting in Z:

R[0; T](Z) = U (union) of Rt(Z) when t is changing from 0 to T

## Computation of Reachable Sets for ISS Systems

Another way of computing over-approximation of a reachable set is by using ISS property of the system. Do not need to assume system is linear. Reachable sets starting from origin and with unit peak inputs:

RT = {x(T) | x(t + 1) = f(x(t), u(t)), x(0) = 0, ||u||infinity <= 1}

The set of points that can be reached from x(0) = 0 with inputs not exceeding unit magnitude. Difficult to find exactly, but methods exist to find over-approximations. ISS gives a very conservative bound.

A less conservative estimate can be computed with level sets:

Find a positive definite function V and a constant c > 0 such that:

When the norm of the input is bounded by 1 and V(x) <= c, V(f(x, u)) - V(x) <= 0

Then, the level set Omega c is defined as {x: V(x) <= c} (the set of all points in which V(x) <= c) contains all of the reachable set.

If we can find a function V satisfying this condition, we can conclude that the set x in which V(x) <= c always contains the set of reachable state for future time.

Note: input u is bounded by 1 if u transpose * u <= 1

## Safety Certification

One of the advantages of computing an over-approximation of the reachable set of a state is to verify if the system enters a bad/unsafe region.

Given an unsafe set U, we want to show that the intersection of RT intersection with U = empty set. Since we cannot compute RT directly, we can compute the level set of a quadratic function which contains the actual reachable set of the system. V is a quadratic function (V(x) = x transpose Px), so the level set is in the form of an ellipsoid. {x | V(x) <= 1} 

If we can show that this ellipsoid does not intersect with U (unsafe set), it means the reachable set does not intersect with U either. Implies safety of system.

An additional safety certification can use **barrier functions** to show that for every x which is subset of U (unsafe), V(x) > 1. Equivalent to finding a positive definite matrix P such that P >= a a transpose