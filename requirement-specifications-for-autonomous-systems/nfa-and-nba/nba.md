# Nondeterministic Buchi Automata (NBA)

How can we represent omega-regular languages using a finite automata that can be stored inside a computer?

NBAs use an omega-automata, which are acceptors for infinite words. They also have the same syntax as for NFAs, and semantics are the language of infinite words.

NBA A = (Q, E (sigma), delta, Q0, F) where:

- Q = finite set of states
- E = alphabet
- sigma = Q x E transition relation
- Q0 = set of initial states
- F = set of final states/accepting states

A run for infinite words is an infinite state sequence in which Q0 belongs to Q and Q1 is the successor under the label A0. The state run is accepting if there exists infinitely many indices i such that Qi belongs to the set of accepting states.

**A word is accepted if its corresponding state run visits an accepting state infinitely often.**

The accepted language Lw(A) is the set of infinite words over E that have an accepting run in A.

## NBA for Linear Time Properties

