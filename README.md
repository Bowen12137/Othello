```markdown
# Othello Game

This project is a Java implementation of the classic board game **Othello**. The game supports a human vs. computer mode, where players can take turns placing pieces on the board to capture the opponent's pieces. The computer uses the Minimax algorithm with alpha-beta pruning to make decisions.

## Project Structure

The project consists of the following main Java files:

- **BoardState.java**: Represents the state of the Othello board and provides methods to check for legal moves, make moves, and determine the game status.
- **Move.java**: Represents a single move on the Othello board with coordinates `x` and `y`.
- **Othello.java**: Contains the main game logic, initializes the board, and implements the Minimax algorithm to allow the computer to make optimal moves.
- **OthelloDisplay.java**: Provides a graphical user interface (GUI) for the game using `JFrame`. It displays the board, pieces, and allows users to make moves by clicking on the board.

## Classes and Key Methods

### 1. **BoardState**
   - **Attributes**:
     - `board`: A 2D array representing the board, where each cell stores the color of the piece (1 for white, -1 for black, and 0 for empty).
     - `colour`: Indicates the current player's color.
   - **Methods**:
     - `deepCopy()`: Creates a deep copy of the current board state.
     - `getLegalMoves()`: Returns a list of all legal moves for the current player.
     - `makeLegalMove(int x, int y)`: Executes a legal move and updates the board.
     - `gameOver()`: Checks if the game is over.
     - `resultString()`: Returns the final result of the game (e.g., "White wins", "Black wins", or "Draw").

### 2. **Move**
   - Represents a move on the board with the coordinates `x` and `y`.

### 3. **Othello**
   - **Constants**:
     - `SQUARESIZE`: The size of each square on the board in pixels.
     - `PIECERATIO`: Ratio of the piece's radius to the square size.
     - `searchDepth`: The depth for the Minimax search algorithm.
   - **Methods**:
     - `main()`: Initializes the board and starts the GUI display.
     - `chooseMove(BoardState boardState)`: Determines the computer's move using the Minimax algorithm.
     - `evaluateBoard(BoardState boardState)`: Evaluates the board to assist the Minimax decision-making.
     - `minimax_val(BoardState boardState, int depth, int alpha, int beta)`: Recursive Minimax algorithm with alpha-beta pruning.
     - `minimax(BoardState boardState, int depth)`: Wrapper method for the Minimax algorithm to choose the best move.

### 4. **OthelloDisplay**
   - A GUI for the Othello game.
   - **Attributes**:
     - `boardState`: Represents the current state of the board displayed in the GUI.
   - **Methods**:
     - `paint(Graphics g)`: Draws the board, pieces, and any game status text.
     - `flashOpponentMove(int x, int y)`: Provides a visual indication of the opponent's move.
     - `mousePressed(MouseEvent e)`: Handles user input and moves based on mouse clicks.
     - `xCanvasToSquare(int x)`, `yCanvasToSquare(int y)`: Converts screen coordinates to board square coordinates.
     - `myWait(int x)`: Simulates a short delay to enhance animation effects.

## Game Rules

1. Players take turns placing pieces on the board.
2. When a piece is placed, all opponent pieces in a straight line (horizontal, vertical, or diagonal) between the new piece and an existing piece of the same color are captured.
3. The game ends when no legal moves are available for either player.
4. The player with the most pieces on the board at the end wins.

## Running the Game

1. Compile the Java files using the following command:
   ```bash
   javac *.java
   ```

2. Run the `Othello` game:
   ```bash
   java Othello
   ```

3. The GUI window will display the Othello board. The player can make a move by clicking on an empty square. The computer will respond with its move.

## How the Computer Plays

The computer's moves are determined using the **Minimax algorithm** with alpha-beta pruning:
- The algorithm evaluates the board for potential moves and chooses the optimal move by maximizing its own score and minimizing the player's score.
- It uses a heuristic scoring system to evaluate the board's state, assigning values to each board position based on strategic importance.

## Dependencies

- Java Development Kit (JDK) 8 or higher.
- No external libraries are required as the GUI is implemented using Java's built-in `Swing` framework.

## Future Improvements

1. **Enhanced AI**: Improve the AI by adjusting the heuristic or adding more advanced search techniques.
2. **Additional Game Modes**: Implement human vs. human mode or difficulty levels for the computer player.
3. **Improved GUI**: Add animations and visual effects for a better user experience.

