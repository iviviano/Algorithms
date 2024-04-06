`(define (env-lookup-t s e) (env-lookup e s))`

# Elinor People

## Al [al-minischeme](https://github.com/orgs/24sp-oberlin-csci275/teams/al-minischeme)

Honor Code:

Environment notes:
- Excellent tests for `env-lookup`!

Parsing notes:
- Nice tests for `parse`. Note that it's not really necessary to look at the fields of the constructed parse tree, if you ensure that the parse tree structure is correct.

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
- Nice tests for `parse`. Instead of looking at the fields of the constructed parse tree, it is better to ensure that its structure is what you expect. (ie that `(parse 5)` returns `(lit-exp 5)`)

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
- When testing `parse`, instead of looking at the fields of the constructed parse tree, it is better to ensure that its structure is what you expect. (ie that `(parse 5)` returns `(lit-exp 5)`)

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
- When testing `parse`, make sure to check the actual values of the the parse tree instead of just the structure. (ie `(parse 5)` returns `(lit-exp 5)`)

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
- For every struct you build, you should add the `#:transparent` tag. This makes testing and debugging much easier. Since your environment is not transparent, evaluating `(env `

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


## Maxann [Maxann_hw5](https://github.com/orgs/24sp-oberlin-csci275/teams/maxann_hw5)  

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


## Sampad and Khalid [Sampad_Khalid_Minischeme](https://github.com/orgs/24sp-oberlin-csci275/teams/sampad_khalid_minischeme) 

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

