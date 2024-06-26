# HW 7 Rubric (Spring 2024)

There are three parts to grade below. Unlike last semester, Summary Problem submissions are _not_ part of this assignment. 
Therefore, if you graded HW7 before, please make sure to **review and ask questions** about any noted changes.  

## Heads Up on Streams
There are a lot of folks who have *almost* a working implementation for Questions 3 & 4, but do not handle one final `a` correctly (they delay it so it does not print properly). This is a subtle, but important, case to handle.

## Grading Part 1 (20 points)
For each question, if implementation is correct, give 5 points; if there are 3 tests, give 5 points.

## Grading Part 2 (20 points)
There are tests in `grading.rkt` for this, but you'll need to **test by hand** as well because the results should be printed at the appropriate times. 

Try running the examples below in DrRacket. The output should match exactly. In particular, after entering the first `a`, there should be no output. After entering the first `b`, it should produce both `a` and `b`.

**REMOVE 2 POINTS IF**: Some students might implement the above behavior by always checking the next two values in
the stream. This is incorrect.

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


```
> (output-stream ((grune 'c 'd) ((grune 'b 'c) ((grune 'a 'b) (keyboard-stream)))))
? a 
? b 
a 
? c 
b 
? d 
c 
d 
? e 
e 
? f 
f 
? g 
g 
? a
? a 
? a 
? a 
? a 
? a 
? a 
? a 
d 
? a 
? a 
? a 
? a 
? x 
c 
x 
? y 
y 
? z 
z 
? x 
x 
? y 
y 
? z 
z 
? <click eof> 
```

For problem 3, give 5 points if the implementation works correctly and 5 points if there are at least 3 tests. (10 points)

For problem 4, give 5 points if the implementation works correctly and 5 points if there are at least 3 tests. (10 points)

## Grading Part 3

This section is new for this semester, so please ask questions about grading it if you have any. 

### Rockstar

They should earn 5 points for a correct description of what the function does. 
+ 3 points for a description
+ 2 points for addressing the order of the fold (l nor r)

The should earn 5 points for describing what the existing tests are doing (be generous for this one).

They should earn 15 points for adding additional tests
+ 7 points for writing additional tests, not thinking the test suite is sufficient 
+ 5 points for testing the empty list 
+ 3 points for a test that considers 0

### Mystery

They should earn 10 points for a correct description of what the function does. 
+ One point for a description
+ 3 points for a description that correctly addresses the fact val is being called on acc
+ 3 points for addressing the order of the fold (r not l)
+ 3 points for talking about mapping input and output types (i.e. input type of one needs to be output type of another)

They should earn 5 points for describing what the existing tests are doing (be generous for this one).

They should earn 15 points for adding additional tests 
+ 5 points for writing additional tests, not thinking the test suite is sufficient
+ 3 points for a test that contains a list of operations longer than length 1
+ 2 points for a test that mixes input/output types
+ 5 points for some other additional test that distinguishes itself (an example is a bespoke lambda, rather than a built in primitive)

## Points
```
Baseline:               /5
Problem  1:             /10
Problem  2:             /10
Problem  3:             /10
Problem  4:             /10
Rockstar:               /25
Mystery:                /30
TOTAL:                  /100
```