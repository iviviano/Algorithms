`(define (env-lookup-t s e) (env-lookup e s))`

# Elinor People

## Al [al-minischeme](https://github.com/orgs/24sp-oberlin-csci275/teams/al-minischeme)

Honor Code: yes

Environment notes:
- Excellent tests for `env-lookup`!

Parsing notes:
- Nice tests for `parse`.

Interpreting notes:
- Nice job on your tests for `interp` constructing the parse tree without `parse`.

```
Part 1:         10/10
Part 2:         50/50
Part A:         20/20
Part B:         20/20
TOTAL:          100/100
```

Nice job!

## Atticus and Shane [atticus-shane-minischeme](https://github.com/orgs/24sp-oberlin-csci275/teams/atticus-shane-minischeme) 

Honor Code: NO!!

Neither of you signed the Honor Code, your grades will not be updated on Campuswire until you do so.

Environment notes:
- Excellent tests for `env-lookup`!

Parsing notes:
- Nice tests for `parse`. In addition to looking at the fields of the constructed parse tree, you should ensure that its structure is what you expect (ie that `(parse 5)` returns `(lit-exp 5)`). This will be helpful when the parse tree gets more complicated in the upcoming assignments.

Interpreting notes:
- Nice job on your tests for `interp` constructing the parse tree without `parse`.

```
Part 1:         10/10
Part 2:         50/50
Part A:         20/20
Part B:         20/20
TOTAL:          100/100
```

Nice job!

## Daniel [daniel-minischeme](https://github.com/orgs/24sp-oberlin-csci275/teams/daniel-minischeme)  

Honor Code: yes 

Environment notes:
- You forgot to test the case of looking up a symbol in the `empty-env` (**-3 points**)

Parsing notes:
- When testing `parse`, in addition to looking at the fields of the constructed parse tree, you should ensure that its structure is what you expect (ie that `(parse 5)` returns `(lit-exp 5)`). This will be helpful when the parse tree gets more complicated in the upcoming assignments.

Interpreting notes:
- Excellent tests for `interp`! In particular, nice job constructing the parse tree without using `parse`.

```
Part 1:         10/10
Part 2:         47/50
Part A:         20/20
Part B:         20/20
TOTAL:          97/100
```

Nice job! 

## Henry [henryscheme](https://github.com/orgs/24sp-oberlin-csci275/teams/henryscheme)  

Honor Code: NO!

You did not sign the Honor Code. Your grade will not be updated on Campuswire until you do so.

Environment notes:
- You didn't follow the convention for parenthesis types in `letrec` in `env-lookup`. Instead of 
```
(letrec
    ([...]
     [...])
  body)
```
you did 
```
(letrec
    [(...)
     (...)]
  [proc...])
```
I would recommend switching to the first type for several reasons. (1) it is better style and follows Racket/Scheme conventions (using brackets for a procedure call is especially unusual). (2) It is consistent with how you write your `cond`. (3) it is more readable and easier to understand what is going on.

Parsing notes:
- When testing `parse`, make sure to check the actual values of the the parse tree instead of just the structure (ie that `(parse 5)` returns `(lit-exp 5)`). This will be helpful when the parse tree gets more complicated in the upcoming assignments.

Interpreting notes:
- Nice job constructing the parse tree without using `parse`.

```
Part 1:         10/10
Part 2:         50/50
Part A:         20/20
Part B:         20/20
TOTAL:          100/100
```

Nice job!


## Kai [kai_hw5](https://github.com/orgs/24sp-oberlin-csci275/teams/kai_hw5)  

Honor Code: yes

Environment notes:
- For every struct you build (including parse tree `lit-exp` and `var-exp`, you should add the `#:transparent` tag. This makes testing and debugging much easier. Since your environment is not transparent, evaluating `(env '(x) '(1) empty-env)` outputs `#<env>`. However, for a transparent struct, the output will will show its structure, with the previous expression evaluating to `(env '(x) '(1) '())`.  (**-1 points**)
- Nice tests for `env-lookup`!
- Your implementation of `env-lookup` works fine for Minischeme A and B. However, you may want to modify it for the future assignments. Here is a case to consider: 
```
(env-lookup (env '(a) (list null) empty-env) 'a)
```

Parsing notes:
- When testing `parse`, in addition to looking at the fields of the constructed parse tree, you should ensure that its structure is what you expect (ie that `(parse 5)` returns `(lit-exp 5)`). This will be helpful when the parse tree gets more complicated in the upcoming assignments.

Interpreting notes:
- Nice job constructing the parse tree without using `parse`.

```
Part 1:         9/10
Part 2:         50/50
Part A:         20/20
Part B:         20/20
TOTAL:          99/100
```


## Maxann [Maxann_hw5](https://github.com/orgs/24sp-oberlin-csci275/teams/maxann_hw5)  

Honor Code: yes

Environment notes:
- A couple of your tests are not quite right. For your "symbol in an empty environment" and "Symbol not present" tests, you forgot to call `env-lookup` on the environment and symbol. However, this still raises an exception since `test-env` and `empty-env` are not procedures. This causes your tests to pass even though they are not right. You should correct these tests and ensure that they still pass when formulated appropriately.

Parsing notes:
- You did the same thing in testing errors for `parse`. Again, since you forgot the procedure, calling the arguments raised an exception. Here however, one of your tests was actually wrong, since `(parse 'a)` works just fine.
- Other than the issues with error testing, your `parse` tests are excellent! I love that you tested the identity, structure, and accessed the value of the parse tree. This is a good practice for the rest of Minischeme and will help with debugging in the future :)

Interpreting notes:
- You are missing an important test case for `eval-exp`. If we run `(eval-exp (lit-exp 'sym) environment)` and `'sym` is not bound in `environment`, `eval-exp` should throw an error. Note that your implementation of `eval-exp` does this correctly (through `env-lookup`). (**-2 points**)
- Again, your error tests are producing exceptions because of the missing procedure call...

```
Part 1:         10/10
Part 2:         50/50
Part A:         20/20
Part B:         18/20
TOTAL:          98/100
```

Nice job! If you are confused about the issue with you error testing, feel free to talk to @mollyfeldman or @iviviano or me in office hours :)

## Sampad and Khalid [Sampad_Khalid_Minischeme](https://github.com/orgs/24sp-oberlin-csci275/teams/sampad_khalid_minischeme) 

Honor Code: yes

Environment notes:
- For every struct you build, you should add the `#:transparent` tag. This makes testing and debugging much easier. Since your environment is not transparent, evaluating `(env '(x) '(1) empty-env)` outputs `#<env>`. However, for a transparent struct, the output will will show its structure, with the previous expression evaluating to `(env '(x) '(1) '())`.  (**-1 points**)
- Your `env-lookup` function does not throw the correct error for looking up a symbol in the `empty-env`. Maybe consider changing the cases of your `cond` or the placement of your `let` expression. This didn't show up in your testing, because it still threw an error. (**-7 points**)
- Very nice, extensive test suite.

Parsing notes:
- Note that you can do `(provide (all-defined-out))` in your "parse.rkt" file instead of listing each procedure. This will save you some typing :)

Interpreting notes:
- Nice test suite for `interp`
- One note on your test for evaluating a boolean literal expression. While it correctly demonstrates the functionality of `interp`, `(parse #t)` will throw an error, not return a `lit-exp`. 

```
Part 1:         9/10
Part 2:         43/50
Part A:         20/20
Part B:         20/20
TOTAL:          92/100
```

Very nice comments, and great job!

# My People

(define (env-lookup-t s e) (env-lookup e s))

## Alec [alec5](https://github.com/orgs/24sp-oberlin-csci275/teams/alec5)   

Honor Code: yes

Environment notes:
- For every struct you build, you should add the `#:transparent` tag. This makes testing and debugging much easier. Since your environment is not transparent, evaluating `(env '(x) '(1) empty-env)` outputs `#<env>`. However, for a transparent struct, the output will will show its structure, with the previous expression evaluating to `(env '(x) '(1) '())`.  (**-1 points**)
- Cool use of a `fold` for `env-lookup`!
- You forgot to test the case of looking up a symbol in the `empty-env` (**-3 points**)

Parsing notes:
- Note that you can do `(provide (all-defined-out))` in your "parse.rkt" file instead of listing each procedure. This will save you some typing :)
- Nice job with `parse` tests. For future, in addition to looking at the fields of the constructed parse tree, you should ensure that its structure is what you expect (ie that `(parse 5)` returns `(lit-exp 5)`). This will be helpful when the parse tree gets more complicated in the upcoming assignments.

Interpreting notes:
- You are missing a test for when a `var-exp`'s symbol is not bound in the current environment. Your test that is labeled this way fails because `'()` is not a `lit-exp?` or a `var-exp?`, so `eval-exp` throws your "data type not supported. you provided " error. (**-2 points**)
- Nice job constructing the parse tree without using `parse` in your tests of `eval-exp`.

```
Part 1:         9/10
Part 2:         47/50
Part A:         20/20
Part B:         18/20
TOTAL:          94/100
```

Nice comments and great job!

## Ben and Ezra [benezra](https://github.com/orgs/24sp-oberlin-csci275/teams/benezra)  

Honor Code: yes

Environment notes:
- For every struct you build, you should add the `#:transparent` tag. This makes testing and debugging much easier. Since your environment is not transparent, evaluating `(env '(x) '(1) empty-env)` outputs `#<env>`. However, for a transparent struct, the output will will show its structure, with the previous expression evaluating to `(env '(x) '(1) '())`.  (**-1 points**)
- Please use this format for testing: 
```
(test-equal? "label"
              test
              expected)
```
This will make your code more readable.

Parsing notes:
- Note that you can provide everything at once: `(provide parse lit-exp? ...)` or even better use `(provide (all-defined-out))` to do everything in the file and save yourself some typing :)

Interpreting notes:
- You are missing an important test case for `eval-exp`. If we run `(eval-exp (var-exp 'sym) environment)` and `'sym` is not bound in `environment`, `eval-exp` should throw an error. Note that your implementation of `eval-exp` does this correctly (through `env-lookup`). (**-2 points**)
- Nice job constructing the parse tree without using `parse` in your tests of `eval-exp`.

```
Part 1:         9/10
Part 2:         50/50
Part A:         20/20
Part B:         28/20
TOTAL:          97/100
```

Nice job!

## Danny [danny-hw5](https://github.com/orgs/24sp-oberlin-csci275/teams/danny-hw5)   

Honor Code: yes

Sorry about the confusion with your extension! Here is your correct feedback:

Environment notes:
- For every struct you build (including parse tree `lit-exp` and `var-exp`, you should add the `#:transparent` tag. This makes testing and debugging much easier. Since your environment is not transparent, evaluating `(env '(x) '(1) empty-env)` outputs `#<env>`. However, for a transparent struct, the output will will show its structure, with the previous expression evaluating to `(env '(x) '(1) '())`.  (**-1 points**)
- Your `env-lookup` function does not throw the correct error for looking up a symbol in the `empty-env`. Maybe consider changing the cases of your `cond`. This didn't show up in your testing, because it still threw an error. (**-7 points**)
- Note that the testing environments `test-env-a` and `test-env-b` defined in "env.rkt" are not accessible to other files, since you don't provide them.
- Good tests for `env-lookup`.

Parsing notes:
- Note that you can do `(provide (all-defined-out))` in your "parse.rkt" file instead of listing each procedure. This will save you some typing :)
- There are no tests for parsing variables (**-5 points**)
- When testing `parse`, in addition to looking at the fields of the constructed parse tree, you should ensure that its structure is what you expect (ie that `(parse 5)` returns `(lit-exp 5)`). This will be helpful when the parse tree gets more complicated in the upcoming assignments.

Interpreting notes:
- Nice tests for `eval-exp`

```
Part 1:         9/10
Part 2:         43/50
Part A:         20/20
Part B:         15/20
TOTAL:          87/100
```

Nice job!

It looks like you had some github issues or missed a commit. Recommit your files and talk to @mollyfeldman. Also, make sure to add "parse.rkt" to the github repository since it is missing. 



## Janny [Janny5](https://github.com/orgs/24sp-oberlin-csci275/teams/janny5)  

Honor Code: NO! 

Environment notes:
- Your implementation of `env-lookup` works but is bad Racket style. It would be preferred to use recursion or a higher order function to iterate over both the list of symbols and values at the same time.
- When testing `predicates`, use `test-true`, `test-false`, or `test-pred` instead of `(test-equal? ... #t)` or `(test-equal? ... #f)`. Again, this is better style.
- You forgot to test the case of looking up a symbol in the `empty-env` (**-3 points**)

Parsing notes:
- Note that you can do `(provide (all-defined-out))` in your "parse.rkt" file instead of listing each procedure. This will save you some typing :)
- When testing `parse`, in addition to looking at the fields of the constructed parse tree, you should ensure that its structure is what you expect (ie that `(parse 5)` returns `(lit-exp 5)`). This will be helpful when the parse tree gets more complicated in the upcoming assignments.

Interpreting notes:
- Your evaluation of variables is not correct. Think about how the expression `(let ([x 5]) x)` is evaluated in racket. We extend the current environment by binding `x` to `5`. To evaluate the body, we see that it is a variable, so we look up its value in the extended environment and return that. If we were to just evaluate `x`, we use the same process. We look up its value in the current environment, returning the value if it exists and throwing an error otherwise. So, evaluating `var-exp`'s requires looking up the symbol in the environment, not just returning the symbol. (**-5 points**)
- You are missing tests for evaluating a `var-exp` (**-5 points**)
- Nice job constructing the parse tree without using `parse` in your tests of `eval-exp`.

```
Part 1:         10/10
Part 2:         47/50
Part A:         20/20
Part B:         10/20
TOTAL:          87/100
```

If you are confused about any of this feedback, reach out to @mollyfeldman or come to office hours with @elinorfrost or me. It is essential that you get variable evaluation working for the rest of Minischeme to work, so **don't wait to sort this out**. Also, you did not submit the Honor Code. Your grade will not be updated on Campuswire until you do so.


## Kenean [KeneanKejela_Minischeme](https://github.com/orgs/24sp-oberlin-csci275/teams/keneankejela_minischeme)  

Honor Code: yes

Parsing notes:
- Note that you can do `(provide (all-defined-out))` in your "parse.rkt" file instead of listing each procedure. This will save you some typing :)
- Your `parse` tests are excellent! I love that you tested the identity, structure, and accessed the value of the parse tree. This is a good practice for the rest of Minischeme and will help with debugging in the future.

Interpreting notes:
- You are missing an important test case for `eval-exp`. If we run `(eval-exp (var-exp 'sym) environment)` and `'sym` is not bound in `environment`, `eval-exp` should throw an error. Note that your implementation of `eval-exp` does this correctly (through `env-lookup`). (**-2 points**)
- Nice job constructing the parse tree without using `parse` in your tests of `eval-exp`.

```
Part 1:         10/10
Part 2:         50/50
Part A:         20/20
Part B:         18/20
TOTAL:          98/100
```

Nice comments and great job!

## Robert and Leah [robert-leah-5](https://github.com/orgs/24sp-oberlin-csci275/teams/robert-leah-5) 

Honor Code: yes

Parsing notes:
- Note that you can do `(provide (all-defined-out))` in your "parse.rkt" file instead of listing each procedure. This will save you some typing :)
- When testing `parse`, in addition to looking at the fields of the constructed parse tree, you should ensure that its structure is what you expect (ie that `(parse 5)` returns `(lit-exp 5)`). You did this for `var-exp`'s, I just want to make sure you understand the importance, since it will be helpful when the parse tree gets more complicated in the upcoming assignments.

Interpreting notes:
- You are missing an important test case for `eval-exp`. If we run `(eval-exp (var-exp 'sym) environment)` and `'sym` is not bound in `environment`, `eval-exp` should throw an error. Note that your implementation of `eval-exp` does this correctly (through `env-lookup`). (**-2 points**)
- Nice job constructing the parse tree without using `parse` in your tests of `eval-exp`.

```
Part 1:         10/10
Part 2:         50/50
Part A:         20/20
Part B:         18/20
TOTAL:          98/100
```

Nice job!

## Ben and Anya [the-bayan-players-hw5](https://github.com/orgs/24sp-oberlin-csci275/teams/the-bayan-players-hw5) 

Honor Code: yes

Environment notes:
- Your `env-lookup` function could be simplified greatly by using `letrec` to define the helper.

Parsing notes:
- Note that you can do `(provide (all-defined-out))` in your "parse.rkt" file instead of listing each procedure. This will save you some typing :)
- When testing `parse`, in addition to looking at the fields of the constructed parse tree, you should ensure that its structure is what you expect (ie that `(parse 5)` returns `(lit-exp 5)`). This will be helpful when the parse tree gets more complicated in the upcoming assignments.

Interpreting notes:
- Nice job constructing the parse tree without using `parse` in your tests of `eval-exp`.

```
Part 1:         10/10
Part 2:         50/50
Part A:         20/20
Part B:         20/20
TOTAL:          100/100
```

Nice job!


## Erika (not cloned yet) - Extension until Saturday

Honor Code:

Environment notes:
- Please use `empty-env` whenever you wish to use an empty environment. While it is equivalent to writing `'()`, `empty`, or `null`, it is better style.
- You are missing some quotes in your tests for `env-lookup`, which might stop it from running. Try replacing `()` with `empty-env` and `cat` with `'cat`. 
- Your `env-lookup` function is missing arguments in the recursive call. 
- Your `env-lookup` tests are missing the case where the symbol is not bound and the environment is not empty. (**-3 points**)

Parsing notes:
- 

Interpreting notes:
- You forgot to provide `init-env` in your `interp` file, which was causing unbound identifier errors.
- 

```
Part 1:         /10
Part 2:         /50
Part A:         /20
Part B:         /20
TOTAL:          /100
```

