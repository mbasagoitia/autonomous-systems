# Safety and Co-Safety Linear Properties

Linear properties can be divided into two categories: safety and co-safety

Let P be a property over alphabet W where P is subset equal to W^omega

We can say P is a **safety property** if for any infinite word not inside P, that word should have a finite prefix such that if you concatenate that finite prefix with any other infinite word, the new word is not inside P. That prefix is called a bad prefix.

The set of all bad prefixes is denoted by bad(P)

We can say P is a **co-safety property** if its complement is a safety property; the complement is W^omega excluding P.

For any infinite word inside P, there should exist a finite prefix such that if you concatenate it with any other infinite word, this new word is also inside P. The finite prefix is called a good prefix. 

The set of all good prefixes is denoted by good(P)