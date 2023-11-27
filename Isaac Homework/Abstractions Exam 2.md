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

Currently, `(parse '(1 + 2))` returns something like `(app-exp (lit-exp 1) (list (var-exp '+) (lit-exp 2)))`. To implement infix notation, we want to parse `(1 + 2)` to something like `(app-exp (var-exp '+) (list (lit-exp 1) (lit-exp 2)))`. So, in the list cases of parse, we should add a condition to check if `(cadr input)` is one of the infix procedures. Then, check the syntax and parse input to `(app-exp (var-exp (cadr input)) (map parse (list* (car input) (cddr input)))`. Then, infix applications are parsed to the equivalent of the prefix application, so they may be evaluated the same way. So, we must only change parse to implement infix operations.

Since we must change parse for implementation, we need to find a way to remove prefix from the grammar. We should add a case to the `list?` cases of parse to check if `(first input)` is an infix procedure. This should come after the case added above (it must come after to address inputs such as `(+ eqv? -)`). In this case, we should throw an error. 

The addition of these two cases to the parser will correctly handle inputs such as `(1 + 2)` and `(lt? 4 2)` in the new grammar. I don't think it is possible to handle more complicated inputs like: 
```{racket}
(let ([x eqv?])
  (+ x 1))

(let ([+ add1])
  (+ 1))
```
with only changes to parse. I think the best way to implement infix operations would be to parse prefix applications to `pre-app-exp`'s and infix applications to `inf-app-exp`'s. Then, interp would handle these cases differently. 

>[!note] 5

Changing parse.rkt would be sufficient, as long as interp.rkt only uses the provided accessors to access fields of parse tree structs. The new struct declarations would be 
```{racket}
(struct app-exp (args proc) #:transparent)
(struct ite-exp (else then cond) #:transparent)
(struct let-exp (body exps syms) #:transparent)
```
We need to change parse so that the fields are assigned correctly. For example, the current implementation of parsing if expressions: `(apply ite-exp (cdr input))` would make the `ite-exp` with fields bound: `(ite-exp {else = (second input)} {then = (third input)} {cond = (fourth input)})`. But the condition of an if expression is always `(second input)`. So we should change parsing if expressions to `(apply ite-exp (reverse (cdr input))`. Changes would also need to be made to parsing applications and lets. Since we assume that interp only accesses the fields by name instead of position, the actual structure of these structs is irrelevant to interp. 

Of course, changing interp would also be sufficient. Each time we access a field, we would use that accessor that corresponds to the position that the desired data used to occupy (ie replace each instance of `ite-exp-else` with `ite-exp-cond`). However, I think this solution is not as intuitive.