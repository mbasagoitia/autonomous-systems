# Feedback Refinement Relations

## Motivation

Question of interest: how are we able to leverage verification techniques and synthesis algorithms for infinite systems?

We need to construct a finite abstraction of continuous space systems. The "main ingredient" is the establishment of a relation between the original system and its finite abstraction, which is called **feedback refinement relation.**

For example, suppose we have a controller C for system S2 and we know that this closed loop (feedback composition of C and S2) satisfies a specification varphi. How can we modify C in the abstract domain to C' in the concrete domain so that C' is feedback composable with S1 and their feedback composition enforces varphi?

The construction of C' is often called **controller refinement** where C is refined to C'.

How should we define the relation between S1 and S2?

### System Replacement

Let's say we are given an interconnected system consisting of a number of subsystems S1, S2, S3, S4 that satisfies varphi. For some reason, we may want to replace S1 with S1' (because S1 is broken, S1' performs better, etc.).

What are the conditions so that the new system S1', S2, S3, S4 still satisfies varphi?

If we are able to establish a relation between S1 and S1', we don't need to worry about the satisfaction of the overall system.

## Definition of Feedback Refinement Relation

**Admissible Inputs**: Given a system S = (X, X0, U, F), we define the set of admissible inputs at state x by:
Us(x) = {u subset of U | F(x, u) != empty} <-- the set of all inputs in which the pair (x, u) is non-blocking

Let Si = (Xi, Xi0, Ui, Fi), i = {1, 2} be two simple systems and assume U2 (input set) is subset equal U1.

A strict relation Q subset equal X1 x X2 is a **feedback refinement relation** from S1 to S2 if the following holds for all (x1, x2) inside of Q (the relation):

- If x1 is an initial state in system 1, then x2 has to be an initial state in system 2
- Every admissible input of state x2 in system 2 should be subset equal to admissible inputs of state x1 in system 1
- Every successor x1' inside of F1(x1, u) when mapped to X2 via Q is contained in F2(x2, u)