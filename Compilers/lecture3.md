# Lecture 3

## NFAs, Formally

Q = finite set of states

sigma =the alphabet

small sigma = transition function

q = start states

F = final states

## NFA and DFA are Equivalent

Two automata M and M' are equivalent iff L(M) = L(M')

### Epsilon CLosure

eclose(s) = set of all states reachable from s using zero or more epsilon transitions

Can always construct a DFA by expanding all possibilities of an NFA

Process called **determinization**

## Regular Languages and Regular Expressions

A **regular language** is any language recognized by an FSM

A **regular expression** is a ppatern that defines a regular language

Each token in a programming language can be defined by a regular language
