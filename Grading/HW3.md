# HW 3 Rubric

There are nine problems in total, each is with 10 points. They earn a base 10 points for completing the assignment - they should get this if they attempt to use `map` and/or `apply` at least once in the assignment. 

For each problem, the students are supposed to write tests. The tests are worth 5 points and the function itself is worth 5 points.

## Notes / FAQs 

- For Problem 1, it is OK to assume that the inputs to `firsts` and `rests` were lists that are non-empty and of equal length 
- `flatten` was allowed to be used in subsequent problems 
- `(transpose '())` should return `'()`

- Don't get too "in the weeds" for the empty cases (such as `'('() '())` versus `'() '()`) for matrix operations. Whatever solution leads to the most "elegant" 
higher order solution is cool with me.

## Grading the implementation

Run the supplied `grading.rkt` file (put it in the same directory as `hw3.rkt`).

- If all grading tests pass, give the full 5 points.
- If only one or two tests fail, give 4 points.
- If more than two tests fail, give 3 points.
- If the problem was not attempted at all, give 0 points.

In all cases, look at their implementation. If you see problems with the code, write a comment about how they can improve their code.

- *IMPORTANT*: For every problem other than #7 (flatten) can only get a max of 4/5 on the implementation if there is no use of a higher order function.
So even if it passes all tests, but is fully recursive, 4/5 on implementation.

## Grading the tests
Give the points listed below for the corresponding problem.

Unless otherwise mentioned, they need at least three tests to get full points. If they only have one test, give 3 points. Edge cases are challenging to describe / implement for this homework, so be more lax with the quality benchmark for tests.

For problem 1, if they have tests for both `firsts` and `rests`, give 5 points, if they only have test for one, then give 3 points. No points for no tests.


## Points
```
Homework Attempted:     /10
Problem  1:             /10
Problem  2:             /10
Problem  3:             /10
Problem  4:             /10
Problem  5:             /10
Problem  6:             /10
Problem  7:             /10
Problem  8:             /10
Problem  9:             /10
TOTAL:                  /100
```