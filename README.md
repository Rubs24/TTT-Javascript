# TTT-Javascript
2 Player Tic Tac Toe game utilizing css style classes and javascript logic to implement. HTML is used for structuring.

This is my code that I created following the "Build Tic Tac Toe With JavaScript - Tutorial" found at this link: https://youtu.be/Y-GkMjUZsmM

A brief explanation:

In the body of the HTML file we have a div with the class "board" and an id of "board". I picked up using classes to reference HTML items in CSS files and Ids to reference them in Javascript files After we have 9 divs that serve as our spaces to place X or O markers. We donote them by their class "cell" or "data-cell" Lastly in the HTML file we have the "winning-message" div with the Restart button as well

In the CSS file first we set up the board setting the height and width to 100vh and 100vw respectively to take up the entire screen however since the cells are only 100px squares they center well in the middle. They were placed on the board in a grid template with 3 columns so as to make the 3x3 cell patter. After some styling adjustments to remove certain borders on each cell to give us the # shape of the TTT board it was ready

The main implementation of this program is creating CSS syle classes tha render black X's and O's or their light grey counter parts that appear upon hovering over unoccupied cells when it's the respective players turn. Based on actions and previous states of the board and or the cell, classes are added to and removed from the board and cell. These classes are added and removed within our javascript logic. The various combination of classes determine the actions that are allowed and what is rendered. There are 4 total classes to be added which are X and O for the board and X and O for the cell. The board X and O indicate whos turn it is and whos light grey marker appears on unoccupied cells when hovering. Once a cell is clicked (and it can only be clicked once as implemented in our logic) it renders the marker of the current player. If for instance it is X's turn the board will have the X class and a grey X will render when the user hovers over unnocupied cells. When they click an empty cell the X class is added to that cell and it will render a solid black X the board will then shed it's X class and the javascript will add the O class to the board. Then a grey O will render once the user hover's over unoccupied cells and again when a open cell is clicked a black O will be rendered in that space.

Once a click is handled and the mark is placed Javascript checks the board for a winning combination. This is done by checking the class of every cell in a winning combination to see if they match. For example this first combinaiton checked is is cells 0, 1, and 2 have the same class. So the "currentClass" (X or O that's just been placed) is passed in and all the winning combinations are checked to see is the "currentClass" matches all three indexes of any of them. If a winning combination is found the game is ended with the function "endGame()" which we pass a false as a parameter to show the game is not a draw. After checking for a win we check for a draw by checking if all the cells contain an X or an O class and if they do and we just checked for a winner and there was none we can call the "endgame()" function with a true parameter. Once the game has ended "endGame()" function will render the "winningMessage" div which occupies the whole screen with the correct text showing who is the winner or a draw. Below it the restart button is also rendered which when clicked removes all classes from the cells, removes all EventListeners, and readds them. The winning message is also stripped of it's "show" class which sets it's display to true. The game can be played once again.
