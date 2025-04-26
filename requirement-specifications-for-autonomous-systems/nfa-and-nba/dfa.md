# Deterministic Finite Automata (DFA)

For any NFA, we can construct a DFA whose language is equal to the language of the NFA.

Given automata A = (Q, sigma, delta, Q0, F), A is deterministic if:

- |Q0| cardinality of the set of initial states <= 1
- |delta(q, A)| <= 1 for all states q in Q and all symbols A in sigma

Called **total** if the above conditions are exactly 1 (one outgoing transition)

In other words, from any state of the automata, under any symbols of the alphabet, we can have at most one transition. No non-determinism. We can utilize **powerset construction** to determinize any NFA.

The DFA is used to determine the complement language (make accepting states non-accepting and vice versa).