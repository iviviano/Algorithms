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
- Your implementation of `pre-order` fails on leaves, since you don't wrap the `(tree-value t)` in a `list`. (**-1 point**)
- All of your `leaf?` cases are unnecessary. The base cases of `map` and `apply` correctly handle the case where `(tree-children t)` is `null`. Removing the `leaf?` case in `preorder` fixes the issue above.

```
Homework Base:      9/9

Part 1
Problem  1:         10/10
Problem  2:         10/10
Problem  3:         9/10


Part 2
Problem  4:         10/10
Problem  5:         10/10
Problem  6:         11/11
Problem  7:         10/10
Problem  8:         10/10
Problem  9:         9/10
TOTAL:              98/100
```

Great job!


Amanda (EXTENSION to Saturday)

Honor Code: yes

Implementation Notes:
- An association list is a list of 2-element lists. So, `weigh` and `heaviest` did not need to check if elements of `bags` were empty. 
- The `cond` in your `fold` lambda of `child-sum` is unnecessary, since we don't create trees with empty children.


Testing Notes:


```
Homework Base:      /9

Part 1
Problem  1:         /10
Problem  2:         /10
Problem  3:         /10


Part 2
Problem  4:         /10
Problem  5:         -1/10
Problem  6:         -3/11
Problem  7:         -1/10
Problem  8:         -1/10
Problem  9:         -3/10
TOTAL:              /100
```


Atticus and Shane

Honor Code: yes

Implementation Notes:
- You used the wrong `fold` for `heaviest`. It fails when there are multiple bags of the maximal weight, returning the name of the last bag, instead of the first. (**-1 point**)
- The `cond` in your `fold` lambda of `child-sum` is unnecessary, since we don't create trees with empty children.
- All of your `leaf?` cases are unnecessary. The base cases of `map` and `apply` correctly handle the case where `(tree-children t)` is `null`. 

Testing Notes:
- Your tests for `visit-tree` do not show that `visit-tree` correctly rebuilds the structure of `t`. The only meaningful test is the `empty-tree` test. (**-3 points**)
- You didn't test a custom tree for `pre-order`. (**-1 point**)

```
Homework Base:      9/9

Part 1
Problem  1:         10/10
Problem  2:         10/10
Problem  3:         9/10


Part 2
Problem  4:         10/10
Problem  5:         10/10
Problem  6:         8/11
Problem  7:         10/10
Problem  8:         10/10
Problem  9:         9/10
TOTAL:              95/100
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

Honor Code: yes

Implementation Notes:
- Your implementation of `visit-tree` was almost correct. You just used the wrong tree constructor. `(make-tree x ...)` makes a tree with value `x` and the rest of the arguments are wrapped in a list as the children. The other constructor, `(tree x children)` makes a  tree with value `x` and children the list `children`. Since your `map` returns the list of updated children, the `tree` constructor would have worked. (**-3 points**)

Testing Notes:
- The way you tested `visit-tree` was great!
For future, please follow this format for tests:
```
(test-equal? "label"
              test
              expected)
```
It helps with readability.

```
Homework Base:      9/9

Part 1
Problem  1:         10/10
Problem  2:         10/10
Problem  3:         10/10


Part 2
Problem  4:         10/10
Problem  5:         10/10
Problem  6:         8/11
Problem  7:         10/10
Problem  8:         10/10
Problem  9:         10/10
TOTAL:              97/100
```

Great job!


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
