[alec5](https://github.com/orgs/24sp-oberlin-csci275/teams/alec5)   

Honor Code: yes

### Part F
- 

### Part G
- 

### Part H
- 

# Rubric
```
MiniScheme F:       30/30
MiniScheme G:       40/40
MiniScheme H:       30/30
TOTAL:              100/100
```

Everything looks great! Nice job!

Ben and Ezra [benezra](https://github.com/orgs/24sp-oberlin-csci275/teams/benezra)  (Extension to Saturday)

Honor Code: yes

### Part F
- No tests for evaluating a `lambda-exp` or its application. (**-5 points**)

### Part G
- `set-exp` and `begin-exp` are not `#:transparent`. (**-4 points**)
- No tests for parsing `set!` or `begin`. (**-10 points**)
- No tests for evaluating `set!` or `begin`. (**-10 points**)

### Part H
- No tests for parsing a `letrec`. Note that tests use any of these procedures: https://docs.racket-lang.org/rackunit/api.html#%28def._%28%28lib._rackunit%2Fmain..rkt%29._test-check%29%29. (**-5 points**)
- No tests for evaluating a parsed `letrec`. (**-5 points**)

# Rubric
```
MiniScheme F:       25/30
MiniScheme G:       16/40
MiniScheme H:       20/30
TOTAL:              61/100
```

Nice implementations, but you were missing a lot of tests.

[danny-hw5](https://github.com/orgs/24sp-oberlin-csci275/teams/danny-hw5)   (Extension to Saturday)

Honor Code:

### Part F
- `lambda-exp` is not `#:transparent`. (**-2 points**)
- `closure` is not `#:transparent`. (**-2 points**)
- The `newenv` created in `eval-app-exp` does not affect evaluation: the behavior would be exactly the same if you just used `environment`. This is because `(parse '())` throws an error. However, if this extension were needed, it would cause an issue since you didn't `box` the value `'()`.
- Excellent syntax testing in parse! The descriptive errors are great!

### Part G
- `set-exp` is not `#:transparent`. (**-2 points**)
- `begin-exp` is not `#:transparent`. (**-2 points**)
- No tests for evaluating a `set-exp`. (**-5 points**)
- No tests for evaluating a `begin-exp`. (**-5 points**)

### Part H
- No tests for evaluating a parsed `letrec`. (**-5 points**)

# Rubric
```
MiniScheme F:       26/30
MiniScheme G:       26/40
MiniScheme H:       25/30
TOTAL:              77/100
```

HW8 is missing. If this is a github issue, please talk to @mollyfeldman.

[Janny5](https://github.com/orgs/24sp-oberlin-csci275/teams/janny5)  (Extension to Monday)

Honor Code: yes

### Part F
- 

### Part G
- 

### Part H
- 

# Rubric
```
MiniScheme F:       30/30
MiniScheme G:       40/40
MiniScheme H:       30/30
TOTAL:              100/100
```

Great job!

[KeneanKejela_Minischeme](https://github.com/orgs/24sp-oberlin-csci275/teams/keneankejela_minischeme) (Extension to Sunday) 

Honor Code: yes

### Part F
- 

### Part G
- 

### Part H
- 

# Rubric
```
MiniScheme F:       30/30
MiniScheme G:       40/40
MiniScheme H:       30/30
TOTAL:              100/100
```

Great job!

[robert-leah-5](https://github.com/orgs/24sp-oberlin-csci275/teams/robert-leah-5) [Note: group!] (Extension to Wednesday) 

Honor Code: yes

### Part G
- Note that your input length check in parsing a `begin` is unnecessary due to the `map` base case.

### Part H
- The way you created the dummy symbols for `letrec` does not always work for multiple bindings. Consider the following modification of the mutually recursive `even`-`odd` example: 

```scheme
(letrec ([proc (lambda (n) (if (eqv? 0 n) True (proc1 (sub1 n))))]  
		 [proc1 (lambda (n) (if (eqv? 0 n) False (proc (sub1 n))))])
		 (proc1 5))
```
which returns `'False` but should return `'True`. **-6 points** 
# Rubric
```
MiniScheme F:       30/30
MiniScheme G:       40/40
MiniScheme H:       24/30
TOTAL:              94/100
```

Nice job and excellent tests!

Ben and Anya [the-bayan-players-hw5](https://github.com/orgs/24sp-oberlin-csci275/teams/the-bayan-players-hw5) (Extension to Monday)

Honor Code: yes

### Part F
- Just like `let`, you should *not* parse the parameter symbols for a `lambda`. (**-2 points**)

### Part G
- Note that using a `map` for `begin` works because `map` is tail recursive and thus iterates left to right. However, your implementation of `begin` evaluation is not quite correct due to your `return-not-void` helper. `begin` evaluates its given expressions sequentially from left to right. It should always return the result of the last evaluation, regardless of which ones are void. For example, `(begin 1 2 3)` evaluates to `3` and `(begin 1 (set! x 1))` evaluates to `#<void>`. (**-5 points**)

### Part H
- Note that the issues with begin evaluation don't affect `letrec` evaluation since only the rightmost expression of the `letrec`'s `begin` is not `#<void>` (the rest are the results of `set!`'s).

Although your implementation of Minischeme passed most of the grading tests, there are a couple important issues that should be addressed.
1. You parsed the symbols of let bindings and lambda parameters. It is frowned upon to parse the symbols, because you just end up unwrapping the `var-exp`. We know that the `let-exp-syms` field is a list of symbols (not a parse tree), so this is redundant. The same goes for parsing the lambda symbols. It seems like this is what your `make-list-2` helper was for. 
2. Your use of the `make-list` helper to evaluate a list of expressions. You can abstract this functionality by using `(map (lambda (x) (eval-exp x e)) args)`. However, `make-list` is missing some cases in the cond, so it cannot evaluate the list `args` when it contains a parsed `let`, `set!`, or `begin`. Since there is no else in the cond, `(make-list args e)` returns `#<void>` whenever `(first args)` is one of these types. For example, evaluating `'(+ 1 (let ([x 1]) x))` causes an error from a `#<void>` showing up. Thus, you have missed the complete recursive language, but "surface-level" evaluation works well. 

# Rubric
```
MiniScheme F:       28/30
MiniScheme G:       35/40
MiniScheme H:       30/30
TOTAL:              93/100
```

Nice job!

[erika-hw5](https://github.com/orgs/24sp-oberlin-csci275/teams/erika-hw5) [REGRADE HW6] (Extension to Sunday)

Honor Code: NO!

You did not sign the Honor Code. Grades will not be updated on campuswire until you do so.

# HW5 Regrade
### Environments
- **15.5 points** back

### Part A
- Correct before, no changes.

### Part B
- **2.5 points** back

Everything was correct, you got half of the points you missed back.

```
Part 1:         10/10
Part 2:         34.5/50
Part A:         20/20
Part B:         17.5/20
TOTAL:          82/100
```

# HW6 Regrade
### Part C
- Added a parsing application test. (**+1 points**)
- Because you don't parse the procedure in applications, their evaluation still doesn't work.

### Part D
- Added a parsing if test. (**+1 points**) 
- Added a test for evaluating an `ite-exp`. (**+1 points**)

### Part E
- Parsing still does not work since you have `(map parse (map first input))` instead of `(map parse (map first (second input)))`.
- Evaluation still missing for `let-exp`.

```
Baseline/Fixes from HW5:    7.5/10
Part C:                     12/30
Part D:                     5/30
Part E:                     0/30
Total:                      24.5/100
```


# HW8 Grade
### Part F
- Only lambda parsing works, since you don't have a `closure` data type. (**-10 points**)
- No tests for parsing lambda's. (**-5 points**)
- No tests for evaluating `lambda-exp`'s or their application. (**-5 points**)

### Part G
- When parsing `set!`, the symbol should not be parsed. (**-5 points**)
- Begin evaluation not finished. (**-5 points**)
- Set evaluation sets the box's value to Racket's `exp` (the natural exponential function), not the evaluated `set!` body. (**-5 points**)
- No tests for parsing set. (**-5 points**)
- No tests for parsing begin. (**-5 points**)
- No tests for evaluating `begin-exp`'s. (**-5 points**)
- No tests for evaluating `set-exp`'s. (**-5 points**)

### Part H
- Not complete.

# Rubric
```
MiniScheme F:       10/30
MiniScheme G:       5/40
MiniScheme H:       0/30
TOTAL:              15/100
```
