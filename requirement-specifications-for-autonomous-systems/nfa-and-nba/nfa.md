# Nondeterministic Finite Automata (NFA)

Even if a set has members of finite length, the set itself can be infinite in cardinality. How can we store these languages inside the computer? The machine requires memory and the ability to recognize regular languages.

A NFA A is a tuple (Q, E, q, Q0, F) where:

- Q is a finite set of states
- E (sigma) is an alphabet
- q (delta): Q * E -> 2^Q is a transition function
- Q0 is a set of initial states
- F is a set of accepting states

## Accepted Language of an NFA

An **accepting** run of a finite word (of some alphabet) in the NFA is a finite sequence of states where the last state is in F (the set of accepting states). The accepted language of the NFA A, denoted by L(A), is the set of finite words accepted by A.

Two NFAs are said to be **equivalent** if their alphabets are equal.

## Synchronous Product of NFAs

How do we take the intersection of two sets with infinite cardinality?

For NFA Ai = (Qi, E, qi, Q0i, Fi) with i = 1, 2 (where both are defined over the same alphabet), the synchronous product automaton A1 x A2 = (Q1 x Q2, E, q, Q01 x Q02, F1 x F2) where:

The state transition map of the product is defined by the ability to go from q1 to q1' under A and q2 to q2' under A

L(A1 x A2) = A(A1) intersection L(A2) <-- the language of the synchronous product is the intersection of the corresponding language of the NFA

**Kleene's Theorem** states that a language L is regular if and only if there is a NFA recognizing it. The union, intersection, finite repetition, and concatenation of two regular languages are all regular.