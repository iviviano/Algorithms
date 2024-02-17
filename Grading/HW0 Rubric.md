# HW 0 Rubric

[Solutions](https://github.com/oberlin-cs275/24sp-grading-solutions/tree/main/hw0)

There are six problems in total - as this is the first assignment, the problems 
themselves will likely take students longer to complete. There is also a Github setup component. 

For each problem, the students are supposed to write tests. 

## Overall Advice 

Run the supplied `grading.rkt` file (put it in the same directory as the student's `hw0.rkt`).
Use the point allocations below to give credit. 

In all cases, please look at the student's implementation! If you see problems with the code, write a
comment about how they can improve their code. This is *especially important to do and do 
kindly* at the beginning so students learn good habits. I would give specific kudos for folks who 
commented their code and wrote particularly thoughtful tests. These are two behaviors I'd like to encourage. 

For this first assignment, I just want them to get practice with Racket. They are allowed 
and encouraged to use built-in methods such as `remove` and `member.` Students might have 
used `append` or `index` and that's OK for this week -
a comment encouraging a simpler, more "Racket-like" solution would be great.

## Specific Grading 

Everyone should get the Github Success points, unless you notice something totally out of the ordinary! Check 
with me before deducting points here. 

A reminder to grade the tests and implementations separately: someone can get full credit on the tests for 
just submitting `tests.rkt` and no implementation. 

### Problem 1 

Here students are expected to write tests _only_ based on a provided implementation.

I expect them to write at minimum three additional tests:

+ gain 5 for empty list 
+ gain 3 for the singleton list (any type)
+ gain 5 for testing another type (the example they get is `'(1 2 3)`, so they shoud likely get this for free....)

- deduct 3 for any test which is a duplicate (only apply once)
- deduct 3 for excessive tests (6 or more, but use your judgement/ask)


### Problem 2 

Here students are expected to write the implementation of `arith` and also write 5 tests. 
Give 2 points for each of the following tests:
* even and >= 10
* even and < 10
* odd and >= 10
* odd and < 10
* any test with zero (in addition to the above)

All the tests together are worth 10 points. Provide 5 points for the implementation, based 
on the following: 

- If all grading tests pass, give the full 5 points.
- If only one or two tests fail, give 4 points.
- If more than two tests fail, give 2 points.
- If the problem was not attempted at all, give 0 points.

### Problems 3 through 6

For each problem, the implementation is worth 4 points and the tests are worth 4 points.

For the implementation, 
- If all grading tests pass, give the full 4 points.
- If only one or two tests fail, give 3 points.
- If more than two tests fail, give 2 points.
- If the problem was not attempted at all, give 0 points.

In all cases, please look at their implementation! If you see problems with the code, write a
comment about how they can improve their code.

If they **ignored the "do not just `not` on `all-atoms?` advice**, give them 1/4 points for their implementation.
They are allowed to assume that the input to `not-all-atoms?` is a list. 

For the tests, give
- 2 points for tests where the function returns `#t`; and
- 2 points for tests where it returns `#f`.


## Points

```
Github Success: /40
Problem  1: /13
Problem  2: /15
Problem  3: /8
Problem  4: /8
Problem  5: /8
Problem  6: /8
TOTAL: /100
```

## Providing Students with Feedback

Please provide them the itemized list of the their scores and provide a comment when they 
lose points. I really appreciate thoughtful comments that encourage students rather than simply
point out the mistakes they made.