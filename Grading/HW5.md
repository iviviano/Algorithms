`(define (env-lookup-t s e) (env-lookup e s))`

# Elinor People

## Al [al-minischeme](https://github.com/orgs/24sp-oberlin-csci275/teams/al-minischeme)

Honor Code:

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

Parsing notes:
- 

Interpreting notes:
- 

```
Part 1:         9/10
Part 2:         43/50
Part A:         /20
Part B:         /20
TOTAL:          /100
```

Very nice comments

# My People

## Alec [alec5](https://github.com/orgs/24sp-oberlin-csci275/teams/alec5)   

Honor Code:

Environment notes:
- 

Parsing notes:
- 

Interpreting notes:
- 

```
Part 1:         /10
Part 2:         /50
Part A:         /20
Part B:         /20
TOTAL:          /100
```



## Ben and Ezra [benezra](https://github.com/orgs/24sp-oberlin-csci275/teams/benezra)  
Honor Code:

Environment notes:
- 

Parsing notes:
- 

Interpreting notes:
- 

```
Part 1:         /10
Part 2:         /50
Part A:         /20
Part B:         /20
TOTAL:          /100
```



## Danny [danny-hw5](https://github.com/orgs/24sp-oberlin-csci275/teams/danny-hw5)   

Honor Code:

Environment notes:
- 

Parsing notes:
- 

Interpreting notes:
- 

```
Part 1:         /10
Part 2:         /50
Part A:         /20
Part B:         /20
TOTAL:          /100
```



## Janny [Janny5](https://github.com/orgs/24sp-oberlin-csci275/teams/janny5)  

Honor Code:

Environment notes:
- 

Parsing notes:
- 

Interpreting notes:
- 

```
Part 1:         /10
Part 2:         /50
Part A:         /20
Part B:         /20
TOTAL:          /100
```



## Kenean [KeneanKejela_Minischeme](https://github.com/orgs/24sp-oberlin-csci275/teams/keneankejela_minischeme)  

Honor Code:

Environment notes:
- 

Parsing notes:
- 

Interpreting notes:
- 

```
Part 1:         /10
Part 2:         /50
Part A:         /20
Part B:         /20
TOTAL:          /100
```



## Robert and Leah [robert-leah-5](https://github.com/orgs/24sp-oberlin-csci275/teams/robert-leah-5) 

Honor Code:

Environment notes:
- 

Parsing notes:
- 

Interpreting notes:
- 

```
Part 1:         /10
Part 2:         /50
Part A:         /20
Part B:         /20
TOTAL:          /100
```


## Ben and Anya [the-bayan-players-hw5](https://github.com/orgs/24sp-oberlin-csci275/teams/the-bayan-players-hw5) 

Honor Code:

Environment notes:
- 

Parsing notes:
- 

Interpreting notes:
- 

```
Part 1:         /10
Part 2:         /50
Part A:         /20
Part B:         /20
TOTAL:          /100
```



## Erika (not cloned yet) - Extension until Saturday

Honor Code:

Environment notes:
- 

Parsing notes:
- 

Interpreting notes:
- 

```
Part 1:         /10
Part 2:         /50
Part A:         /20
Part B:         /20
TOTAL:          /100
```

