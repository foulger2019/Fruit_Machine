## Finishing Touches

Great! We now have two buttons. The first button rolls again, tells us if we won or lost, and updates the score. The second button starts the game again, resetting the scores back to 100.

Let's design the interface so that the two buttons are next to each other.

--- task ---

Put the buttons into a list, separated by a `,`, and then put the list inside the `Row` function. `Row` takes a list, `{}`, of items, in this case buttons, and puts all of the items on one line.


```
roll = RandomChoice[fruits, 3];
result = Text["Click Roll Again to Start"];
score = 100;
Row[{
Button["Roll Again",
roll = RandomChoice[fruits, 3];
result =
Which[
Max[Counts[roll]] == 3, score += 10; Text[ "Winner!"],
 Max[Counts[roll]] == 2, Text[ "So Close!"],
 Max[Counts[roll]] == 1, score -= 10; Text[ "Loser!"]]
 ],
 Button["Start Again", score = 100]
 }]
Dynamic[Grid[{roll}, Frame -> All, FrameStyle -> Thick]]
Dynamic[result]
Dynamic[score]
```
--- /task ---

