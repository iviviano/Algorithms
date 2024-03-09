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
- You might be interested in `append*`, which works like `(apply append ...)`.
- Your implementation of `gen-map` only handles 1 "layer" of list nesting. Note that `(gen-map list? lst)` should maintain the structure of `lst`, replacing every atom with `#f`. Your implementation correctly handles `(gen-map list? '(() (1) (1 2)))`, returning `'(() (#f) (#f #f))`. For a deeper nested list, it fails: `(gen-map list? '((() ())))` returns `'((#t #t))` instead of `'((() ()))`.

```
Homework Attempted:     10/10
Problem  1:             10/10
Problem  2:             10/10
Problem  3:             10/10
Problem  4:             10/10
Problem  5:             10/10
Problem  6:             10/10
Problem  7:             10/10
Problem  8:             10/10
Problem  9:             9/10
TOTAL:                  99/100
```

Great job! You've got a good handle on the higher order functions.


Rory and Amanda

Honor Code: yes

Implementation notes:
- `map` handles the the empty list input by returning the `'()`: for any procedure `proc`, `(map proc '())` evaluates to `'()`. This means that you have unnecessary base cases for several problems. 

```
Homework Attempted:     10/10
Problem  1:             10/10
Problem  2:             10/10
Problem  3:             10/10
Problem  4:             10/10
Problem  5:             10/10
Problem  6:             10/10
Problem  7:             10/10
Problem  8:             10/10
Problem  9:             10/10
TOTAL:                  100/100
```

Great job!


Ben and Anya

Honor Code: NO!!!

Implementation notes:
- `map` handles the the empty list input by returning the `'()`: for any procedure `proc`, `(map proc '())` evaluates to `'()`. This means that you have unnecessary base cases for several problems. 

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


