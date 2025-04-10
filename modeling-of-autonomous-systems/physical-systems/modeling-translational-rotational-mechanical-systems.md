# Modeling Translational Mechanical Systems

Newton's Law: The summation of the force applied to a mass is equal to the mass * acceleration (mass * second derivative of displacement with respect to time).

Summation(i) Fi(t) = ma(t) = mx(t)

F = force
M = mass
a = acceleration
x = displacement
K = spring constant
B = frictional coefficient
v = velocity

F = M * a; M * second derivative of x <-- force applied to mass; opposed by opposing force of mass
F = K * x <-- force applied to spring; opposed by elasticity
F = B * v; B * first derivative of x <-- force applied to damper; opposed by friction

# Rotational Mechanical Systems

T = torque
J = moment of inertia (similar to mass)
a = angular acceleration (second derivative of theta)
theta = angular displacement
K = torsional spring constant
B = rotational friction coefficient
w = angular velocity

T = J * a; J * second derivative of theta <-- force applied by torque; opposed by torque
T = K theta <-- force applied to torsional spring; opposed by elasticity
T = B * w; B * first derivative of theta <-- force applied to damper; opposed by rotational friction

Generally, we can assign new variables to displacement and velocity and write second-order differential equations as a system of first order differential equations