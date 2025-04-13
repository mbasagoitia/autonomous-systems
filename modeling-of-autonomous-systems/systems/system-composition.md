# System Composition

How can we interconnect systems and build new systems?

Let Si = (Xi, Xi,0, Ui, Vi, Yi, Fi, Hi), i = {1, 2} be two systems

## Parallel Composition

**Parallel composition** of S1 and S2 is defined by S1 || S2 = (X12, X12,0, U12, V12, Y12, F12, H12) where:

- || means parallel composition
- X12 = X1 * X2
- X12,0 = X1,0 * X2,0
- V12 = V1 * V2
- U12 = U1 * U2
- Y12 = Y1 * Y2

- F12(x, v) = F1(x1, v1) * F2(x2, v2)
- H12(x, u) = H1(x1, u1) * H2(x2, u2)