>[!def]
>A [[Dynamic Programming Paradigm]] solution to the [[Shortest Paths Problem]]. The idea is to impose a measure of progress to parameterize the subproblems.

We will measure progress by the number of edges in the path.

1. Compute all possible shortest paths with $≤$ $1$ edge.
2. Do the same with $≤2$ edges
3. ...
4. If no negative [[Cycle]], can stop after computing all shortest paths with $≤n-1$ edges