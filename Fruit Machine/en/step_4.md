## Building a Game

There are three possible outcomes for the game:
+ 3 fruit the same: the player wins
+ 2 fruit the same: the player is close
+ All fruits different: the player loses

We can find out how many of the randomly selected fruits are the same by finding the `Count` of each fruit. We can then use `Max` to find out the largest number of duplicates.

![Max Counts 2](images/MaxCounts2.png)

So now we have a set of rules.

+ If `Max` is 3, then we win
+ If `Max` is 2, then nothing happens
+ If `Max` is 1, then we lose.

We can use these `Max` counts to build a game.
+ If all three are the same, print 'Winner!'
+ If two are the same, print 'So Close!'
+ If all three are different, print 'Loser!'

The best way to check if one of multiple conditions is true, and return a specific output if the condition is true, is a `Which` statement.

A `Which` statement takes an input (the list of randomly chosen fruits), and checks each condition in order. If the first answer is `True`, it returns the output for that rule. If the second one is `True`, it returns the output for that condition, and so on, until there are no more conditions to check.

![Which Statement](images/Which.png)

--- task ---

Combine the random fruit picker and the game rules into a single function using a `Which` statement.

```
roll = RandomChoice[fruits, 3]
Which[
 Max[Counts[roll]] == 3, Print["Winner!"],
 Max[Counts[roll]] == 2, Print["So Close!"],
 Max[Counts[roll]] == 1, Print["Loser!"]]
```
Delete any previous code featuring `RandomChoice[fruits, 3]`
--- /task ---
