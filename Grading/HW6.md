Alec [alec5](https://github.com/orgs/24sp-oberlin-csci275/teams/alec5)   

Honor Code: yes

Parsing Notes:
- Parsing is where you check for correct syntax structure of the input. This includes verifying that `if` statements having exactly three expressions. When they do not, you should raise a *descriptive* exception. Right now, `parse` does not fail when given a four-plus argument if expression. It fails when given a two-or less argument if expression, since you call `fourth` on the input. But, this error is raised by `fourth`, not `parse`. (**-2 points**)
- You have only one test for parsing an if expression. (**-2 points**)
- When parsing let expressions, **you should not parse the symbols**. Note that in your "interp.rkt" file, you just end up unwrapping the parsed symbols. Since you never need to check their node type, this is unnecessary. (**-2 points**)
- Again, you did not check the syntax of let expression inputs. (**-2 points**)

Interpreting Notes:
- Your primitive procedure `negate` does not work as expected. Note that `negate` in Minischeme returns the opposite of a number. This is different from `negate` in Racket which takes a predicate and returns the logical negation of that predicate. (**-1 points**)
- The empty list input does not work in your implementation of Minischeme. This is because of the way you bound it in your `init-env`. We expect `(eval-exp (parse 'null) init-env)` to return `()`. Think about why parsing `'null` is very different from parsing `'()`. This may help you fix the issue. (**-1 points**)
- There is no test of evaluating a let expression that shadows a binding in the previous environment. (**-3 points**)

## Rubric 
```
Baseline/Fixes from HW5:    10/10
Part C:                     28/30
Part D:                     26/30
Part E:                     23/30
Total:                      87/100
```

Nice job!


Ben Toker and Ezra [benezra](https://github.com/orgs/24sp-oberlin-csci275/teams/benezra)  (Extension to Saturday)

Honor Code: yes

Parsing Notes:
- The procedure in an `app-exp` should be parsed. You are just treating it as a symbol, which works for this lab. For example, your `parse` returns `(app-exp 'list '())` for `(parse '(list))` but should return `(app-exp (var-exp 'list) '())`. However, later you will need to parse things like `((lambda x x) 1)`, and this implementation will not work.  (**-2 points**)
- Parsing is where you check for correct syntax structure of the input. This includes verifying that `if` statements having exactly three expressions. When they do not, you should raise a *descriptive* exception. Right now, `parse` does not fail when given a four-plus argument if expression. It fails when given a two-or less argument if expression, since you call `fourth` on the input. But, this error is raised by `fourth`, not `parse`. (**-2 points**)
- There are no tests for parsing if expressions (**-4 points**)
- Again, you did not check the syntax of let expression inputs. (**-2 points**)

Interpreting Notes:
- Your primitive procedure `negate` does not work as expected. Note that `negate` in Minischeme returns the opposite of a number. This is different from `negate` in Racket which takes a predicate and returns the logical negation of that predicate. (**-1 points**)
- Your `car` and `cdr` implementations are not correct, because of your error throwing. Generally, your implementation of the primitive procedures is much more complicated than is necessary. Note that you can use the Racket functions built-in error throwing. I would think about the way you implemented `+` can be generalized. (**-2 points**)
- The presence of `cdr` in your `lt?` primitive causes it to fail. (**-1 points**)
- The issue with `lt?` caused one of the if expression grading tests to fail. (**-2 points**)

## Rubric 
```
Baseline/Fixes from HW5:    10/10
Part C:                     25/30
Part D:                     21/30
Part E:                     28/30
Total:                      84/100
```

Nice job! You should definitely fix your `app-exp` parsing and evaluation and primitive procedure evaluation.

Danny [danny-hw5](https://github.com/orgs/24sp-oberlin-csci275/teams/danny-hw5)   

Honor Code: yes

Parsing Notes:
- None of your parse tree structs are `#:transparent`. For every struct you build, you should add the `#:transparent` tag. This makes testing and debugging much easier. The difference is evaluating `(env '(x) '(1) empty-env)` outputs `#<env>` (without the `#:transparent` tag). However, for a transparent struct, the output will will show its structure, with the previous expression evaluating to `(env '(x) '(1) '())`. This lost you two points per part. (**-6 points**)
- In your tests, in addition to looking at the fields of the constructed parse tree, you should ensure that its structure is what you expect (ie that `(parse (+ 1 2))` returns `(app-exp (var-exp '+) (list (lit-exp 1) (lit-exp 2)))`). This may rely on your parse tree being transparent, but it should be regardless.
- Nice job with having `parse` throw errors when syntax is invalid. It would be preferable to have the procedure `parse` itself do the error raising, with helpful descriptions. For example, right now calling `(parse '(if 1 2))` results in `fourth: list contains too few elements...`. Instead, something like `parse: invalid if syntax` or even better `parse: invalid if syntax, if expects 3 expressions given 2` would be preferred. 
	- Note that you forgot the case where a `let` expression is given more than two arguments. (**-2 points**)

Interpreting Notes:
- Your `init-env` is missing a few bindings. Remember, we defined `x` and `y` to be `23` and `42`, respectively. More importantly, `null` is not bound. (**-1 points**)
- Three grading tests for if expressions failed because `x` and `y` are not bound in the `init-env`. (**-3 points**)
- You should never evaluate both branches of the if statement. Only evaluate the branch that is needed. Since you don't do this, the input `(if True 1 z)` throws an unbound identifier error. 
- There are no tests for evaluating an if expression. (**-4 points**)
- There is no test of evaluating a let expression that shadows a binding in the previous environment. (**-3 points**)

## Rubric 
```
Baseline/Fixes from HW5:    10/10
Part C:                     27/30
Part D:                     21/30
Part E:                     23/30
Total:                      78/100
```

Nice job!


Janny [Janny5](https://github.com/orgs/24sp-oberlin-csci275/teams/janny5)  (Extension to Sunday)

Honor Code: NO!!!

You did not submit the Honor Code! Your grade will not be updated on Campuswire until you do so.

Parsing Notes:
- You have an incorrect extraneous case in your `list?` cond. Checking if the `(first input)` is a `number?` is not necessary. Also, forming a `lit-exp` out of `input` when this is true is incorrect. Although it may seem strange, `(parse '(1 2 3))` should return `(app-exp (lit-exp 1) (list (lit-exp 2) (lit-exp 3)))`. 
- Parsing is where you check for correct syntax structure of the input. This includes verifying that `if` statements having exactly three expressions. When they do not, you should raise a *descriptive* exception. Right now, `parse` does not fail when given a four-plus argument if expression. It fails when given a two-or less argument if expression, since you call `fourth` on the input. But, this error is raised by `fourth`, not `parse`. (**-2 points**)
- Again, you did not check the syntax of let expression inputs. (**-2 points**)


Interpreting Notes:
- The primitive operators and environment should be defined in "interp.rkt", not "env.rkt". All of the primitive operators should be added to `prim-env`.
- You **cannot** assume that the procedure being applied in an `app-exp` is a primitive operator. Instead, you should evaluate the parse procedure with `eval-exp`. Your implementation will fail on the following examples (the second of which is implemented in HW8):
```scheme
(let 
  ([f +])
  (f 1 1))
  
((lambda (x) x) 1)
```
- Your primitive procedures `add1`, `sub1`, and `negate` don't work the way they should because you used `map` instead of `apply`. The procedures `add1` and `sub1` should work exactly the the same as the Racket built-in ones. For example, `(add1 1)` should return `2`. In your implementation, `(add1 1)` returns `'(1)`. (**-3 points**)
- Your implementations of `car` and `cdr` are incorrect. `car` returns the first element of argument list. In your implementation, the argument list is `(first args)`. Note that the way you call `car` should be something like `(car (list 1 2 3))`. (**-2 points**)
- You should not evaluate the condition of an if expression twice. This will cause issues in HW8 when we introduce mutability into Minischeme. Maybe think about using a local binding with `let` to avoid the double evaluation.
- Two grading tests for if expressions failed due to your errors with primitive procedures. (**-4 points**)
- There were no tests for evaluating if expressions. (**-4 points**)
- The issue with your primitive procedure implementation caused one of the let expression grading tests to fail. (**-5 points**)
- There is no test of evaluating a let expression that shadows a binding in the previous environment. (**-3 points**)

## Rubric 
```
Baseline/Fixes from HW5:    10/10
Part C:                     25/30
Part D:                     20/30
Part E:                     30/30
Total:                      75/100
```

Talk to @mollyfeldman if you are confused about the issues with your evaluation of `app-exp`'s. It works for primitive applications, but will fail for all other application types. This is very important for the implementation and testing of `lambda`'s in HW8!


Kenean [KeneanKejela_Minischeme](https://github.com/orgs/24sp-oberlin-csci275/teams/keneankejela_minischeme)  (Extension to Saturday)

Honor Code: yes

Parsing Notes:


Interpreting Notes:

## Rubric 
```
Baseline/Fixes from HW5:    10/10
Part C:                     30/30
Part D:                     30/30
Part E:                     30/30
Total:                      100/100
```

Nice comments and great, extensive tests!


Robert and Leah [robert-leah-5](https://github.com/orgs/24sp-oberlin-csci275/teams/robert-leah-5) [Note: group!]  

Honor Code: yes

Parsing Notes:
- Only one test for parsing an if expression. (**-2 points**)

Interpreting Notes:
- Nice tests for primitive applications!
- You should not evaluate the condition of an if expression twice. This will cause issues in HW8 when we introduce mutability into Minischeme. Maybe think about using a local binding with `let` to avoid the double evaluation.
- There are a couple of issues with the way you bound boolean values in `init-env`. First, having the quoted values inside the quoted list causes an `env-lookup` error when evaluating `'True` or `'False`. Second, these should not be bound to `#t` and `#f`. `#t` is the Racket value of true, not the Minischeme value of true. (**-3 points**)
- No tests for evaluating an if expression. (**-4 points**)
- Evaluating let expressions does not work. You call `parse` on the parsed `let-exp-body`. This throws an error, since parsed expressions are not valid Minischeme syntax. You should **never** be calling `parse` in `eval-exp`. In the REPL flow, the input is fully parsed, then this parse tree is evaluated. (**-10 points**)
- There are no tests for evaluating a let expression. (**-7 points**)

## Rubric 
```
Baseline/Fixes from HW5:    10/10
Part C:                     30/30
Part D:                     21/30
Part E:                     13/30
Total:                      74/100
```




Ben Rapopport and Anya [the-bayan-players-hw5](https://github.com/orgs/24sp-oberlin-csci275/teams/the-bayan-players-hw5) (Extension to Sunday)

Honor Code: yes

Parsing Notes:
- There is only one test for parsing an application. (**-2 points**)
	- Note that `'+` and `'()` are not applications.
- Parsing is where you check for correct syntax structure of the input. This includes verifying that `if` statements having exactly three expressions. When they do not, you should raise a *descriptive* exception. Right now, `parse` does not fail when given a four-plus argument if expression. It fails when given a two-or less argument if expression, since you call `fourth` on the input. But, this error is raised by `fourth`, not `parse`. (**-2 points**)
- There are no tests for parsing if expressions. (**-4 points**)
- Again, you did not check the syntax of let expression inputs. (**-2 points**)

Interpreting Notes:
- Your primitive procedure `negate` does not work as expected. Note that `negate` in Minischeme returns the opposite of a number. This is different from `negate` in Racket which takes a predicate and returns the logical negation of that predicate. (**-1 points**)
- Your implementation of `'null` does not work. This is due to a couple issues with your `env-lookup` function. It seems like the case 
```scheme
[(and (equal? (first sym-list) symbol) (not (is-prim-proc (first val-list) primitive-operators-2)) (not (number? (first val-list)))) (env-lookup next-env (first val-list))]
```
of your `rec-lookup-helper` function is designed to prevent returning anything other than a `number?` or `prim-proc?` from `env-lookup`, instead looking up `symbol` in the previous environment. However, the call `(env-lookup next-env (first val-list))` calls `env-lookup` on a bound value, not a symbol. This is what causes it to fail on `(env-lookup init-env 'null)`. This case will eventually be true, so you call `(env-lookup prim-env '())`. Then, `env-lookup` throws an error, since `'()` is not bound in the `empty-env`. A similar situation happens when looking up `'True` and `'False`. (**-1 points**)
	- Note that you should not have changed `env-lookup` from HW5. You should be able to revert to the previous working version to fix these issues.
- Evaluating `'True` and `'False` does not work (see above). (**-3 points**).
- Your `scheme-bool` function doesn't work correctly. This is a nice idea and you can even extend this  abstraction to all of the primitive predicates. However, there is an issue with the implementation. In `apply-primitive-op`, you pass the list of arguments to `scheme-bool`. But in `scheme-bool`, you call `condi` on `arg` (the list of arguments). For example, when evaluating something like `(number? 1)`, you pass `number?` as `condi` and `'(1)` as `arg`. `(number? '(1))` returns `#f`. This issue makes your `number?`, `list?`, and `null?` predicates to not work. (**-3 points**)
- On several of your primitive predicates, you returned `'true` and `'false` instead of `'True` and `'False`. You should fix `eqv?`, `lt?`, `gt?`, `leq?`, `geq?` by returning the appropriate values. (**-1 points**)
- Issues with primitive predicates caused an if evaluation test to fail. (**-2 points**)
- There are no tests for evaluating if expressions. (**-4 points**)
- Nice tests for let evaluation.


## Rubric 
```
Baseline/Fixes from HW5:    10/10
Part C:                     26/30
Part D:                     15/30
Part E:                     28/30
Total:                      75/100
```

Don't forget about `map` and `apply`! Several of your helper functions (including `first-get`, `second-get`, and `make-list` can be done with `map`). Using higher order functions will save you time and make your code more readable. If you are confused about the feedback on `env-lookup`, talk to @mollyfeldman, @elinorfrost, or me. You need to get this working for HW8. 


Erika [erika-hw5](https://github.com/orgs/24sp-oberlin-csci275/teams/erika-hw5) (Extension to Sunday)

Honor Code: yes

Environment Notes:
- Your `env-lookup` function is great. It works perfectly if you fix your environment struct. That said, there are a couple issues with your environment. The first issue is the names of the fields. You did
```scheme
(struct env (env-syms env-vals env-previous) #:transparent)
```
This defines the `env` constructor and `env?` recognizer correctly. However, the getters for the fields will be `env-env-syms`, `env-env-vals`, and `env-env-previous`. If you rename the fields without the prefix `env-`, you will get the correct getter names. The second issue is that you tried to define the accessors independently: 
```scheme
(define env-syms list)

(define env-previous env)

(define env-vals list)  
```
Remember, whenever you create a data type with `struct`, Racket `define`s all of the getters for you. 
- If you make these changes to the `env`, your `env-lookup` function should work correctly. (Note that `empty-env` lookup test is missing the no argument lambda wrapper. Compare it to the `empty-env` previous test.)

Parsing Notes:
- Your parse tree structs look pretty good. They are all correct except the `ite-exp` which has an extra field `if`.
- Your parsing of applications is correct. 
- There are no tests for parsing applications. (**-4 points**)
- Your parsing of if expressions was not finished. (**-5 points**)
- There are no tests for parsing if expressions. (**-4 points**)
- Your parsing of let expressions was not finished. (**-8 points**)
- There are no tests for parsing let expressions. (**-5 points**)

Interpreting Notes:
- There is still an issue with your evaluation of `var-exp`s. To evaluate `(var-exp 'x)`, we should look up the value of `'x` in the current environment. What your implementation does is just return `'x`. However, `(eval-exp (var-exp 'x) init-env)` should return `23`, since `'x` is bound to `23` in `init-env`. (This is Minischeme B)
- You did not bind `'null` in `init-env`. (**-1 points**)
- Your evaluation of applications is almost correct. The only problem is that you `map` `eval-exp` over the parsed list of arguments. This is the correct idea. However, `eval-exp` takes two arguments: the parse tree and the current environment. Thus, you must `map` a curried version of `eval-exp` to this argument list. If you fix this and the issue with evaluating `var-exp`s, Minischeme C will work. (**-11 points**)
	- Also, your primitive procedure `negate` does not work as expected. Note that `negate` in Minischeme returns the opposite of a number. This is different from `negate` in Racket which takes a predicate and returns the logical negation of that predicate. 
- There is only one test for evaluating an application. (**-3 points**)
- Your implementation of `'True` and `'False` is not correct, since you incorrectly bind them in `init-env`.
- All of the primitive predicates are missing. (**-8 points**)
- Your evaluation of if expressions is almost correct. If you remove the last line `(if co th el)` and fix the parenthesis of the `let`, it should work. (**-6 points**)
- There is only one test for evaluating an if expression. (**-2 points**)
- Your evaluation of let expressions was not finished. (**-10 points**)
- There are no tests for evaluating let expressions. (**-7 points**)

## Rubric 
```
Baseline/Fixes from HW5:    5/10 (Issues with environment struct)
Part C:                     11/30
Part D:                     3/30
Part E:                     0/30
Total:                      21/100
```

Please reach out to @mollyfeldman. Also, consider coming to office hours with @elinorfrost or me. 