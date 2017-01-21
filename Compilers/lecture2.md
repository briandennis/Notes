# Lecture 2

**front end** understand source code S

**IR** intermediate representation

**back end** map IR to T

## The Scanner

Translates sequence of chars into a sequence of tokens (ignoring whitespace)

Each time scanner is called it should:

- find longest prefix (**lexeme**) of the remaining input corresponding to a token

- return that token

Scanner generator

Inputs:

- one regular expression for each token
- one regular expression for each item to ignore

Output: scanner program

How does a scanner generator work? Finite state machines

## Finite State machines

Input: string
Output: accept or reject

### FSMs formally

- Finite set of states
- the alphabet (characters)
- transition function
- start states
- end states

There are deterministic finite automata (DFA) and nondeterministic finite automata (NFA)

### NFA

- Nondeterministic
- Epsilon transitions - move to another state without input
- If there exists a sequence of transitions leading to a final state, it is accepted
- Theoretical, not really constructed

Why NFA?

Simpler and more intuitive than DFA
  
