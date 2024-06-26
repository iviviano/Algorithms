# HW 6 Grading Guide

There are three parts in total. The students are not required to implement this
exactly as I suggest in the writeup, but they do need to follow the overall flow.

For instance, if they call their data type for variables `variable-exp` instead of `var-exp`, this is totally fine. 

For each part, they are expected to write tests in both `parse-test.rkt` and
`interp-test.rkt`. The tests in `parse.rkt` should test that input in the form
introduced by that version of MiniScheme can be parsed into a data structure
they create successfully. The tests in `interp-test.rkt` should test that a
parse tree can be evaluated correctly in an environment. Students may use
`parse` to construct the parse trees in `interp-test.rkt` (although it's
better if they do not).

To test the `parse` function, you can run `parse.rkt` in DrRacket. To test the
`eval-exp` function, you can run `interp.rkt`. You can also run
`minischeme.rkt` to test evaluating MiniScheme expressions.

Make sure you read through their code and tests and give comments.

## Grading MiniScheme C (30 points)

Test that running `(parse '(foo 1 x y))` produces some form of an application
expression. E.g.,
```scheme
(app-exp (var-exp 'foo)
         (list (lit-exp 1)
               (var-exp 'x)
               (var-exp 'y)))
```
8 points (2 for the procedure, 2 for parsing each argument, 2 for the parsed arguments being in a list, 2 for the new data type.)

Test that the primitive procedures `+`, `-`, `*`, `/`, `add1`, `sub1`,
`negate`, `list`, `cons`, `car`, and `cdr` work correctly. The easiest way to
do this is to run `minischeme.rkt` and enter the code in the box. For example,
```scheme
(cdr (list 2 7 5))
```
should return `'(7 5)`. Some students struggled not understanding that we only allow `list` to construct lists in MiniScheme, not quoted lists. Be on the lookout for that.

Test that `null` is bound to the empty list. Give one
point for each primitive procedure that works, so 11 for the primitive procedures and 1 for `null`. 12 points.

Give 4 points if they have at least _two_ tests for parsing a procedure
application.

Give 6 points if they have at least _two_ tests for evaluating procedures, at least one primitive. 

## Grading MiniScheme D (30 points)

Test that running `(parse '(if x (add1 y) z))` produces something like
```scheme
(ite-exp (var-exp 'x)
         (app-exp (var-exp 'add1) (list (var-exp 'y)))
         (var-exp 'z))
```
3 points.

Test that `True` evaluates to `True` and `False` evaluates to `False`. 3
points.

Test that `eqv?`, `lt?`, `gt?`, `leq?`, and `geq?` work correctly with numbers
and return the expected results. E.g., `(leq? x y)` returns `True` (because
`x` should be bound to 23 and `y` should be bound to 42 from MiniScheme A).
Each of these should return `True` or `False`, not `#t` or `#f`. 5 points.

Test that `null?`, `list?`, and `number?` behave correctly, returning `True`
or `False`. 3 points.

Test that evaluting `(if (lt? 1 2) (add1 x) (sub1 x))` returns 24. 2 points.

Test that evaluating `(if (null? 4) (add1 x) (sub1 x))` returns 22. 2 points.

Test that evaluating `(if 0 x y)` returns 42. 2 points.

Test that invalid if expressions raise an error. E.g., `(if x y)` or `(if x 1
2 3)` 2 points if both raise an error, 0 points if at least one does not.

Give 4 points if they have at least _two_ parse tests for an if expression.

Give 2 points if they have at least one evaluation test for an if expression
where the condition is (or evaluates to) `True`.

Give 2 points if they have at least one evaluation test for an if expression
where the condition is (or evaluates to) `False`.

## Grading MiniScheme E (30 points)

Test that running `(parse '(let ([x 1] [y (add1 z)]) y))` produces something
like
```scheme
(let-exp '(x y)
         (list (lit-exp 1) (app-exp (var-exp 'add1) ((var-exp 'z))))
         (var-exp 'y))
```
That is, it has a list of symbols, a list of expressions, and a body. Note that they are expected _not_ to parse the symbols list (we went over this in class). 6 points (roughly 2 points per element).

Test that invalid let expressions raise an error. (Just test constructing a
let with too many or too few parameters. Don't test what happens if the
binding symbols are not actually symbols). 2 points.

Test that evaluating a basic let expression works. E.g.,
```scheme
(let ([x 2])
  (- 10 x))
```
returns 8. 5 points.

Test that evaluating a let expression works correctly when bound to a procedure. E.g.,
```scheme
(let ([+ -])
  (+ 5 3))
```
returns 2. 5 points.

Give 5 points if there is at least one parse test for a let expression.

Give 4 points if there is at least one evaluation test for a let expression.

Give 3 point if there is at least one evaluation test for a let expression
that shadows a binding. This can either shadow something in the `init-env` or
a nested `let` where the inner `let` has a binding that shadows a binding in
the outer `let`.

## Rubric 
```
Baseline/Fixes from HW5:    /10
Part C:                     /30
Part D:                     /30
Part E:                     /30
Total:                      /100
```