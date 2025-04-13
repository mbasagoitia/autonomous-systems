# Systems' Solutions and Behaviors

Note on interval syntax:

- [a, b] means real numbers between a and b including a and b
- ]a; b[ means integers between a and b excluding a and b

Given a system S (u, v, x, y), 

(u(0), v(0), x(0), y(0)) ... (u(T-1), v(T-1), x(T-1), y(T-1)) is a **solution** over the interval [0; T] if:

- x(0) is in the initial state set (X0)
- x(t+1) is in F(x(t), v(t)) and this holds for all t [0; T-1[ (satisfies conditions of transition map)
- (y(t), v(t)) is inside of H(x(t), u(t)) and this holds for all t [0; T[ (satisfies conditions of output map)

The **behavior** of a system, denoted B(S), is only concerned with external input (u) and output (y) of the system. We do not consider internal variables.

Given a system (u, y), the sequence of pairs (u(0), y(0)) ... (u(T-1), y(T-1)) belongs to the behavior of the system if:

- There exists internal input variable v, x, T such that (u, v, x, y) is a solution of S on [0; T[
    - T < infinity imples that (x(T-1), v(T-1)) is blocking. This is how we allow only finite sequences to be a part of the system. Otherwise, the elements of the behaviors of the system are all infinite sequences of (u, y).

If S is simple, (u, v, x, y) reduces to (u, x) which means that solutions and behaviors are described in the same way. Each finite solution (u, x) that ends with a blocking pair is also an element of the behavior B(S). Each infinite solution (u, x) is in the behavior B(S) as well.

- Solutions can be finite or infinite
- Behaviors are infinite and are only allowed to be finite if we end up at a blocking pair