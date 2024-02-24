# HW 1 Rubric

There are eight problems in total on this homework. For each problem, the students are supposed to 
write at least 3 tests in `tests.rkt`.  

## Grading the implementation

Run the supplied `grading.rkt` file (put it in the same directory as `hw1.rkt`). All problems 
get 5 points total for their implementation, other than problem 5. 

- If all grading tests pass, give the full 5 points.
- If only one or two tests fail, give 4 points.
- If more than two tests fail, give 2 points.
- If the problem was not attempted at all, give 0 points.

**For Problem 5 only**, give 5 additional points (10 total for implementation) for a working 
`delete-second-x` (all or nothing).

In all cases, please look at their implementation! If you see problems with the code, write a
comment about how they can improve their code.

They are allowed and encouraged to use built-in methods such as `remove` and `member.` 
Students might have used `append` or `index` and that's
OK for this week - a comment encouraging a simpler, more "Racket-like" solution would be great.

You can ignore the note about `equal?` for Problem 3 - it's okay to use `member` here. The main
concern there was to prevent folks from using `=` or `eq?` instead.

I would give specific kudos for folks who commented their code and wrote particularly 
thoughtful tests. These are two behaviors I'd like to encourage. 

_Higher order function use?_ They were specifically asked to not use the, so deduct *2 points* 
from a working implementation if they use higher order. 

## Grading the tests
Give the points listed below for the corresponding problem - all tests are worth 5 points each. 

For problems 1 & 2, give
- 2 points for tests where the function returns `#t`; and
- 2 points for tests where it returns `#f`.
- 1 point for any third (or more) tests

For problems 3 through 8, give 4 points if they write at least three tests, 3 points
if they write two tests, and 2 points if they write one test. 

Then, for all the tests for each a problem, give 1 point if the tests for that problem cover 
at least 2 important cases, 0 points if they are too generic. 

## Points

```
Assignment Attempted:   /15
Problem  1:             /10
Problem  2:             /10
Problem  3:             /10
Problem  4:             /10
Problem  5:             /15
Problem  6:             /10
Problem  7:             /10
Problem  8:             /10
TOTAL: /100
```