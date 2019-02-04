## Making the Game Playable

This is cool, but it's not very interactive yet. We still have to evaluate two cells in order to get our result. It would be better if we had a button which prints the fruit selection and the result every time we press it.

We want a button which selects three random pieces of fruit, and runs our Which function to display a result.


--- task ---

Put your Which statement and your roll variable into a button.

Use a `;` to separate commands inside the button.

![Basic Roll Agian Button](images/BasicButton.png)

--- /task ---

You might notice that every time you press the button, the new output appears underneath the old output. It would be better to replace the old output with the new output each time you press the button.

We can do this using `Dynamic`. `Dynamic` displays the updated value, so each time we reevaluate the code by pressing the button, `Dynamic` will update to the new value.

--- task ---
Use `Dynamic` to create a button. 


```
roll = RandomChoice[fruits, 3];
result = Text["Click Roll Again to Start"];
Button["Roll Again",
 roll = RandomChoice[fruits, 3];
 result =
  Which[
   Max[Counts[roll]] == 3, Text[ "Winner!"],
   Max[Counts[roll]] == 2, Text["So Close!"] ,
   Max[Counts[roll]] == 1, Text["Loser!"]]]
Dynamic[Grid[{roll}, Frame -> All, FrameStyle -> Thick]]
Dynamic[result]
```
Delete your code for the non-Dynamic button you made in the previous step.
--- /task ---
