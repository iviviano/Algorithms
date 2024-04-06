# HW 5 Rubric 

There are three parts in total below for a total of 100 points.

## Heads Up & FAQ
- Should our environment handle something like the following?
```
(let ([x 1]
         [y 2]
         [z 3]
         [a 4]) ...)
```

Yes! Even though the examples only give you two possible bindings, your env should be robust enough to handle n bindings simultaneously.

- `(define env-lookup  (env '(x y x) '(1 2 3) empty-env))` should return 1

## Grading Parts 1 & 2 (60 points)

I asked them to implement the `env` themselves and I allude hopefully really obviously to the fact they should 
use built-in Racket `structs`. 

- -2 for each argument that is incorrectly named (it should be `syms`, `vals`, and `previous`)
- -1 for no `#:transparent` (and a note to remind them to add it!)

**If they implement `env` *not* with a struct, give them 4 points total and the correct solution in the comments.** 
Strongly suggest they use structs whenever building their own data types.

`env-lookup` is worth 35 points and the tests are worth 15 points.

There are five cases they should handle, both implementation and testing wise. Each case is worth 7 points for implementation and 3 points if they have at least one test per each case - many is great! 

1. Looking up a symbol that's not bound in an environment throws an error (7 points for implementaiton, 3 points for a test)
2.  Looking up a symbol in an empty environment throws an error. (7 points for implementaiton, 3 points for a test)
3. Looking up a symbol that's bound in an environment returns its value (7 points for implementaiton, 3 points for a test)
4. Looking up a symbol that's not bound in an environment but is bound in the
  environment's previous environment returns the correct value (7 points for implementaiton, 3 points for a test)
5. Looking up a symbol that's bound in an environment and also in the
  environment's previous environment returns the value from the current
  environment (7 points for implementaiton, 3 points for a test)

Students are free to implement this as they see fit,  however the writeup tells them to test at least five situations. Any Racket functions (helpers, built-in methods, etc.) are allowed. 

_They do need to properly throw errors for this implementation._

If you see an incorrect solution, *note this* for the students and suggest that they need to fix it ASAP.

# Overview of MiniScheme Grading 

The students are not required to implement this exactly as I suggest in the writeup, but they do need to follow the overall flow.

For instance, if they call their data type for variables `variable-exp` instead of `var-exp`, this is totally fine. 

For each part, they are expected to write tests in both `parse-test.rkt` and
`interp-test.rkt`. The tests in `parse.rkt` should test that input in the form
introduced by that version of MiniScheme can be parsed into a data structure
they create successfully. The tests in `interp-test.rkt` should test that a
parse tree can be evaluated correctly in an environment. Students should get a "thumbs down" comment if they use
`parse` to construct the parse trees in `interp-test.rkt` - vastly preferred to make their own test trees. 

To test the `parse` function, you can run `parse.rkt` in DrRacket. To test the
`eval-exp` function, you can run `interp.rkt`. You can also run
`minischeme.rkt` to test evaluating MiniScheme expressions.

Make sure you read through their code and tests and give comments! **Comments on the setup for parse and eval-exp are particularly useful this week, given that this assignment gets directly built on!**

## Grading MiniScheme A (20 points)

Test that running `(parse 275)` produces something like `(lit-exp 275)`. That is, the result should be a struct (here, `lit-exp`) containing the number. 5
points.

Test that running `(eval-exp (parse 275) empty-env)` returns 275. (If their
`parse` procedure does not work correctly, you can instead try evaluating what
`parse` should return: `(eval-exp (lit-exp 275) empty-env)`. 5 points.

Give 5 points if they have at least one test for parsing a number.

Give 5 points if they have at least one test for evaluating a `lit-exp` (or
equivalent).

## Grading MiniScheme B (20 points)

Test that running `(parse 'x)` produces something like `(var-exp 'x)`. 5 points.

Test that running `(eval-exp (parse 'x) init-env)` returns 23 (or whatever
value they bound `x` to in `init-env`). 5 points.

Give 5 points if they have at least one test for parsing a variable.

Give 3 points if they have at least one test for evaluating a `var-exp` (or equivalent).

Give 2 points if they have at least one test for evaluating a `var-exp` that is *not bound* in an environment. 

Write a nice note if they have a lot of exhaustive testing!  

## Points
```
Part 1:         /10
Part 2:         /50
Part A:         /20
Part B:         /20
TOTAL:          /100
```