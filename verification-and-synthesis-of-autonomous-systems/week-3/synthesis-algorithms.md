# Synthesis Algorithms

## Safety and Reachability

The **pre map** of a simple system S for a set Z which is a subset of U x X, known as pre(Z), is the set of non-blocking input/state pairs for which all successor states are in the projection of Z on X.

Pre is monotone

Simple trick:

Ask: to find pre(Z), from which states and under which inputs can I reach this state Z? These transitions must be deterministic! If you can reach multiple different states under the same input from a given state, that state should NOT be included inside of pre(Z).

## Synthesis for Safety Specifications

Given a simple system S, labeling map L, and safety formula varphi = always varsi, we need to determine if varphi is realizable on S under L. If it is, provide a system C that is feedback composable with S so that C x S satisfies varphi.

Zv is the set of all input state pairs such that, when you apply L to them, L(u, x) satisfies the propositional formula varsi

The monotone function G: 2^U x X --> 2^U x X is defined by G(Z) = pre(Z) intersection with Z varsi. This intersection is also monotone.

### Theorem: Realizability for Safety

varphi = always varsi is realizable on S under L iff X0 (set of initial states) is subset equal to the projection of maximal fixed point over the state

### Corollary: Controller Synthesis for Safety

Suppose that the set of initial states is subset equal of the projection of the maximal fixed point over the state set. Let C = ({q}, {q}, X, X, U, Fc, Hc) be a static system with a strict transition function and strict output map Hc(q, x) = H'c(x) * {x} where H'c satisfies:

- u if (u, x) belongs to projection of the maximal fixed point over the state set
- U (any input) otherwise 

Then, C is feedback composable with S and C x S satisifes varphi

## Synthesis for Reachability Specifications

Reachability formula: varphi = eventually varsi

The monotone function G: 2^U x X --> 2^U x X is defined by G(Z) = pre(Z) union with Z varsi. This union is also monotone.

### Theorem: Realizability for Reachability

varphi = eventually varsi is realizable on S under L iff X0 (set of initial states) is subset equal to the projection of minimal fixed point over the state

How do we synthesize a controller for reachability? We need to use a function j(x)

H'c(x) = 

- u if (u, x) belongs to the corresponding set in the fixed point iteration after iteration j(x) if j(x) < infinity
- U (any input) otherwise 

Then, C is feedback composable with S and C x S satisifes varphi

j(x) = inf({i subset of real numbers} | s.t. x is subset of minimal fixed point projection)

In other words, j(x) = lowest index i in which x would have been inside the projection of the ith iteration set that comes from the fixed point iteration; the index Zi in which the state we are interested in first appears in the fixed point iteration.

## Synthesis Algorithms for Persistence, Recurrence, and Beyond