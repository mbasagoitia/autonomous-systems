# Modeling Examples

## Electric Passive Filter

v = voltage
i = current
L = inductance coefficient
C = capacitor coefficient
R = resistor coefficient


- Inductors: v(t) = Li*(t)
    - Laplace domain: V(s) = sLI(s) assuming i(0) = 0
- Capacitors: i(t) = Cv*(t)
    - Laplace domain: I(s) = sCV(s) assuming v(0) = 0
- Resistors: v(t) = Ri(t)
    - Laplace domain: V(s) = RI(s)

To model this electric passive filter, we will work in the Laplace domain to solve differential equations, then go back into time domain.

## Laplace Domain

- Inductor: V(t) = L * dI(t)/dt <-- voltage expressed as a differential equation in relation to current
- Capacitor: I(t) = C * dV(t)/dt <-- current expressed as a differential equation (integral) in relation to voltage

Laplace transform turns time domain equations into algebraic frequency domain equations

L(dI/dt) = s*I(s)

- Inductor: V(s) = L * s * I(s)
- Capacitor: I(s) = s * C * V(s)

Assume initial conditions are 0

# Expressing as a First-Order System

d/dt X(t) ([X1, X2, X3, X4]) = A * X(t) + B * v(t)

Where X(t) represents the state vector, A is a system matrix, and B is the input matrix

# Discretizing the Continuous Time System

We need a way to convert continuous differential equations into a model of a system--we need to sample it.

- Choose a sampling interval
- Assume that within each time step T, the input u(t) stays constant
- Implemented zero-order-hold (ZOH)
- ZOH takes the discrete-time input and holds it constant over each sampling interval
- Sampler converts into a discrete time signal

Now this sample-and-hold system can be described using the simple system model  

State space (X) = vector in n-dimensional space
Input space (U) = m-dimensional vector
Transition function (F(x, u)) = defines how the system transitions from one state to another under a constant input over one sampling period