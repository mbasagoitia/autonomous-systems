# Introduction

Model-based design paradigm

- Specification/requirement: what the system is supposed to do
- Modeling: Description of what the system actually does
- Design: Structured creation of artifacts to modify the system behavior
- Verification: certify that the system does what it is supposed to do
- Refinement: if the verification step fails, go back and refine the design

How to assess system correctness:

- Formal methods: mathematical-based techniques for the specification, development, and verification of software and hardware systems
- Testing: simulation/execution based inspection of the system correctness

Formal verification and testing are two different things.

## Formal Verification vs Testing

Testing:

- Cannot guarantee absence of errors
- Requires less mathematical skills
- Is computationally cheap

Drawbacks of testing: cannot simulate uncountably many initial conditions, and cannot simulate the system for infinite time

Formal verification: 

- Provides a mathematical proof of the absence of errors relative to the specifications and the model
- Uses formal specifications whose formulations require highly-qualified engineers
- Is computationally expensive and often fails even in a naive application for real-world systems

Formal verification can prove, for example, that a system is asymptotically stable without any testing by searching for a function v with these two properties:

- V(x) = 0 iff x = 0
- For all x != 0, V(f(x)) - V(x) < 0

## Formal Synthesis

Synthesis is the process of generating the description of a system in terms of related lower-level components from some high-level description of the expected behavior. Produces some provably-correct artifact/controller.

Formal synthesis is a methodology that mechanizes the design step and integrates the verification step in one unifying procedure; "describe and synthesize" or "specify-synthesize-refine" instead of "specify-design-verify-refine" (above). Also known as "correct-by-construction" synthesis.

Formal synthesis can be computationally much more complex than formal verification.

x(t + 1) = Ax(t) + Bu(t) where x represents the state at a given time, current and next, and u represents input/actuation, and A and B are matrices

For example, for the system above, we can design a controller u(t) = Kx(t) which guarantees asymptotic stability