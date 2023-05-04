Download Link: https://assignmentchef.com/product/solved-csci-1133-assignment-5-detecting-wizards
<br>
Problem A. <strong>Detecting Wizards</strong>:

It is well documented that it is physically impossible for a college student to have enough time to get good grades, have a social life, and get enough sleep: at most two of the three goals can be achieved.  Therefore, any student that does appear to have all three things must be using dark magic.




Write a function wizards(grades, life, sleep) that takes in three lists of student names (strings), where grades represents students who get good grades, life represents students who have a social life, and sleep represents students who get enough sleep.  You can assume that all lists are in alphabetical order.  The function must return a list of all students who are clearly wizards (because they appear in all three lists).




However, there is a complication.  One of the wizards in this course really doesn’t like how easy the Python in keyword makes everything, so they performed a magic ritual that will turn anyone using the in keyword for this problem into a newt.  Therefore, <strong>you must solve this problem without using </strong><strong>in</strong>.




<strong>Hints: </strong>

<ul>

 <li>You may assume that no name appears in a single list multiple times.</li>

 <li>There are two basic approaches to this: a complicated, but fast (in terms of runtime) method that uses only one loop by taking advantage of the fact that the lists must be in alphabetical order, and a simple, but slow method that uses three nested while loops. Either strategy is fine.</li>

 <li>If you’re going with the complicated, efficient strategy, remember that you can compare strings alphabetically with operators like &gt; and &lt;=.</li>

 <li>If you’re going with the triple while loop strategy, be careful about where you increment your loop variables inside the nested loop.</li>

</ul>




<strong>Constraints</strong>:

<ul>

 <li>Do not import/use any Python modules other than random (used for problem B).</li>

 <li>For this problem, you are not allowed to use the in keyword (this means no for loops).</li>

 <li>Don’t use the input() function, as this will break our grading scripts.</li>

 <li>You are not allowed to use the Python set intersection, or anything similar, to trivialize the problem (don’t worry if you don’t know what that is at this point).</li>

 <li>Your submission should have no code outside of function definitions (comments are fine)</li>

</ul>

<strong>Examples</strong>:

&gt;&gt;&gt; wizards([‘Harry’, ‘Hermione’], [‘Harry’, ‘Ron’], [‘Hermione’,

‘Ron’])

[]




&gt;&gt;&gt; wizards([‘Aragorn’, ‘Frodo’, ‘Gandalf’], [‘Aragorn’, ‘Gandalf’,

‘Gimli’, ‘Pippin’], [‘Gandalf’, ‘Pippin’])

[‘Gandalf’]




&gt;&gt;&gt; wizards([‘Zelda’], [], [‘Ganondorf’, ‘Link’, ‘Zelda’])

[]




&gt;&gt;&gt; wizards([‘Mary’, ‘Spock’, ‘Sue’], [‘Kirk’, ‘Mary’, ‘Sue’],

[‘Mary’, ‘Sue’])

[‘Mary’, ‘Sue’]

Problem B. (30<em> points</em>)  <strong>Playing Tic-Tac-Toe Randomly</strong>

<u><a href="https://en.wikipedia.org/wiki/Tic-tac-toe">Tic</a><a href="https://en.wikipedia.org/wiki/Tic-tac-toe">–</a><a href="https://en.wikipedia.org/wiki/Tic-tac-toe">Tac</a><a href="https://en.wikipedia.org/wiki/Tic-tac-toe">–</a><a href="https://en.wikipedia.org/wiki/Tic-tac-toe">Toe</a></u> is a very simple game involving a 3×3 grid, where players take turns, attempting to place 3 of their marks in a row, either vertically, horizontally, or diagonally (see the link for details if you are unclear on the rules).  In this problem, you will be creating a program that plays tic-tac-toe by choosing an open spot at random, in order to determine how often ‘X’ wins, how often ‘O’ wins, and how often the game results in a draw when both players use that strategy.




We’ll be representing the board as a single list of 9 one-character strings in this problem.  The first 3 elements of the list represent the top row of the board, the second 3 elements represent the middle row, and the last 3 elements represent the bottom row.  Each string can either be ‘X’, ‘O’, or ‘-‘ (which represents an empty space).  See the diagram below for an example of how to represent a tic-tac-toe board as a 9 element list.




[‘X’, ‘O’, ‘-‘, ‘-‘, ‘O’, ‘O’, ‘X’, ‘X’, ‘-‘]




To do this, you need to write four functions.  Be sure you match the names and arguments of the functions exactly to prevent grading issues.




open_slots(board) takes in a board list (formatted as specified above), and returns a list of the indexes which still contain a ‘-‘ (that is, the indexes of the open spots left).  Indexes here refer to standard list indexing in Python, so since board is a 9 element list, they should all be numbers between 0 and 8, inclusive.




winner(board) takes in a board list (formatted as specified above), and returns a single character string that describes whether a player has won the game.  In particular, it should return:

<ul>

 <li>‘X’, if X won the game (there are three X’s in a row, horizontally, vertically or diagonally)</li>

 <li>‘O’, if O won the game</li>

 <li>‘D’, if the game ended in a draw (all spots are filled but neither player won)</li>

 <li>‘-‘, if the game is not over (there is at least one empty spot and neither player won)</li>

</ul>

You can ignore the possibility of getting a board where both X and O have achieved three in a row, since this should not happen in a real game.




tic_tac_toe() takes in no arguments, and simulates a single game of tic-tac-toe, returning a one character string that signifies the winner (‘X’, ‘O’, or ‘D’ for a draw).  This simulation needs to follow the rules of tic-tac-toe: X and O alternate turns, starting with X; each player must choose an empty space on their turn; and the game ends as soon as someone wins or all spaces are filled.  When choosing a space, the player should act randomly, with an equal chance to pick any of the remaining open spaces. play_games(n) takes in one argument, an integer n representing the number of games to play.  It then calls tic_tac_toe n times, and prints out the total number of times X won, the number of times O won, and the number of times that a draw occurred.  This function does not return anything.  Be sure to match the print formatting shown in the examples below.




You may also write any number of additional helper functions you think are useful.




<strong>Hints: </strong>

<ul>

 <li>Consider writing a function that displays a board list in the more traditional 3×3 grid form: this could be very helpful for debugging purposes.</li>

 <li>(a == b == c == d) works as you would expect (True if all four values are equal, False otherwise), so long as you don’t separate any of the equality operations by parentheses.</li>

 <li>There are a LOT of different ways to write the winner function, and some are significantly more compact than others. Try to find an approach that’s a bit more clever than 17 if statements.</li>

 <li>choice is a function that picks a random element from a list: this may be useful for choosing the next move from a list of open slots.</li>

 <li>You should probably do a lot more tests of winner than the four provided below; this will make your life easier when you get to the later functions.</li>

</ul>




<strong>Constraints</strong>:

<ul>

 <li>Do not import/use any Python modules other than random.</li>

 <li>You may use any list method that is appropriate to solving this problem.</li>

 <li>You can also use the in keyword again: the wizard from problem A has been defeated.</li>

 <li>Don’t use the input() function, as this will break our grading scripts.</li>

 <li>Your submission should have no code outside of function definitions (comments are fine).</li>

</ul>




<strong>Examples</strong>:

&gt;&gt;&gt; open_slots([‘-‘, ‘-‘, ‘-‘, ‘-‘, ‘-‘, ‘-‘, ‘-‘, ‘-‘, ‘-‘]) [0, 1, 2, 3, 4, 5, 6, 7, 8]

&gt;&gt;&gt; open_slots([‘-‘, ‘X’, ‘O’, ‘O’, ‘X’, ‘-‘, ‘-‘, ‘X’, ‘O’]) [0, 5, 6]

&gt;&gt;&gt; open_slots([‘O’, ‘X’, ‘O’, ‘X’, ‘X’, ‘O’, ‘X’, ‘O’, ‘X’]) []

&gt;&gt;&gt; open_slots([‘X’, ‘X’, ‘O’, ‘-‘, ‘X’, ‘-‘, ‘X’, ‘O’, ‘O’])

[3, 5]




&gt;&gt;&gt; winner([‘X’, ‘X’, ‘O’, ‘O’, ‘X’, ‘X’, ‘O’, ‘X’, ‘O’])

‘X’

&gt;&gt;&gt; winner([‘X’, ‘-‘, ‘O’, ‘X’, ‘O’, ‘-‘, ‘O’, ‘-‘, ‘X’])

‘O’

&gt;&gt;&gt; winner([‘O’, ‘X’, ‘O’, ‘X’, ‘X’, ‘O’, ‘X’, ‘O’, ‘X’])

‘D’

&gt;&gt;&gt; winner([‘X’, ‘X’, ‘O’, ‘-‘, ‘X’, ‘-‘, ‘X’, ‘O’, ‘O’])

‘-‘




(Note: the output of tic_tac_toe and play_games is random, so your results will not match the ones below.  However, probability says that you should see X win roughly 58% of the time, O win about 29% of the time, and a draw about 13% of the time: if you’re not getting close to that when running a large number of games then you may want to look for mistakes in your code).




&gt;&gt;&gt; tic_tac_toe()

‘X’

&gt;&gt;&gt; tic_tac_toe() ‘O’

&gt;&gt;&gt; tic_tac_toe()

‘D’




&gt;&gt;&gt; play_games(1)

X wins: 1

O wins: 0

Draws: 0




&gt;&gt;&gt; play_games(100)

X wins: 61

O wins: 30

Draws: 9




&gt;&gt;&gt; play_games(10000)

X wins: 5917

O wins: 2798