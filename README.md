# Game Play
Ultimate Tic-Tac-Toe is a variant of the classic Tic-Tac-Toe game. It is played on a larger 9x9 grid which consists of nine 3x3 grids. The objective of the game is to win each 3x3 grid, and ultimately, the entire game by winning the most 3x3 grids.

In this game, players take turns placing their symbol (either X or O) in a vacant square of the 3x3 grid. However, the twist is that the square where a player places their symbol determines the 3x3 grid where their opponent must play on their next turn. If a player wins a 3x3 grid, they gain control of that grid, and their symbol is displayed in the corresponding square of the larger 9x9 grid. The game continues until one player wins three 3x3 grids in a row, or until all the squares have been filled, resulting in a draw.

Ultimate Tic-Tac-Toe is a more complex version of Tic-Tac-Toe that requires strategic thinking and planning ahead. It also introduces an element of control over the opponent's moves, as the placement of a player's symbol determines the next playable grid for their opponent. Overall, Ultimate Tic-Tac-Toe is an engaging and challenging game that provides a new twist on a classic game.

# Preview

[![thumbnail](./UIpreview)](https://user-images.githubusercontent.com/67221507/235636375-ae5099f8-9d22-4b33-9b81-8cf77bacbf4b.mp4)

# Game Logics (only for those who want to understand the code):
The startGame() function initializes several global variables, including plot, bigsquareConcluded, numOfBSConcluded, previousBSID, and movesPlayed. It also sets the Player variable to "X".

    The function selects all of the tile elements and big square elements in the game board and assigns them to the tiles and BIGsquares variables respectively.

    It then sets the movesPlayed variable to 0 and hides the conclusion display.

    The plot variable is initialized as an empty array with 81 null values, which is used to store the state of the game board.

    The bigsquareConcluded variable is initialized as an empty array with 9 null values, which is used to store the state of each big square.

    The function then loops through all the BIGsquares and sets their background color to grey.

    Finally, the function loops through all the tiles, clears their innerText, and sets their backgroundColor to #ffd304. It also adds event listeners for click, mouseover, and mouseout events on each tile.

    Overall, startGame() sets up the initial state of the game board and prepares it for the start of the game.

II. Updating Moves

    Describes how the function updates the movesPlayed variable
    Extracts the ID of the clicked tile and saves the move played by the human player in the plot variable

III. Adding X or O and Changing Background Color

    Selects the clicked tile and adds the corresponding X or O depending on the turn of the human player
    Changes the background color of the tile based on the player's turn

IV. Checking Small Square for Win or Tie

    Calls the checkWinTiles() and checkTieTiles() functions to check if the human player has won the small square or if it is a tie
    Stores their return values in the temp1 variable
    If temp1 has a non-null value, stores the conclusion in the bigsquareConcluded variable and highlights the corresponding big square with the appropriate color

V. Checking Game for Win or Tie

    Calls the checkWinBS() and checkTieBS() functions to check if the human player has won the game or if it is a tie
    Stores their return values in the temp1 variable
    If temp1 has a non-null value, calls the gameOver() function to end the game

VI. Preparing for Bot's Move

    Deactivates all the tiles and prepares for the bot's move
    Calls the botMove() function to get the ID of the tile where the bot should make its move

VII. Adding Bot's X or O and Changing Background Color

    Selects the corresponding tile and adds the bot's X or O to it
    Changes the background color of the tile based on the bot's turn

VIII. Checking Small Square for Win or Tie (Bot's Move)

    Uses the same approach as before to check if the bot has won the small square or if it is a tie
    If the bot has won a small square or the game, calls gameOver() to end the game

IX. Activating Tiles and Switching Turn

    Activates the tiles in the square where the bot has played
    Switches the turn back to the human player.

deactivateAll() function removes event listeners and changes the cursor and background color of all tiles. It also checks if any of the 9 small squares (called bigsquares) have been concluded, and if so, sets their color to white.

activate(tileID) function activates the tiles for the next move based on the move played. It first determines which bigsquare the move was made in, and then activates all empty tiles in that bigsquare by adding event listeners, changing cursor and background color. If the bigsquare has already been concluded, it calls the activateAll(BSindexID) function.

The botMove() function is called when it is the bot's turn to move. The function first checks if the number of moves played is greater than or equal to 100. If so, it returns the result of the minimax() function, which is not yet implemented. Otherwise, the function increments the movesPlayed variable and returns the result of the randomPlay() function.

The randomPlay() function is called when the bot decides to make a random move. If the square that was clicked is not yet concluded, the function generates an array of valid moves for that square and chooses a random move from that array. It then updates the plot array and the game board with the bot's move and returns the index of the move. If the square that was clicked is already concluded, the function generates an array of valid moves for any unconcluded square and chooses a random move from that array. It then updates the plot array and the game board with the bot's move and returns the index of the move.
