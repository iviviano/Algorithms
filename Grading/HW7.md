[KeneanKejela_hw7](https://github.com/orgs/24sp-oberlin-csci275/teams/keneankejela_hw7) 

honor code: yes

Stream operations notes:
- Nice job!

Gruning notes:
- There is an issue with the second condition of your `cond` in both `grune-a-b` and `grune`. Because you used `(not (equal? (stream-rest s) empty-stream))` instead of `(not (empty-stream? (stream-rest s)))`, you sometimes take `(stream-first empty-stream)` in the body of that case. This causes an error for inputs like `(grune-a-b '(a))`. Note that it works correctly for `(grune-a-b (stream 'a))`. However, lists are also valid streams. (**-2 points**)

Rockstar notes:
- Excellent tests and descriptions!

Mystery notes:
- Nice job!

## Points
```
Baseline:               5/5
Problem  1:             10/10
Problem  2:             10/10
Problem  3:             9/10
Problem  4:             9/10
Rockstar:               25/25
Mystery:                30/30
TOTAL:                  98/100
```

Great job!

[Maxann_hw7](https://github.com/orgs/24sp-oberlin-csci275/teams/maxann_hw7)

---

honor code: no!!

Stream operations notes:
- Nice job!

Gruning notes:
- `grune` and `grune-a-b` are missing. (**-10 points**)
- There is no test suite for `grune`. (**-5 points**)

Rockstar notes:
- Missing. (**-25 points)

Mystery notes:
- Missing. (**-30 points**)

## Points
```
Baseline:               5/5
Problem  1:             10/10
Problem  2:             10/10
Problem  3:             5/10
Problem  4:             0/10
Rockstar:               0/25
Mystery:                0/30
TOTAL:                  30/100
```

It looks like you may have missed a commit. If this is a Github issue, please talk to @mollyfeldman. Also, make sure to sign the Honor Code when you commit.


---

Stream operations notes:
- Nice job!

Gruning notes:
- Nice use of a `letrec` for `grune`!

Rockstar notes:
- Description does not address the direction of the fold. (**-2 points**)

Mystery notes:
- Description states that each function of the input list should accept one argument, but doesn't relate the input and output types of consecutive functions. (**-2 points**)
- Description does not address the direction of the fold. (**-3 points**)
- No test that mixes input and output types of the functions in `lst`. (**-2 points**)

## Points
```
Baseline:               5/5
Problem  1:             10/10
Problem  2:             10/10
Problem  3:             10/10
Problem  4:             10/10
Rockstar:               23/25
Mystery:                23/30
TOTAL:                  91/100
```

Nice job! Sorry for all of the confusion with the commits and file location issues. Your grade should be correct now.

[meltzer-hw7](https://github.com/orgs/24sp-oberlin-csci275/teams/meltzer-hw7)  
honor code: yes

Stream operations notes:
- Nice job!

Gruning notes:
- You should not always look at the first to elements of the input stream. First, you should check if `(stream-first s)` is `'a`. If it is, you should look at the second element. Your output for the keyboard stream was 
```
> (output-stream ((grune 'x 'y) (keyboard-stream))) 
? a
? b
a
? c
b
? d
c
? x
d
? y
x
? a
y
? b
a
? x
b
? x
y
? x
? x
y
? a
? b
a
b
? <click eof>
```
but it should have been:
```
> (output-stream ((grune 'x 'y) (keyboard-stream))) 
? a 
a 
? b 
b 
? c 
c 
? d 
d 
? x 
? y 
x 
y 
? a 
a 
? b 
b 
? x 
? x 
y 
? x 
? x 
y 
? a 
a 
? b 
b 
? <click eof> 
```
This is (**-2 points**)

Rockstar notes:
- Rockstar does not add non-numbers, since `positive?` throws a contract violation when called on a non-number. (**-1 points**)
- You did not address the order of the fold. (**-2 points**)
- No test considers an input list with a 0. (**-3 points**)

Mystery notes:
- Description does not address the order of the fold. (**-3 points**)
- Description does not address the required types of the functions in the input list. (**-3 points**)
- Description does not address that the result of calling `val` on `acc` is what is returned by the combine lambda. (**-1 points**)
- Note that this is similar to the Racket built in function `compose` (https://docs.racket-lang.org/reference/procedures.html#%28def._%28%28lib._racket%2Fprivate%2Flist..rkt%29._compose%29%29) except that is does `((apply compose lst) 0)` for the input `lst`.
- No test that mixes input and output types of the functions in `lst`. (**-2 points**)

## Points
```
Baseline:               5/5
Problem  1:             10/10
Problem  2:             10/10
Problem  3:             9/10
Problem  4:             9/10
Rockstar:               19/25
Mystery:                21/30
TOTAL:                  83/100
```

Nice job!

[robert-leah-7](https://github.com/orgs/24sp-oberlin-csci275/teams/robert-leah-7) [Note: group!]  
honor code: yes

Rockstar notes:
- You are missing a test case that considers when the input list contains a 0. (**-3 points**)
- Note that it's not really necessary to test error throwing when it isn't something you explicitly implemented to handle invalid inputs. 

Mystery notes:
- Description does not address the required types of the functions in the input list. (**-3 points**)
- No test that mixes input and output types of the functions in `lst`. (**-2 points**)

## Points
```
Baseline:               5/5
Problem  1:             10/10
Problem  2:             10/10
Problem  3:             10/10
Problem  4:             10/10
Rockstar:               22/25
Mystery:                20/30
TOTAL:                  92/100
```

Nice job!

[Sampad_Khalid_hw7](https://github.com/orgs/24sp-oberlin-csci275/teams/sampad_khalid_hw7) [Note: group!]  
honor code: yes

Gruning notes:
- Your implementation of `grune` fails on all finite streams, since you always check the first two elements of the stream. This is an example of when you have to be careful about using `let` to bind several identifiers. (**-4 points**)

Rockstar notes:
- Nice job!

Mystery notes:
- Good description, but you did not address the required types of the functions in the input list. (**-3 points**)
- No test that mixes input and output types of the functions in `lst`. (**-2 points**)

## Points
```
Baseline:               5/5
Problem  1:             10/10
Problem  2:             10/10
Problem  3:             8/10
Problem  4:             8/10
Rockstar:               25/25
Mystery:                25/30
TOTAL:                  91/100
```

Great job!

[The-Bayan-Players-Lab7](https://github.com/orgs/24sp-oberlin-csci275/teams/the-bayan-players-lab7) [Note: group! Ben R & Anya]  
honor code: 

Stream operations notes:
- You have two redundant tests for `stream-remove-all`. You should have tested the cases where `x` is not in `s` and where `s` in an infinite stream. (**-1 points**)
- Again, you have insufficient unique tests for `stream-replace`. (**-1 points**)
- Note that you don't need to use `stream-take` for finite streams. `stream->list` will terminate and give you the whole stream as a list.

Gruning notes:
- Your `grune` functions fail on finite streams that end in an odd number of `a`'s. Your `grune-helper` doesn't check if `(stream-rest s)` is empty before checking `(stream-first (stream-rest s))`. This causes `(grune-a-b '(a))` to throw an error. (**-2 points**)
- Again, you have insufficient unique tests for `grune-a-b`. (**-1 points**)

Rockstar notes:
- Description does not address the order of the fold. (**-2 points**)
- Good tests!

Mystery notes:
- Description does not address the order of the fold. (**-3 points**)
- Description does not address the required types of the functions in the input list. (**-3 points**)
- Note that this is similar to the Racket built in function `compose` (https://docs.racket-lang.org/reference/procedures.html#%28def._%28%28lib._racket%2Fprivate%2Flist..rkt%29._compose%29%29) except that is does `((apply compose lst) 0)` for the input `lst`.

## Points
```
Baseline:               5/5
Problem  1:             9/10
Problem  2:             9/10
Problem  3:             8/10
Problem  4:             9/10
Rockstar:               23/25
Mystery:                24/30
TOTAL:                  87/100
```

Nice job!

[William]
honor code: yes

Rockstar notes:
- Description does not address the order of the fold. (**-2 points**)
- No test that considers when the input list contains a 0. (**-3 points**)
- No test for the empty input list. (**-5 points**)

Mystery notes:
- Description does not explain the composition of the input functions. Note that this is similar to the Racket built in function `compose` (https://docs.racket-lang.org/reference/procedures.html#%28def._%28%28lib._racket%2Fprivate%2Flist..rkt%29._compose%29%29) except that is does `((apply compose lst) 0)` for the input `lst`. (**-1 points**)
- Description does not address the required types of the functions in the input list. (**-3 points**)
- No test that mixes input and output types of the functions in `lst`. (**-2 points**) 
- Not enough additional tests. (**-5 points**)

## Points
```
Baseline:               5/5
Problem  1:             10/10
Problem  2:             10/10
Problem  3:             10/10
Problem  4:             10/10
Rockstar:               15/25
Mystery:                19/30
TOTAL:                  79/100
```

Nice job!





>[!question]
>What if their tests/test descriptions address something that their description misses?







Rockstar notes:
- No test that considers when the input list contains a 0. (**-3 points**)

Mystery notes:
- Description does not address the composition of the procedures: that the output of each is the input to the next. (**-1 points**)
- Description does not address the required types of the functions in the input list. (**-3 points**)
- Nice tests!

## Points
```
Baseline:               5/5
Problem  1:             10/10
Problem  2:             10/10
Problem  3:             10/10
Problem  4:             10/10
Rockstar:               22/25
Mystery:                26/30
TOTAL:                  93/100
```

Great job!
