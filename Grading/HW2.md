Erika:

Honor Code: yes
```
Homework Base:      20/20
Problem  1:         10/10
Problem  2:         10/10
Problem  3:         9/10 Your implementation correctly identifies whenever the elements of sublist appear in biglist in order. However, it does not determine whether they appear consecutively. For example, (has-sublist? '(x y z) '(a x y b z)) should return #f. One way to fix this is with a helper predicate that recognizes if the elements of a sublist are the first elements of a biglist. 
Problem  4:         7/10 Incomplete procedure. Lost 1 additional point on tests for not having a test where the sublist is not in the biglist.
Problem  5:         10/10
Problem  6:         8/10 Your implementation fails for all nonempty lists, since you call second on the list. 
Problem  7:         10/10
Problem  8:         9/10 Your implementation of all-exchange is circular. For example, (all-exchange '(a c) '(c a) '(c)) should return '(a) instead of '(c).
TOTAL:              93/100
```

Nice job overall, especially with tests. For future, use the default Dr Racket indentation and follow this format for your tests:
```
(test-equal? "label"
              test
              expected)
```
These will make your code more readable.
I saw your commit messages. Remember that you can ask for an extension *before the due date* if you won't be able to finish a homework on time.

Haley:

Honor Code: yes
```
Homework Base:      20/20
Problem  1:         10/10
Problem  2:         10/10 No points off this week, but you should avoid using append. Use cons instead to construct lists. Also, you should use a letrec for helper functions. 
Problem  3:         8/10 A comment on the second case of your cond: try to make your conditions as simple as possible. If you find yourself using or, you can split this into two cond cases. Also, avoid using functions like length or index for lists. We want to operate based on their recursive structure. You had the right idea using a helper function here. I think it would have worked better if you used it in the condition of that cond case and added the appropriate base cases. As is, your implementation fails on inputs like (has-sublist? '(x y z) '(a b c x y)) and (has-sublist? '(x y z) '(a x z y b)).
Problem  4:         9/10 Again, don't use append. Here especially, it just complicates your implementation. You used the helper function correctly here. However, the following input has an error due to missing base cases in your helper: (delete-sublist '(x y) '(x x)).
Problem  5:         10/10
Problem  6:         10/10
Problem  7:         10/10
Problem  8:         9/10 Your implementation of all-exchange is circular. For example, (all-exchange '(a c) '(c a) '(c)) should return '(a) instead of '(c).
TOTAL:              96/100
```

Great job and excellent tests! 

Please only submit the required files to github. You can use a .gitignore file to prevent committing extra stuff: https://git-scm.com/docs/gitignore.

One style note: closing parentheses should all be on the same line. Check out the racket fundamentals if you are confused https://campuswire.com/c/GD97EB223/feed/11.

Janny:

Honor Code: yes
```
Homework Base:      20/20
Problem  1:         5/10 Please use letrec in the future for helper functions. Note that you could assume input lists were sorted for this problem.
Problem  2:         5/10 This implementation relies on merge working on unsorted lists.
Problem  3:         4/10 Everything works except that the order of your base cases is wrong. So, (has-sublist? null null) returns #f but should return #t.
Problem  4:         5/10 
Problem  5:         5/10
Problem  6:         5/10
Problem  7:         0/10 Missing
Problem  8:         4/10 I think that using so many helper functions overcomplicated the problem. Your implementation fails on the inputs: (all-exchange '(a c) '(c a) '(c)) and (all-exchange '(a b c) '(x y z) '(a b r a c a d a b r a)). The first should return '(a) and the second should return '(x y r x z x d x y r x).
TOTAL:              53/100
```

You lost 5 points on every problem because there were no tests in your tests.rkt file. If this is a github issue, please reach out to Molly.


Jkutchey

Honor Code: NO!!
```
Homework Base:      20/20
Problem  1:         10/10
Problem  2:         10/10
Problem  3:         10/10 Cool implementation of has-sublist?. Please use a letrec for your helper functions in the future :)
Problem  4:         9/10 This strategy overcomplicated the delete-sublist? function. It failed on the (delete-sublist '(x y z) '(a b x y z c)). Your function returned '((a b) c) instead of '(a b c). No points off, but append will not be allowed on future homeworks unless otherwise noted.
Problem  5:         8/10 Your base case is wrong for nest. (nest '()) should return '() instead of '(()). 
Problem  6:         10/10
Problem  7:         9/10 Again, there is a simpler way to do exchange. Try to do it without a helper function based on the structure of lst. Your implementation didn't work on singletons because of issues with the connect helper.
Problem  8:         9/10 Your implementation of all-exchange was missing base cases to handle empty replacement lists: (all-exchange null null '(1 2 3)) raises an error. It is also circular: (all-exchange '(a b) '(b a) '(a a)) should return '(b b) but returns '(a a).
TOTAL:              97/100
```

You did not sign the Honor Code! Your grade will not be updated on campus wire until you do so.

Great job and excellent tests!


Kai:

Honor Code: yes
```
Homework Base:      20/20
Problem  1:         10/10 Great job using letrec for your helper function.
Problem  2:         10/10
Problem  3:         9/10 You are missing a base case to check if sublist is empty, so (has-sublist? empty empty) fails.
Problem  4:         9/10 Lost 1 point for not testing the empty sublist case.
Problem  5:         10/10
Problem  6:         10/10
Problem  7:         10/10
Problem  8:         9/10 Your implementation of all-exchange is circular. For example, (all-exchange '(a c) '(c a) '(a)) should return '(c) instead of '(a).
TOTAL:              97/100
```

Great job! Please make use of the `cond` special form more. It is generally more readable than `if`. Every instance of nested `if`'s should be replaced by a `cond`.

Also, follow this format for your tests:
```
(test-equal? "label"
              test
              expected)
```


Kenean 

Honor Code: yes
```
Homework Base:      20/20
Problem  1:         10/10
Problem  2:         10/10
Problem  3:         10/10 For future, avoid functions like take and length. We want to recurse based on the pairwise structure of lists.
Problem  4:         10/10
Problem  5:         10/10
Problem  6:         10/10
Problem  7:         10/10
Problem  8:         10/10
TOTAL:              100/100
```

Great job and excellent tests! Great comments, it's especially helpful to have descriptions of your helper functions :) For future assignments, you should use a `let` form to define helpers if they are only used for a single procedure.


Leah and Henry:

Honor Code:
```
Homework Base:      /20
Problem  1:         /10
Problem  2:         /10
Problem  3:         /10
Problem  4:         /10
Problem  5:         /10
Problem  6:         /10
Problem  7:         /10
Problem  8:         /10
TOTAL:              /100
```
