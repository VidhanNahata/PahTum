# PahTum
🎮 What Your Code Does

Game Setup

The program starts by asking the player what board size they want (default is 7×7, but it can be 3–25).

It then prints the rules and a scoring table that changes depending on the board size.

The player chooses Human vs Computer or Human vs Human.

If Human vs Computer → asks if the human wants to play first (as White) or second (as Black).

Board Representation

The board is shown as a grid:

. = empty cell

W = white stone

B = black stone

Rows and columns are numbered so the player can type coordinates.

Example of an empty 5×5:

   1 2 3 4 5
 1 . . . . .
 2 . . . . .
 3 . . . . .
 4 . . . . .
 5 . . . . .


Turns & Moves

White always plays first.

On each turn:

If it’s a human’s turn, they type a move (e.g., 3 4 → row 3, col 4).

If it’s the computer’s turn, the AI chooses a move automatically.

✅ The AI isn’t random — it tries to maximize immediate points from placing a stone, while avoiding giving the opponent a big scoring opportunity.
✅ It also slightly prefers moves closer to the center (to simulate strategy).

Scoring System

Only straight lines (horizontal & vertical) matter.

Runs of less than 3 don’t score anything.

Longer runs give rapidly increasing points, based on this formula:

Points(L, N) = round((L - 2)^(1 + N/10) * 2)


where L = run length, N = board size.

Example for N=7:

3 in a row → small points

4 in a row → much more

7 in a row → very high score

(This mimics the steep scoring growth in traditional Pah-Tum).

Game End

The game ends when the board is full (all cells filled).

Final scores for White and Black are calculated and displayed.

The program declares:

"White wins!" if White has more points

"Black wins!" if Black has more points

"Draw!" if tied
