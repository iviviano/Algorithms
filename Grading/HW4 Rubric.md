# HW 4 Rubric

There are nine problems in total. They earn a base 9 points for completing the assignment - they should get this if they use `fold` consistently across Part 1 and attempt to use a `map` once and a `fold` at least once in Part 2.

For each problem, the students are supposed to write tests. The tests are worth 5 or 6 points and the function itself is worth 5 points.

### Be Aware for This Week 

- They _must_ use `fold`s on Problems 1 thorugh 3 
- The testing requirements for Problems 4 through 9 are specific (see below)
- They were allowed to choose *either* a pre-order or post-order traversal to implement. Please check that they implemented the right one.


## Grading the implementation

Run the supplied `grading.rkt` file (put it in the same directory as the student's `hw4.rkt`).

Each implementation is worth 5 points. For Part 1 (Problems 1 - 3) they were expected to use `foldl` and `foldr` to receive full credit. Remove 2 points from their base score each time their Part 1 implementations do **not** use a `fold`. Otherwise, use the following rubric:

- If all grading tests pass, give the full 5 points.
- If only one or two tests fail, give 4 points.
- If more than two tests fail, give 2 points.
- If the problem was not attempted at all, give 0 points.

For Part 2 (tree manipulations, Problems 4 through 9), they were expected to use `apply`, `map`, or `fold`. Deduct one point from a working implementation if there is no use of higher-order functions.

For Problem 9, check that they implement the right traversal (i.e. not just that it works, but that the procedure name matches the output). Deduct 2 points if it does not.

In all cases, look at their implementation. If you see problems with the code, write a comment about how they can improve their code.

## Grading the tests
Give the points listed below for the corresponding problem.

For Part 1: they need at least two tests to get full points. If they only have one test, give 2 points. Don't put a lot of effort into evaluating the quality of tests here. Tests are worth 5 points total.

For Part 2 (problems 4 through 9), they were expected to write tests as follows:

- Write  at least two meaningful tests for each procedure
-  Assume that all trees are numerical trees (i.e. trees which contain numbers as values). This is true of all the provided trees as well.
- At least one test per problem should reference **a test tree of their own development** that is defined in tests.rkt

If they only have 1 test, give them 2 points. If they have two tests, but no tree of their own creation, then give them 4/5 points. They can only get 5/5 points for tests with 2 or more tests _and_ a unique tree. The tree *can be the same* for all problems in Part 2, but should be unique to the student (not just a tree whose value changed from a provided test tree). You should deduct 1 point off for each problem that does not have a bespoke test.

The exception to the point rule is problem 6: for problem 6, the tests are worth 6 points for a total of 10 points and having only a single test is worth 3 points. Similarly, only a 5/6 can be achieved without a unique tree.


## Points
```
Homework Base:      /9

Part 1
Problem  1:         /10
Problem  2:         /10
Problem  3:         /10


Part 2
Problem  4:         /10
Problem  5:         /10
Problem  6:         /11
Problem  7:         /10
Problem  8:         /10
Problem  9:         /10
TOTAL:              /100
```