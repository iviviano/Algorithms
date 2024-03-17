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
- The `cond` in your `fold` lambda of `child-sum` is unnecessary, since we don't create trees with empty children. Similarly, all of the `empty-tree?` cases in your `fold` lambdas will never run.
- It looks like you were trying to handle multiple tree layers at once. For example, in `all-sum`, you fold over the children nodes of the current tree `t`. Instead of adding up the sums of the subtree rooted at each node, you look explicitly at its children. A simple correct solution for this case is `(apply + (tree-value t) (map all-sum (tree-children t))` using `map` and `apply` (using your `helper-sum`, this would be `(+ (tree-value t) (helper-sum (map all-sum (tree-children t))))`). With a `fold`, this case would be `(foldl (lambda (node sum) (+ (all-sum node) sum)) (tree-value t) (tree-children t))`. You had the right ideas, but just ended up overcomplicating it. I think you made similar mistakes on the other tree procedures. It would be a good exercise to try to adapt this code to fix each of the tree procedures.
- `all-sum` fails for trees with height larger than 1 (**-1 points**)
- `visit-tree` returns a list instead of tree, since you didn't call `make-tree` on the updated `tree-value` and children (**-3 points**)
- `size-of` fails for trees with height larger than 1, since you don't always recurse on the children (**-1 points**)
- no recursion makes `height` not work generally (**-1 points**)
- Your `fold` lambda of `pre-order` has only one argument, causing it to throw errors on any trees with height larger than 0 (**-3 points**)
- A good starting point for `pre-order` would be to look at the `leaves` procedure in tree.rkt


Testing Notes:
- Your tests for `visit-tree` are incorrect. `visit-tree` should return a `tree?`, not a `list?`

```
Homework Base:      9/9

Part 1
Problem  1:         10/10
Problem  2:         10/10
Problem  3:         10/10


Part 2
Problem  4:         10/10
Problem  5:         9/10
Problem  6:         8/11
Problem  7:         9/10
Problem  8:         9/10
Problem  9:         7/10
TOTAL:              91/100
```

Nice job! It seems like you have a good handle on folds and higher-order functions. Since you struggled a little with recursion on trees, you might want to talk to @mollyfeldman or come to office hours. 


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

Honor Code: yes

Implementation Notes: 
- Your implementation of `heaviest` is incorrect, since it returns `#<void>` on all inputs. This is because you return the result of `(set! heavy ...)` as your accumulator each call to the `fold` lambda (**-3 points**)
- `set!` is not allowed for any homework (talk to @mollyfeldman if you are confused about whether something is in domain)
- The `cond` in your `map` lambda of `child-sum` is unnecessary, since we don't create trees with empty children. 


Testing Notes:


```
Homework Base:      /9

Part 1
Problem  1:         /10
Problem  2:         /10
Problem  3:         -3/10


Part 2
Problem  4:         /10
Problem  5:         /10
Problem  6:         /11
Problem  7:         /10
Problem  8:         /10
Problem  9:         /10
TOTAL:              /100
```
