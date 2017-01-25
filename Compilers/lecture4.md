# Lecture 4

## Regular Expression to NFA

1. logically map regex operators to DFAs.
2. chain them together to form one large state machine that recognizes the language.

## Using FSMs for tokenization

FSMs only check membership

Scanner needs more. It needs to recognize a stream of many different tokens. Successively finds the *next* token by a "maximal munch".
