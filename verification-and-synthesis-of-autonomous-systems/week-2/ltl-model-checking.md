# LTL Model Checking

How can we verify that a finite system S satisfies a given LTL formula?

Given a simple system S over a set of atomic propositions AP and an LTL formula varphi over AP, does S satisfies varphi hold?

Basic idea: try to refute that S satisfies varphi by searching for a state path pi in S such that pi != varphi

- Construct an NBA A for Words(not varphi) <-- "bad behaviors"
- Search a path pi in S with L(pi) subset Words(not varphi) = Lw(A)

Construct the product system S product A and search a path in the product that meets the acceptance condition of A