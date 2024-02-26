Becca
Honor Code: 
```
Assignment Attempted:   /15
Problem  1:             /10
Problem  2:             /10
Problem  3:             /10
Problem  4:             /10
Problem  5:             /15
Problem  6:             /10
Problem  7:             /10
Problem  8:             /10
TOTAL: /100
```

Maxann
Honor Code: yes
```
Assignment Attempted:   15/15
Problem  1:             10/10
Problem  2:             10/10
Problem  3:             10/10
Problem  4:             10/10
Problem  5:             15/15
Problem  6:             10/10
Problem  7:             10/10
Problem  8:             10/10
TOTAL: 100/100
```

Great job! When writing curried versions of procedures you have already written, you can use existing procedure. For example, you could have done 
```
(define (make-all-same pred)
	(lambda (lst) (all-same? pred lst)))
```
The same applies to `curry-delete-second`. Full credit for your implementations, but you will use currying again in the future and this can save you some time :)
Nice, thoughtful, and concise tests. Your test suites demonstrated general procedure functionality and possible edge cases without redundant examples. Excellent work!

Robert and Leah
Honor Code: yes
```
Assignment Attempted:   15/15
Problem  1:             10/10
Problem  2:             10/10
Problem  3:             10/10 Nice use of a helper function. Note that the third case of the cond in `is-in?` is redundant.
Problem  4:             10/10
Problem  5:             15/15
Problem  6:             10/10 
Problem  7:             10/10
Problem  8:             10/10 The same comment about nesting conds applies here.
TOTAL: 100/100
```

Nice job! 

Danny Perlow (Teamthatiamin)
Honor Code: yes
```
Assignment Attempted:   15/15
Problem  1:             10/10
Problem  2:             10/10
Problem  3:             10/10
Problem  4:             10/10
Problem  5:             15/15
Problem  6:             10/10
Problem  7:             10/10
Problem  8:             10/10 No need to make max-value curried
TOTAL: 100/100
```

Great job! When writing curried versions of procedures you have already written, you can use existing procedure. For example, you could have done 
```
(define (make-all-same pred)
	(lambda (lst) (all-same? pred lst)))
```
The same applies to `curry-delete-second`. Full credit for your implementations, but you will use currying again in the future and this can save you some time :)
Nice, thoughtful, and concise tests. Your test suites demonstrated general procedure functionality and possible edge cases without redundant examples. Excellent work!


Ben an Anya
Honor Code: yes
```
Assignment Attempted:   15/15
Problem  1:             10/10
Problem  2:             10/10
Problem  3:             10/10
Problem  4:             9/10 Incorrect base case.
Problem  5:             13/15 Same as for problem 4.
Problem  6:             10/10
Problem  7:             10/10
Problem  8:             10/10
TOTAL: 97/100
```

Great job! When writing curried versions of procedures you have already written, you can use existing procedure. For example, you could have done 
```
(define (make-all-same pred)
	(lambda (lst) (all-same? pred lst)))
```
The same applies to `curry-delete-second`. Full credit for your implementations, but you will use currying again in the future and this can save you some time :)
One style note: closing parentheses should all be on the same line. Check out the racket fundamentals if you are confused https://campuswire.com/c/GD97EB223/feed/11.


Ben Toker
Honor Code: NO!!
```
Assignment Attempted:   15/15
Problem  1:             /10
Problem  2:             /10
Problem  3:             /10 When possible, style conventions prefer to use a single cond with more conditions instead of nesting conds. You're helper function in-list? is not correct as the following returns #f: (in-list? '() '(())).
Problem  4:             /10
Problem  5:             /15
Problem  6:             /10
Problem  7:             /10
Problem  8:             /10
TOTAL: /100
```

Please sign the Honor Code! You're grade will not be updated on campuswire until you do so.

A style note on the third case of your `all-members?` procedure: 
```
[(= (length lst1) 1) (in-list? (first lst1) lst2)]
```
It is preferred to use the structure of the list instead of its length. I would write 
```
[(empty? (cdr lst)) ...]
```
Also note that this case is redundant.

Great job! When writing curried versions of procedures you have already written, you can use existing procedure. For example, you could have done 
```
(define (make-all-same pred)
	(lambda (lst) (all-same? pred lst)))
```
The same applies to `curry-delete-second`. Full credit for your implementations, but you will use currying again in the future and this can save you some time :)
Please use the default Dr Racket indentation, and don't forget to put your name at the top of each file.

Jasper
Honor Code: 
```
Assignment Attempted:   /15
Problem  1:             /10
Problem  2:             /10
Problem  3:             /10
Problem  4:             /10
Problem  5:             /15
Problem  6:             /10
Problem  7:             /10
Problem  8:             /10
TOTAL: /100
```

Autumn
Honor Code: 
```
Assignment Attempted:   /15
Problem  1:             /10
Problem  2:             /10
Problem  3:             /10
Problem  4:             /10
Problem  5:             /15
Problem  6:             /10
Problem  7:             /10
Problem  8:             /10
TOTAL: /100
```