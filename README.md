# BacktrackingAlgo

SOURCE: https://dev.to/aspittel/how-i-finally-wrote-a-sudoku-solver-177g




The Algorithm
One algorithm to solve Sudoku puzzles is the backtracking algorithm. Essentially, you keep trying numbers in empty spots until there aren't any that are possible, then you backtrack and try different numbers in the previous slots.

Awesome visualization from Wikipedia

Shoutout to Wikipedia for the awesome visualization!
The first thing that I did was continue my "easy" Sudoku solver's approach of finding the possible values for each square based on which values were already in that square's row, column, and box. I stored all of these values in a list so that I could quickly refer to them while backtracking or finding which value to use in that square.

Next, I needed to implement the forward moving and backtracking of putting items in each space. I put markers on each non-given space (so the ones that were zeros when the game started) so that those spaces would be included in the backtracking and given spots wouldn't be. I then iterated through those un-solved spots. I would put the first item of the possible value list in that spot and then move to the next unsolved spot. I would then put the first possible value of that spot in its place. If it conflicted with the value of the previous slot, I would then move to the second item in the list of possible values and then move to the next slot. That process would continue until there was no possible move for a given spot -- i.e. the end of the possible value list was reached and none of the values worked in that row, column, or box. Then, the backtracking algorithm kicked in.

Within the backtracking implementation, the code would move back to the last spot that was filled in and move to the next possible value and then start moving forward again. If the last of the possible values was reached at that spot as well, the backtracking algorithm would keep moving backwards until there was a spot that could be incremented.

Once the end of the puzzle was reached with correct values in each square, the puzzle was solved!
