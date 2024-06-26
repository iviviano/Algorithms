[abby_tejera_hw7](https://github.com/orgs/24sp-oberlin-csci275/teams/abby_tejera_hw7) 
**Honor Code:** Yes
**Part 1 Notes:** 
- Great implementation and tests! 

**Part 2 Notes:** 
- Your implementations for `grune` and `grune-a-b` work as intended, so great job! It's not usually recommended to nest `define` statements together. You might consider defining helpers separately or using `letrec` instead!

**Part 3 Notes:** 
`rockstar` :
- You did not mention the order of the fold in your description, so this is **-2pts**. 
- Your additional tests were great!
`mystery`: 
- You were close in your description of how `mystery` works, but you did not mention anything about mapping input and output types (i.e. input type of one needs to be output type of another), so this is **-3 pts**. `mystery` has the same functionality as `((apply compose lst) 0)`.
- Your additional test with multiple procedures was great!
- You should have added a test with different input and output types, as that is what makes `mystery` different from other functions we've seen. This is **-2 pts**. 
- You should have also added another test to encompass more cases. This could look like a test with a non-primitive procedure in `lst` by defining something with `lambda`. **-5pts**. 

```
Baseline:               5/5
Problem  1:             10/10
Problem  2:             10/10
Problem  3:             10/10
Problem  4:             10/10
Rockstar:               23/25
Mystery:                20/30
TOTAL:                  88/100
```


[Al Fessler](https://github.com/24sp-oberlin-csci275/homework-7-al-hw7)
**Honor Code:** Yes
**Part 1 Notes:** 
- Great job on tests and implementation of `stream-remove-all` and `stream-replace`!
**Part 2 Notes:** 
- You implement `grune` and `grune-a-b` by always checking the first and second elements of the stream before ever returning anything. This is because you have an `and` statement that requires you to look at the second element before moving on, even when the first statement doesn't match what you are looking for. ==This is **-2**. ==
**Part 3 Notes:** 
`rockstar`:
- You described the procedure's end result, but did not mention the order of the `fold`, so this is **-2**.
- Great extra tests, but an important one to add was an instance of `0` in the list. This is **-3**.
`mystery`:
- You were close in your description of how `mystery` works, but you did not mention anything about mapping input and output types (i.e. input type of one needs to be output type of another), so this is **-3 pts**. `mystery` has the same functionality as `((apply compose lst) 0)`.
- Your additional test with multiple procedures was great!
- You should have added a test with different input and output types, as that is what makes `mystery` different from other functions we've seen. This is **-2 pts**. 

```
Baseline:               5/5
Problem  1:             10/10
Problem  2:             10/10
Problem  3:             9/10
Problem  4:             9/10
Rockstar:               20/25
Mystery:                25/30
TOTAL:                  /100
```

[alec7](https://github.com/orgs/24sp-oberlin-csci275/teams/alec7)
**Honor Code:** Yes
**Part 1 Notes:** 
- Great implementations and tests!
**Part 2 Notes:** 
- for `grune` and `grune-a-b`, you use `stream-length` but we don't know if the streams will be infinite, so this means your implementation doesn't return anything until we end the stream (or click EOF in keyboard stream). It should return things as it goes. This is **-5** for `grune`, and **-5** for `grune-a-b`. 
- ==Do I take the full 5 points even if it works for non-infinite streams? At least 2 points off bc they always check the first two elts ==
**Part 3 Notes:** 
`rockstar`:
- You described the procedure's end result, but did not mention the order of the `fold`, so this is **-2**.
- Great extra tests, but an important one to add was an instance of `0` in the list. This is **-3**.
`mystery`: 
- You were close in your description of how `mystery` works, but you did not mention anything about mapping input and output types (i.e. input type of one needs to be output type of another), so this is **-3 pts**. `mystery` has the same functionality as `((apply compose lst) 0)`.
- Great job adding tests with multiple procedures and different types within the `lst`!
- You should have also added another test to encompass more cases. This could look like a test with a non-primitive procedure in `lst` by defining something with `lambda`. **-5pts**. 

```
Baseline:               5/5
Problem  1:             10/10
Problem  2:             10/10
Problem  3:             5/10
Problem  4:             5/10
Rockstar:               20/25
Mystery:                22/30
TOTAL:                  /100
```

[amanda_hw7](https://github.com/orgs/24sp-oberlin-csci275/teams/amanda_hw7)  
**Honor Code:** Yes
**Part 1 Notes:** 
- your implementations of `stream-remove-all` and `stream-replace` actually run forever on finite streams, but work for infinite streams. This is because you call `(stream-helper s)` instead of returning the `empty-stream` on your base case. ==This is **-5** for `stream-remove-all` and `stream-replace`. ==
**Part 2 Notes:** 
- Your implementations of `grune-a-b` and `grune` fail when using the `keyboard-stream` or other infinite streams because you rely on the method `length` (which also gives you a contract violation because it's looking for a list, not a stream). We don't know if the streams will be infinite, so this means your implementation doesn't return anything until we end the stream (or click EOF in keyboard stream). It should return things as it goes. This is **-5** for `grune`, and **-5** for `grune-a-b`. 
- ==Do I take the full 5 points even if it works for non-infinite streams? At least 2 points off bc they always check the first two elts ==
**Part 3 Notes:** 
- excellent summary for `rockstar`!
- Unfortunately, `rockstar` could use a few more tests, such a test that includes `0` in the list, and a test for the empty list. This is **-15**. 
- For `mystery`, there is nothing in the definition that specifies `val` must be a simple arithmetic operation. What makes `mystery` kind of cool is that you can actually give it a list of procedures that return different types than they were given, as long as the one before takes an input of the following function's output (since it goes right to left). As long as `0` is a valid input to the very last procedure in the `lst`, the rest of the procedures do not necessarily have to operate on integers. You described other parts of `mystery`, like the `acc` being `0` at first, and `val` being applied to `acc` every time, but because you did not include the ability for the procedures to act on different types, this is **-3**. 
- `mystery` could use a few more tests than the one you provided, though this one was a good addition because you handled multiple operations in the list. Some more you could have added were tests that started and ended with different input types, and tests with a non-primitive procedure in `lst` by defining something with `lambda`. These missing tests are **-7**. 

```
Baseline:               /5
Problem  1:             /10
Problem  2:             /10
Problem  3:             /10
Problem  4:             /10
Rockstar:               10/25
Mystery:                20/30
TOTAL:                  /100
```

[Atticus-Shane-hw7](https://github.com/orgs/24sp-oberlin-csci275/teams/atticus-shane-hw7) [Note: group!]  
**Honor Code:** Yes
**Part 1 Notes:** 
- great implementations of `stream-remove-all` and `stream-replace`!
**Part 2 Notes:** 
- Your implementation of `grune` and `grune-a-b` check `[(stream-empty? (stream-rest keyboard-stream))...]` before checking `[(equal? x (stream-first keyboard-stream))...]`. This means that it is always checking to see if there is a next thing, so when given something like the following, it waits to return `b` even though it should just return it right away: 
```
> (output-stream (grune-a-b (keyboard-stream)))
? a
? a
b       <- this is good, it should wait when given a
? b
? b     <- this should have returned b before asking for next symbol
b
? <click-eof>
b
```
==This is **-2** for both `grune` and `grune-a-b`. ==

**Part 3 Notes:** 
- Great description and extra tests for `rockstar`! In particular, great job adding a test with `0` in the list and a test with the `empty` list. 
- For `mystery`, it is important to note in the description that a function must have an input type of the following function's output type. This is **-3**.
- Great additional tests for `mystery` 

```
Baseline:               5/5
Problem  1:             9/10
Problem  2:             10/10
Problem  3:             10/10
Problem  4:             10/10
Rockstar:               19/25
Mystery:                20/30
TOTAL:                  83/100
```
[BGalbraith_HW7](https://github.com/orgs/24sp-oberlin-csci275/teams/bgalbraith_hw7)  
**Honor Code:** Yes
**Part 1 Notes:** 
- Your test suite for `stream-remove-all` does not contain three unique tests, since you test `(stream-remove-all 'x test-stream)` twice. Even though you take a different number of elements in the two tests, the "empty" test is just a subset of the "remove element" test. To test the empty stream input, you should look at what is returned by `(stream->list (stream-remove-all 'x empty-stream))`. This is **-1**.

**Part 2 Notes:** 
- Excellent tests for `grune`!

**Part 3 Notes:** 
- Rockstar description does not explain that the negative numbers in the list are added. This is **-3**.
- Rockstar test suite is missing a test that considers an input list with a 0. This is **-3**.
- For `mystery`, it is important to note in the description that a function must have an input type of the following function's output type. This is **-3**.
- Also, note that the list of functions is *composed*: the output of the rightmost function applied on 0 is fed as input to the next function moving left. This is **-2**.
- Finally, for the `mystery` description, you did not address the order of the `fold`. This is **-3**.
- You should have added a test with different input and output types, as that is what makes `mystery` different from other functions we've seen. This is **-2 pts**. 

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


Danny Perlow (EXTENSION UNTIL 4/20)
**Honor Code:**
**Part 1 Notes:** 

**Part 2 Notes:** 

**Part 3 Notes:** 

```
Baseline:               5/5
Problem  1:             10/10
Problem  2:             9/10
Problem  3:             8/10
Problem  4:             8/10
Rockstar:               22/25
Mystery:                26/30
TOTAL:                  88/100
```
[daniel_hw7](https://github.com/orgs/24sp-oberlin-csci275/teams/daniel_hw7)
**Honor Code:** Yes
**Part 1 Notes:** 
- Your `stream-replace` procedure does not terminate when you replace an item with itself. This is because in your second case, you `cons` `y` with `(stream-rest s)` and then call `stream-replace` recursively. So, if `(equal? x y)` is `#t` and at some point `(equal? x (stream-first s))` is `#t`, you keep recursively calling `stream-replace` on the same stream. An example of where this occurs is `(stream-replace 'x 'x test-stream)`. This is **-1**.

**Part 2 Notes:** 
- Your implementations of `grune` and `grune-a-b` do not work on infinite streams. This is because you used `stream-length`. This procedure works by recursively iterating over its input stream (without forcing any evaluation) until the input is empty. It counts the number of recursive calls, giving the length. However, for an infinite input stream, it will not terminate. This is **-2** for both procedures.

**Part 3 Notes:** 
- Rockstar test suite is missing a test that considers an input list with a 0. This is **-3**.
- For `mystery`, it is important to note in the description that a function must have an input type of the following function's output type. This is **-3**.
- Also, note that the list of functions is *composed*: the output of the rightmost function applied on 0 is fed as input to the next function moving left. This is **-1**.
- Nice test suite for `mystery`!


GRADING MEETING NOTES: 
- Rockstar: Don't take off points for not mentioning fold or order. 
- For a half-working implementation, give 3 points (like only works for infinite, or only works for finite). **-2**. 