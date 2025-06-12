# Controller Refinement

How can we leverage feedback refinement relation and refine a controller from an abstract system to a concrete system?

Consider two systems, S1 (concrete) and S2 (abstraction) which share the same input set, and a controller C that is feedback composable with S2.

If C is nonblocking, S2 is also nonblocking

Assume that Q is strict feedback refinement relation from S1 to S2

Theorem: 

Let Q be a feedback refinement relation from S1 to S2 and C. If C is feedback composable with S2 and C is non-blocking implies S2 is non-blocking, then the following statements are true:

1. C is feedback composable with the series interconnection of Q and S1
2. The behavior of the feedback interconnection of C and S1 is subset equal to the behavior of the feedback interconnection of Q and S2. For any input state sequence which belongs to the behavior of S1, Q, and C, there exists an input state sequence of S2 and C such that the state trajectory (x1, x2) at any given time are in the relation.

This means that the closed loop of S1, Q, and C also satisfies the property of interest.

Q can be used as a quantizer after the output of S1; state information of S1 goes into Q and the output of Q goes to the controller C.

Serial interconnection of Q and C represent C', the refined controller