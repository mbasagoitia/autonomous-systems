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

Any accepted state run can be broken into two parts: a finite prefix/word beginning with the inital state that eventually leads to an accepting state, and the accepting state with a self loop.

In an NFA in which there are outgoing transitions from the accepting state, you can always construct another NFA with the same language where there are no outgoing transitions from the accepting state.

To create finite/infinite repetition, need to add a transition to the successor of the initial state under the same symbol/transition.

To concatenate NFA with NBA, make accepting states of NFA not accepting, and instead transition from the (previously accepting) state to successors of initial states of NBA under same symbols. Initial states of NBA is are longer the initial state.