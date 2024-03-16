Abby

Honor Code: yes

Implementation Notes:
- You used `=` for comparison in your implementation of `replace`. The procedure `=` only works for comparing `number?`, and throws a contract violation for all other data types. You should always be using `equal?` for comparison in this class. This is one reason you should test your procedures on multiple data types. (**-3 points**)
- Your `helper` function for `heaviest` should have been an anonymous `lambda` or bound with a `let` expression. 
- You have nested `if` statements in your implementation of `child-sum`. If you ever find yourself writing nested `if`'s, please convert it to a `cond`. This is better style and more readable.
- A lot of your `empty-tree?` conditions are unnecessary and could be removed. It would be a good exercise to see which ones are made redundant by `map` and `apply` base cases.

```
Homework Base:      9/9

Part 1
Problem  1:         7/10
Problem  2:         10/10
Problem  3:         10/10


Part 2
Problem  4:         10/10
Problem  5:         10/10
Problem  6:         11/11
Problem  7:         10/10
Problem  8:         10/10
Problem  9:         10/10
TOTAL:              97/100
```

Nice job with trees and higher order functions!

Al

Honor Code: yes

Implementation Notes:
- Nice job using `let` forms to bind your helper functions!
- Your implementation of `all-sum` is fine, but based on the name of the your helper function, it seems like you might be a little bit confused about currying. Check out the Racket Documentation of the `curry` procedure: https://docs.racket-lang.org/reference/procedures.html#%28def._%28%28lib._racket%2Ffunction..rkt%29._curry%29%29
- Your second case of the `cond` in `visit-tree` is redundant. Also, we had a recognizer `leaf?` that checks if a tree has no children. You *should* use tools like this when they are given.
- You have another redundant case in `height`, since `max` can take any positive number of arguments

```
Homework Base:      9/9

Part 1
Problem  1:         10/10
Problem  2:         10/10
Problem  3:         10/10


Part 2
Problem  4:         10/10
Problem  5:         10/10
Problem  6:         11/11
Problem  7:         10/10
Problem  8:         10/10
Problem  9:         10/10
TOTAL:              100/100
```

Great job and nice, thoughtful tests!


Alec

Honor Code: yes

Implementation Notes:
- You used the wrong `fold` for `heaviest`. It fails when there are multiple bags of the maximal weight, returning the name of the last bag, instead of the first. (**-1 point**)
- 

Testing Notes:


```
Homework Base:      /9

Part 1
Problem  1:         /10
Problem  2:         /10
Problem  3:         -1/10


Part 2
Problem  4:         /10
Problem  5:         /10
Problem  6:         /11
Problem  7:         /10
Problem  8:         /10
Problem  9:         -1/10
TOTAL:              /100
```


Amanda (EXTENSION to Saturday)

Honor Code:

Implementation Notes:


Testing Notes:


```
Homework Base:      /9

Part 1
Problem  1:         /10
Problem  2:         /10
Problem  3:         /10


Part 2
Problem  4:         /10
Problem  5:         /10
Problem  6:         /11
Problem  7:         /10
Problem  8:         /10
Problem  9:         /10
TOTAL:              /100
```


Atticus and Shane

Honor Code:

Implementation Notes:


Testing Notes:


```
Homework Base:      /9

Part 1
Problem  1:         /10
Problem  2:         /10
Problem  3:         /10


Part 2
Problem  4:         /10
Problem  5:         /10
Problem  6:         /11
Problem  7:         /10
Problem  8:         /10
Problem  9:         /10
TOTAL:              /100
```


Becca (LATE?)

Honor Code:

Implementation Notes:


Testing Notes:


```
Homework Base:      /9

Part 1
Problem  1:         /10
Problem  2:         /10
Problem  3:         /10


Part 2
Problem  4:         /10
Problem  5:         /10
Problem  6:         /11
Problem  7:         /10
Problem  8:         /10
Problem  9:         /10
TOTAL:              /100
```


Daniel

Honor Code:

Implementation Notes:


Testing Notes:


```
Homework Base:      /9

Part 1
Problem  1:         /10
Problem  2:         /10
Problem  3:         /10


Part 2
Problem  4:         /10
Problem  5:         /10
Problem  6:         /11
Problem  7:         /10
Problem  8:         /10
Problem  9:         /10
TOTAL:              /100
```



Erika (EXTENSION to Saturday)

Honor Code:

Implementation Notes:


Testing Notes:


```
Homework Base:      /9

Part 1
Problem  1:         /10
Problem  2:         /10
Problem  3:         /10


Part 2
Problem  4:         /10
Problem  5:         /10
Problem  6:         /11
Problem  7:         /10
Problem  8:         /10
Problem  9:         /10
TOTAL:              /100
```
