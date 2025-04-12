# Timed Automata

## Syntax

Quantitative time information is needed in some applications; describes amount of time we are in a specific state.

**Timed automata** introduces a finite set of real-valued clocks, which:

- Can reset to zero by transitions
- Show the time elapsed since the last transition
- Transitions are labeled by time conditions

TA = (L, L0, U, -->, C, Inv)

where:

- L is a finite set of locations
- L0 is a set of initial locations
- U is a finite set of actions
- C is a finite set of clocks {x1 ... xn}
- Inv: L -> P is an invariant-assignment function, where P is a set of timing conditions (xj > q; xj <= q)
- --> is the state transition relation
    - Given by the tuple (l, u, p, l', Cres)
        - l = current location
        - u = input symbol
        - p = enabling (timing) conditions, evaluates to 0 or 1
        - l' = next location
        - Cres = subset of clocks that are reset

## How Timed Automata Evolve

- Initialize the location at l0 and set all clocks to zero
- If p evaluates to 1 and Inv(current state) is valid, the transition can be executed, and all assigned clocks (Cres) are reset

Invariants are the only means to force transition to be taken. If you are in a location and the time is elapsing, the invariants might get violated--this will force a transition.

## Example: Real-Time Scheduling

Timeliness is formulated by equipping each software task with a worst-case execution time C, a relative deadline D, and (in periodic tasks) a period T. A task becomes active every T units of time and its execution must finish no later than D units of time after becoming active. A scheduler decides which of the active tasks should be executed by the processor. The decision process takes into account period, deadline, and fact that execution may take C units of time to complete (worst-case). The set of tasks is schedulable if it can be executed without violating any of the deadlines.

## System Representation of Timed Automata

The system S = (X, X0, U, F) associated with timed automation is given by:

- X = {sleep, active, error, execute}; discrete and continuous values
- X0 = {(xa, xb)}
- U = {awake, expired, starting, finished}; discrete and continuous inputs; union of the two sets
- (xa', xb') is part of F((xa, xb), u) iff one of the two following conditions holds:
    - Staying within the initial location and some conditions are satisfied (clock keeps running even if we don't take discrete transition)
    - Changing the location, the location changes based on the input u and the clock variables get reset based on the discrete transitions