# HW 2 Rubric

There are eight problems in total on this homework. For each problem, the students are supposed to 
write at least 3 tests in `tests.rkt`.  

## Grading the implementation

Run the supplied `grading.rkt` file (put it in the same directory as
`hw2.rkt`).

- If all grading tests pass, give the full 5 points.
- If only one or two tests fail, give 4 points.
- If more than two tests fail, give 3 points ("code was written" scenario)
- If the problem was not attempted at all, give 0 points.

In all cases, look at their implementation. If you see problems with the code, write a comment about how they can improve their code. A reminder to provide *actionable* and *realistic* feedback.

They've spent time with `map`/`apply` and a little bit of `fold` for this homework. Do not take points off if you see them using higher order functions, but just remind them that having multiple ways to solve any particular problem is important (i.e. if they _can't_ come up with the "normal" solution, that's an issue!)

## Grading the tests
Give the points listed below for the corresponding problem. Each function should have at least three tests to receive full points.

1.
   - 1 point for a test where the first list is empty;
   - 1 point for a test where the second list is empty; and
   - 3 points for additional tests.
2.
   - 1 point for a test where the list is empty;
   - 1 point for a test where the list is not sorted;
   - 3 points for additional tests.
3.
   - 1 point for a test where `sublist` is empty;
   - 1 point for a test where `sublist` is not empty and appears in `biglist`;
   - 1 point for a test where `sublist` is not empty and doesn't appear in
     `biglist`; and
   - 2 points for having at least 3 tests in total (counting the ones above);
4.
   - 1 point for a test where `sublist` is empty;
   - 1 point for a test where `sublist` is not empty and appears in `biglist`;
   - 1 point for a test where `sublist` is not empty and doesn't appear in
     `biglist`; and
   - 2 points for having at least 3 tests in total (counting the ones above);
5.
   - 1 point for a test where `lst` is the empty list (`empty`, `null` or
     `'()`);
   - 1 point for a test of a nonempty list; and
   - 3 points for additional tests.
   
6.
   - Give 5 points if there are at least 3 tests
   - 4 points if there are 2 tests; and
   - 3 points if there's 1 test.
7.
   - 1 point for a test with no matching elements;
   - 1 point for a test with at least one matching element; and
   - 3 points for additional tests.
8.
    - 1 point for a test with no matching elements;
    - 1 point for a test with matching elements; and
    - 3 points for additional tests.

## Rubric

```
Homework Base:      /20
Problem  1:         /10
Problem  2:         /10
Problem  3:         /10
Problem  4:         /10
Problem  5:         /10
Problem  6:         /10
Problem  7:         /10
Problem  8:         /10
TOTAL:              /100
```