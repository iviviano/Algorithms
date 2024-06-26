
# OCAML

## Em

### Notes
- Code for `weigh` does not run, because of the unused record field name "name". (**-3 points**)

### Rubric
```
Submission                           20/ 20 
3 Problem Implementations:           57/ 60
Documentation and Description:       20/ 20
Total                               97/ 100
```

Nice job!

## Alec

### Notes
- `all-same` does not behave as expected. This should be the equivalent of the Racket procedure `andmap`, but you implemented `ormap` (https://docs.racket-lang.org/reference/pairs.html#%28def._%28%28lib._racket%2Fprivate%2Fmap..rkt%29._andmap%29%29). (**-5 points**)
- Code for `firsts` does not run when called on a list of integers. This is because of your match case that returns `nan`. (**-3 points**)

### Rubric
```
Submission                           20/ 20 
3 Problem Implementations:           52/ 60
Documentation and Description:       20/ 20
Total                               92/ 100
```

Nice job!

## Shane and Atticus (extension to Sunday)

### Notes
- `all-same` does not implement its behavior correctly. This procedure should take a predicate and a list. It returns true if the result of the calling the predicate on each element of the list is true and false otherwise. Note that this is the same as the Racket procedure `andmap` or the OCaml procedure `List.forall`. (**-5 points**)
- `all-same` cannot be called with the correct arguments due to type issues from the way it was implemented. (**-3 points**)
- No description of the process of implementing each procedure. (**-4 points**)
- In line citations are ok.

### Rubric
```
5 Problem Implementations:          71 / 80
Documentation and Description:      20 / 20
Total                              91 / 100
```

Nice job!

## Becca

### Notes
- Code for `make-all-same` does not run due to an in-exhaustive pattern match. (**-3 points**)
- Your implementation of `make-all-same` is incorrect. This procedure should take a predicate and return a procedure which takes a list and calls the predicate on every member of the list, returning true if and only if every result is true. (**-5 points**)
- Your implementation of `sort` is just a built-in procedure. (**-3 points**)
- Your implementation of `dot-product` does not run, since you give the `max` function two arguments, but it expects a single argument list. (**-3 points**)
- Your implementation of `dot-product` does not follow functional programming style since you use for loops and a mutable array. (**-2 points**)
- No description of the process of implementing each procedure. (**-15 points**)
- In line citations are ok.

### Rubric
```
Submission                          20 / 20 
3 Problem Implementations:          32 / 60
Documentation and Description:      20 / 20
Total                              72 / 100
```



Notes:
- No description of the process of implementing each procedure. (**-15 points**)

### Rubric
```
Submission                          20 / 20 
3 Problem Implementations:          45 / 60
Documentation and Description:      20 / 20
Total                              85 / 100
```

Nice job!

---
# Pyret

## Haley

### Notes
- Your implementation of `merge` does not follow functional style, since you use `append`. (**-2 points**)

### Rubric
```
Submission                          20 / 20 
3 Problem Implementations:          58 / 60
Documentation and Description:      20 / 20
Total                              98 / 100
```

Nice job!

## Sampad and Khalid

### Notes
- Your implementation of `merge` does not follow functional style, since you use a `for` loop. (**-2 points**)
- Your experience file has no citations, though you mention using resources besides the guide. (**-5 points**)

### Rubric
```
5 Problem Implementations:          78 / 80
Documentation and Description:      15 / 20
Total                              93 / 100
```

Nice job writing tests!

# ASK MOLLY: they used built in max: ok?
- (**-3 points**)

## Danny

### Notes
- Your experience file is missing citations and notes about the guide you followed. (**-10 points**)

### Rubric
```
Submission                          20 / 20 
3 Problem Implementations:          60 / 60
Documentation and Description:      10 / 20
Total                              90 / 100
```

Nice implementations and tests! 