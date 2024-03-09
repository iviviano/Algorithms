Becca (extension)

Honor Code:

Implementation notes:


Testing notes:

```
Homework Attempted:     /10
Problem  1:             /10
Problem  2:             /10
Problem  3:             /10
Problem  4:             /10
Problem  5:             /10
Problem  6:             /10
Problem  7:             /10
Problem  8:             /10
Problem  9:             /10
TOTAL:                  /100
```


Al

Honor Code: yes

Implementation notes:
- You used a helper function for `mat-vec-mul`, which is fine. From now on, you should avoid using `define` to declare helpers if they are only used in one procedure. Instead, use an appropriate `let` form or an anonymous `lambda`.
- If you're going to use `append` on a homework assignment or exam, please talk to Molly and make sure it's ok. No points off this week, since `append` allows the use of higher order functions for `flatten`. Also, you might be interested in `append*`, which works like `(apply append ...)`.
- Your implementation of `gen-map` only handles 1 "layer" of list nesting. Note that `(gen-map list? lst)` should maintain the structure of `lst`, replacing every atom with `#f`. Your implementation correctly handles `(gen-map list? '(() (1) (1 2)))`, returning `'(() (#f) (#f #f))`. For a deeper nested list, it fails: `(gen-map list? '((() ())))` returns `'((#t #t))` instead of `'((() ()))`.


Testing notes:

```
Homework Attempted:     /10
Problem  1:             /10
Problem  2:             /10
Problem  3:             /10
Problem  4:             /10
Problem  5:             /10
Problem  6:             /10
Problem  7:             /10
Problem  8:             /10
Problem  9:             -1/10
TOTAL:                  /100
```

Great job! You've got a good handle on the higher order functions.

Rory and Amanda

Honor Code:

Implementation notes:


Testing notes:

```
Homework Attempted:     /10
Problem  1:             /10
Problem  2:             /10
Problem  3:             /10
Problem  4:             /10
Problem  5:             /10
Problem  6:             /10
Problem  7:             /10
Problem  8:             /10
Problem  9:             /10
TOTAL:                  /100
```


Ben and Anya

Honor Code:

Implementation notes:


Testing notes:

```
Homework Attempted:     /10
Problem  1:             /10
Problem  2:             /10
Problem  3:             /10
Problem  4:             /10
Problem  5:             /10
Problem  6:             /10
Problem  7:             /10
Problem  8:             /10
Problem  9:             /10
TOTAL:                  /100
```


William (extension, due Saturday)

Honor Code:

Implementation notes:


Testing notes:

```
Homework Attempted:     /10
Problem  1:             /10
Problem  2:             /10
Problem  3:             /10
Problem  4:             /10
Problem  5:             /10
Problem  6:             /10
Problem  7:             /10
Problem  8:             /10
Problem  9:             /10
TOTAL:                  /100
```


