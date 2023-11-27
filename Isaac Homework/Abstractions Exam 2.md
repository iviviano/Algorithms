<p align=center>
Programming Abstractions <br>
Exam 2 <br>
Isaac Viviano
</p>

>[!note] 1

(a) 

(b) 

(c) false

>[!note] 2

(a) ```((λ () 1))```

(b) ```(curry + 1)```

(c) ```#t```

>[!note] 3

(a) e = [x -> 3, y -> 17], f = e([x -> 39, a -> 96]),  g = f([y -> 4])

(b) 

(c) extended environment: g([x -> 22, y -> 60])

>[!note] 4

Currently, `(parse '(1 + 2))` returns something like `(app-exp (lit-exp 1) (list (var-exp '+) (lit-exp 2)))`. To implement infix notation, we want to parse `(1 + 2)` to something like `(app-exp (var-exp '+) (list (lit-exp 1) (lit-exp 2)))`. So, in the list cases of parse, we should add a condition to check if `(cadr input)` is one of the infix procedures. Then, check the syntax and parse input to `(app-exp (var-exp (cadr input))`


>[!note] 5

Changing parse.rkt would be sufficient, as long as interp.rkt only uses the provided accessors to access fields of parse tree structs. The new struct declarations would be 
```{racket}
(struct app-exp (args proc) #:transparent)
(struct ite-exp (else then cond) #:transparent)
(struct let-exp (body exps syms) #:transparent)
```
We need to change parse so that the 