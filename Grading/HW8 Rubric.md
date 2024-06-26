# HW 8 Rubric

Solutions are the same for all three assignments - see the same folder.

There are three parts in total. The students are not required to implement this
exactly as I suggest, but should have the right outcomes.

For each part, they are expected to write tests in both `parse-test.rkt` and
`interp-test.rkt`. The tests in `test-parse.rkt` should test that input in the
form introduced by that version of MiniScheme can be parsed into a data
structure they create successfully. The tests in `interp-test.rkt` should test
that a parse tree can be evaluated correctly in an environment. Students may
use `parse` to construct the parse trees in `interp-test.rkt`.

To test the `parse` function, you can run `parse.rkt` in DrRacket. To test the
`eval-exp` function, you can run `interp.rkt`. You can also run
`minischeme.rkt` to test evaluating MiniScheme expressions.

**Make sure you read through their code and tests and give comments.**

## Grading MiniScheme F (30 points)

Test that running `(parse '(lambda (x y) (+ x y)))` produces some form of a
lambda expression. E.g.,
```scheme
(lambda-exp (x y)
            (app-exp (var-exp '+)
                     (list (var-exp 'x)
                           (var-exp 'y))))
```
5 points.

Test that running `(eval-exp (parse '(lambda (x y) (+ x y))) init-env)` returns a
closure object containing the list of parameters, an expression body, and the
`init-env`. 5 points.

Test that running these expressions produces the correct results.
```scheme
MS> ((lambda (x) x) 1) 
1 
MS> ((lambda (x y) (* x y)) 2 4) 
8 
MS> (let ((sqr (lambda (x) (* x x)))) (sqr 64)) 
4096 
MS> (let ((sqr (lambda (x) (* x x)))) (let ((cube (lambda (x) (* x (sqr x))))) (cube 3)))
27
MS> (let ((f (lambda (x) (lambda (y) (+ x y))))) ((f 3) 5))
8
```
10 points.

Give 5 points if they have at least one test for parsing a `lambda`.

Give 2 points if they have at least one test evaluating a `lambda-exp` (or
equivalent) to a closure.

Give 3 points if they have at least one test for applying a closure to a
value.

The last two tests could be combined into a single test. E.g., testing
`((lambda (x) x) 1)`.

## Grading MiniScheme G (40 points)
Test that running `(parse '(begin 1 2 3))` produces some form of a
begin expression. E.g.,
```scheme
(begin-exp (list (lit-exp 1) (lit-exp 2) (lit-exp 3)))
```
5 points.

Test that running `(parse '(set! x (+ 1 2)))` produces some form of `set-exp`
(or `assign-exp`). E.g.,
```scheme
(set-exp 'x (app-exp (var-exp '+) (list (lit-exp 1) (lit-exp 2))))
```
5 points.

Test that running `(eval-exp (parse '(begin 1 2 3)) empty-env)` returns 3. 5
points.

Test that running 
```scheme
(eval-exp (parse '(let ((x 0)) (begin (set! x (add1 x)) (add1 x)))) init-env)
```
returns 2. 5 points.

Give 5 points if they heave at least one test for parsing a `begin`.

Give 5 points if they heave at least one test for parsing a `set!`.

Give 5 points if they heave at least one test for evaluating a `begin`.

Give 5 points if they heave at least one test for evaluating a `set!`.

## Grading MiniScheme H (30 points)
Test that parsing a `letrec` gives a `let-exp`, **_not_ any sort of
`letrec-exp`**. For example,
```scheme
(parse '(letrec ([fac (lambda (x) (if (eqv? x 0) 1 (* x (fac (sub1 x)))))]) (fac 4)))
```
should return something like
```scheme
(let-exp
 '(fac)
 (list (lit-exp 0))
 (let-exp
  '(g114137)
  (list (lambda-exp
          '(x)
          (ite-exp
           (app-exp (var-exp 'eqv?)
                    (list (var-exp 'x) (lit-exp 0)))
           (lit-exp 1)
           (app-exp (var-exp '*)
                    (list (var-exp 'x)
                          (app-exp (var-exp 'fac)
                                   (list (app-exp (var-exp 'sub1)
                                         (list (var-exp 'x))))))))))
  (begin-exp (list (set-exp 'fac (var-exp 'g114137))
                   (app-exp (var-exp 'fac) (list (lit-exp 4)))))))
```
Notice that this involves an outer `let-exp` expression, an inner `let-exp`,
and inside that, a `begin-exp` and a `set-exp`. 10 points.

**Reminder**: `'g114137` above is a `gensym`, so no student will have this *exact* output, but they should have something that starts with `g` as their output.

Test that the following examples work.
```scheme
MS> (letrec ([fac (lambda (x) (if (eqv? x 0) 1 (* x (fac (sub1 x)))))]) (fac 4))
        24
MS> (letrec ([fac (lambda (x) (if (eqv? x 0) 1 (* x (fac (sub1 x)))))]) (fac 10))
        3628800
MS> (letrec ([even? (lambda (n) (if (eqv? 0 n) True (odd? (sub1 n))))]  
             [odd? (lambda (n) (if (eqv? 0 n) False (even? (sub1 n))))] )
   (even? 5))
False
```
2 points each for the first two, 6 points for the third.

Give 5 points if they have at least one test for parsing a `letrec`. This is
almost certainly going to have to take the form of testing that it's producing
a `let` since the symbols produced by `gensym` are going to differ each time.

Give 5 points if they have at least one test for evaluating a `letrec` with a
recursive function.

## Points

```
MiniScheme F:       /30
MiniScheme G:       /40
MiniScheme H:       /30
TOTAL:              /100
```