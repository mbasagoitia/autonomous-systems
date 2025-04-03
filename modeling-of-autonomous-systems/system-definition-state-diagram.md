# System's Definition and its State Diagram

Modeling framework contains these two main equations:

- x(t + 1) = F(x(t), v(t)) <-- the state value at time t + 1 is inside a function of a state value at the current time and internal value at the current time

- (y(t), v(t)) = H(x(t), u(t)) <-- the output at the current time and the internal input at the current time is inside a function of the state at the current time and external input at the current time

A general definition of a **system** S is a tuple S = (X, X0, U, V, Y, F, H) where:

- X, U, V, Y are nonempty sets
- X is the state alphabet
- X0 is the initial state alphabet (and is a subset of X)
- U is the external input alphabet
- V is the internal input alphabet
- Y is the output alphabet

- H: X * U -> Y * V is the output function (set-valued map; assumed to be strict)
- F: X * V -> X is the transition function (set-valued map)

A set-valued map (also called a multifunction) is a generalization of a function where instead of assigning a single output to each input, it assigns a set of possible outputs, allowing for uncertainty or multiple possible behaviors.

A system is:

- Finite if X, U, V, Y are finite (if not, it is infinite)
- Autonomous if U is a singleton (from outside, we cannot affect the behavior of the system)
- Deterministic/nondeterministic (deterministic if the set F(x, v) has at most 1 element)
- Basic if U = V (external and internal input alphabets are the same)
- Static if X is a singelton (system does not have any memory)
- Moore if the output does not depend explicitly on the input
- Moore with state output if X = Y (the output is the state variable itself)
- Simple if it is basic and Moore with state output

A pair (x, v) is blocking if F(x, v) is empty

## Example: Vending Machine as a Simple System

X = {pay, select, soda, beer}, X0 = {pay} <-- possible state values and initial state
U = {insert_coin, get_soda, get_beer, t} <-- external input

Transition are associated with action labels that indicate the actions that cause the transitions.

- insert_coin, get_soda, get_beer, are user actions (inputs)
- t denotes an activity that is not of interest to the modeler (it represents an internal activity of the vending machine)

Based on the property of interest, a more abstract model can be used (reduce size of system due to property of interest, AKA abstraction/aggregation):

- X = {pay, select, drink}, X0 = {pay}
- U = {insert_coin, get_drink, t}

## Example: Turnstile

A turnstile has two states: locked and unlocked.

- In locked state, pushing on the arm doesn't change the state. Putting a coin in shifts the state from locked to unlocked.

- In unlocked state, putting more coins in doesn't change the state. A customer pushing through shifts the state back to locked.

X = {1: locked, 2: unlocked}
X0 = {1}
U = {coin, push}

F(1, push) = {1}, F(1, coin) = {2}, F(2, coin) = {2}, F(2, push) = {1}
Y = {locked, unlocked}
H(1, push) = {locked}, H(1, coin) = {locked}
H(2, push) = {unlocked}, H(2, coin) = {unlocked}

(push, locked) and (coin, unlocked) create a self-loop (no change), whereas (coin, locked) and (push, unlocked) cause a state change