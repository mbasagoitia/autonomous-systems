# Regular Expressions

Regular expressions (used to represent a language) over a finite set (alphabet) W are represented by symbols.

Some of these include:

- 0 - empty language
- e (epsilon) - empty string (singleton consisting of the empty word)
- w - symbol inside the set W
- . - concatenation
- + - union
- * Kleene star (finite repetition)

The language L(a) of a regular expression a over W is subset equal to W*

# Omega Regular Expressions

Addition of omega operator (w), represented as a^w, to represent infinite repetition

L^w is subset equal W^w if epsilon is not in L because epsilon^w is epsilon itself

Examples:

Let W = {a, b}

- a should never occur: b^w
- a should occur exactly once: b* a b^w
- at some point, b should occur: (a + b)* b (a + b)^w
- at some point, b should occur forever afterwards: (a + b)* b^w
- a should occur only finitely many times: (a + b)* b^w