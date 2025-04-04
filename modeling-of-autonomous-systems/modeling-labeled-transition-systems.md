# Modeling Labeled Transition Systems as Systems

TS = (S, Act, -->, I, AP, L)

AP (atomic proposition) and L (labeling function) can be ignored for now because they have to do with properties of interest.

Essentially, the evolution of the system is given by (S, Act, -->), described as a simple system (X, X0, U, F) where:

- X = S (state set)
- X0 = I (initial state set)
- U = Act (set of external inputs)
- x' (part of F(x, u)) <-> (x, u, x') (part of -->) (transition relation)