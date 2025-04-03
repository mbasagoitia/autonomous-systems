# Modeling Sequential Circuits as Systems

A sequential circuit produces an output based on input and register variables. Sequential circuits include memory elements that are capable of storing binary information.

- u: input
- r: register
- y: output

State contains evaluation of input value and register variable; used to determine next value of the register.

X is the set of evaluations of input variable u and register variable r; {(0, 0), (0, 1), (1, 0), (1, 1)}. Initial states are those with r = 0.

Output function: H((u hat, r), u) = {NOT(u hat XOR r)}

Where u hat is previous input variable (stored in memory) and u is the current input variable

Transition function: F((u hat, r), u) = {(u, u hat OR r)}