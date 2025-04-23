# Basic Concepts of Languages

To define a **language**, we need words or **strings**, which are made up of **symbols** that constitute an **alphabet**.

- Given an alphabet W = {a, b, c}
- Strings over W are "omega" (empty string), "aab", "bac", etc.
- W* denotes the set of all finite strings over W
- W^omega denotes the set of all infintie strings over W
- If x is a string over W, then |x| denotes the length of x, such as |abc| = 3, |omega| = 0

A language is a set of finite or infinite strings. Since languages are sets of strings, new languages may be constructed using operations on sets such as intersection, etc. and these four basic operations:

- union
- concatenation
- Kleene star (*, finite repetition)
- omega operator (w (omega), infinite repetition)

The languages that are obtained by repeatedly applying the first three basic operations on simple languages are called **regular languages**, and by repeatedly applying the four basic operations on these simple languages are called **omega-regular languages**

- Regular expressions are representations of regular languages
- Omega-regular expressions are representations of omega-regular languages

Omega is the identity element of the concatenation operator because any word concatenated with omega is just the word itself.

A prefix can only be a finite-length word. Infinite words cannot be prefixes.