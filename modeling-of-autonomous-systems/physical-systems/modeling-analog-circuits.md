# Modeling Analog Circuits

Electric laws:

V = voltage
i = current
q = accumulated charge
L = inductance coefficient
R = resistor coefficient
c = capacitor coefficient

- Voltage across an inductance: V(t) = Li*(t) = Lq**(t)
- Voltage across a resistor: V(t) = Ri(t) = Rq*(t)
- Voltage across a capacitor: V(t) = 1/c integral of current with respect to time, which is accumulated charge itself (1/c * q(t))

Summation of voltages in a loop (V(t)) = 0

## Mechanical vs Electrical

- Force (F) - Voltage (V)
- Mass (M) - Inductor (L) resists acceleration/change in current
- Damper (b) - Resistor (R) resists velocity/current
- Spring (k) - Capacitor (C) stores energy in displacement/charge

Current(i): flow of electric charge over time. Derivative of charge (q)

Inductor(L) -> first derivative of current; analagous to mass

Resistor: Voltage directly proportional to current -> V(t) = R * i(t) where R = resistor; analagous to damper

Capacitor: Voltage directly proportional to accumulated charge (integral of current); analagous to spring
