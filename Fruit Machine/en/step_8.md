## Challenge: End the Game

How could you make the game end when the player loses all their points? Try putting an extra test in the `Which` statement.

---hints---

--- hint ---
If the score is less than 0, then set the score to 100, and print `Text` which tells the user they are out of points.

--- /hint---

--- hint ---

```
score < 0, score = 100; Text["Out of Points!" Start again!]
```
--- /hint---

--- hint ---
```
Which[
 score < 0, score = 100; Text["Out of Points! Start again!"],
 Max[Counts[roll]] == 3, score += 10; Text[ "Winner!"],
 Max[Counts[roll]] == 2, Text[ "So Close!"],
 Max[Counts[roll]] == 1, score -= 10; Text[ "Loser!"]
 ]
 ```
--- /hint---

---/hints---
