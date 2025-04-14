# System Composition

How can we interconnect systems and build new systems?

Let Si = (Xi, Xi,0, Ui, Vi, Yi, Fi, Hi), i = {1, 2} be two systems

## Parallel Composition

Parallel composition of S1 and S2 is defined by S1 || S2 = (X12, X12,0, U12, V12, Y12, F12, H12) where:

- || means parallel composition
- X12 = X1 * X2
- X12,0 = X1,0 * X2,0
- V12 = V1 * V2
- U12 = U1 * U2
- Y12 = Y1 * Y2

- F12(x, v) = F1(x1, v1) * F2(x2, v2)
- H12(x, u) = H1(x1, u1) * H2(x2, u2)

## Serial Composition

Used in quantizers, static systems, and sample-and-hold systems

Serial composition of S1 and S2 is defined by S2 ∘ S1 = (X12, X12,0, U1, V12, Y2, F12, H12) where:

S1 is serial composable with S2 if Y1 is part of U2 (output set of system 1 is a subset of the external input set of system 2)

- ∘ means serial composition and S1 feeds into S2
- X12 = X1 * X2
- X12,0 = X1,0 * X2,0
- V12 = V1 * V2

- F12(x, v) = F1(x1, v1) * F2(x2, v2)
- H12(x, u1) = {(y2, (v1, v2))}
    - Output Function:
        For a given state and external input, outputs are determined by combining:
        Output from S₁ and its internal input.
        Feeding S1's output into S2 and calculating its output and internal input.
        Requires the existence of an intermediate output from S1 that serves as valid input to S2.

### Example: System and Static Quantizer

A static system Q (like a quantizer) follows a simple system S.

- Q maps real-valued output from S into discrete (quantized) values.
- Output of S is quantized by Q.
- Resulting system (Q ∘ S) is a basic system, no longer simple, because the output set has changed.

You can also place the quantizer before the system:
- Q's output becomes the input to system S.
- This is still a valid serial composition as long as Q's output set is a part of S’s external input set.
- Used to model quantized input control instead of quantized measurements.

## Feedback Composition

S1 is feedback composable with S2 if the output of system 1 can be an external input of system 2 AND vice versa; and S2 is Moore to prevent circular dependencies (recall that Moore means that the output is not explicitly a function of external input)

Feedback composition of S1 and S2 is defined by S2 X S1 = (X12, X12,0, {0}, V12, Y2, F12, H12) where:

- X means feedback composition
- X12 = X1 * X2
- X12,0 = X1,0 * X2,0
- V12 = V1 * V2
- The external input set U becomes singleton ({0})

- F12(x, v) = F1(x1, v1) * F2(x2, v2)
- H12(x) = {(y1, y2), (v1, v2)}

- y2 -> H1 -> y1 -> H2 -> y2
- y2 doesn't get explicitly affected by y1

Application: S1 is the controller, S2 is the plant, S1 X S2 is the closed loop