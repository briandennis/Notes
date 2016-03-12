#Overarching Lessons from Algos

## Divide and Conquer

Splits the problem up, recursively solves it for each part and then merges them together to get the total solution.

- Often useful for reducing ugly, but still polynomial problems to a more manageable time complexity
- Rarely can be used to drop something from exponential to polynomial

### Examples

- Merge-sort

## Greedy

Do the best possible option at every point and end up with the optimal result.

- Awesome because it is trivial to write
- Not awesome because it usually does not work, it isn't broadly applicable to a wide variety of problem classes

### Examples

- Dijkstra's
- Minimum spanning tree (Prim's, Krustal's, etc.)

## Dynamic Programming

>Careful brute force.

Use recursion like structure where you remember the answer to subproblems to reduce complexity.

Has the stupid name of dynamic programming because a guy was trying to hide from his boss the fact he was doing math.

- Broadly applicable and should be one of the first techniques to use when you know nothing else
- Can often reduce from exponential to polynomial by looking up answers to subproblems rather than repeating them every time
- Can usually use recursion + memoization or 'bottom-up', an iterative method where you precompute the subproblems and store in a table

### Basic Steps

1. Subproblems
2. Guess
3. recurrence/Bellman Equation
4. Memoize, Table
5. Solve original problem

### Strategies

- For strings and sequences use suffixes/prefixes O(n) or substrings O(n^2)

### Examples

- Fibonacci
- Knapsack
- Weighted interval scheduling
- Bellman/Ford for networks
