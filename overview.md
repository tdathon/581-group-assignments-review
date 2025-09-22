# Overview
## Objects
// Game states obj 
let gameState = {
  board: [],        
  mineCount: 10,    
  flagsPlaced: 0,   
  revealedCells: 0, 
  status: 'ready',  
  firstClick: true  
};

// Relevant vars
{
  isMine: false,     
  isRevealed: false, 
  isFlagged: false,  
  adjacentMines: 0    
}




-----
## Diagram

User Input
│
▼
Game Object
┌───────────────────────┐
│ board[][]             │
│ mineCount, flagsPlaced│
│ revealedCells, status │
│ firstClick            │
└───────────────────────┘
│
▼
Rendering Functions
(renderBoard, updateUI)
│
▼
UI Display
(grid, status bar)



## Archeticture
The system is a web page Minesweeper game that uses HTML, CSS, and JavaScript.

* HTML (Brett Balquist) provides the skeleton: controls for mine input, start button, status display, and a container for the grid.
* CSS (Jay Patel) handles the UI styling, including typography, button interactions, game grid visuals, and colors for different numbers and states (flagged, revealed, mine, etc.).
* JavaScript powers the game logic:
    * Daniel Neugent: board initialization, mine placement, rendering functions, and core game loop (start, reveal, end).
    * Tej Gumaste: gameplay logic such as calculating adjacent mines, flagging, win condition checks, and handling clicks.
* Arnav Jain: utility functions (e.g., isValid) and user feedback (screen shake on loss).

The game maintains a game state object (above) with board data, mine/flag counts, revealed cells, and status. 
On start (`startGame()`), the board is generated (`initializeBoard()` + `renderBoard()`) and rendered dynamically. 
The first click triggers mine placement (`placeMines()`) and adjacency calculation (`calculateAdjacentMines()`), ensuring no immediate mine. 
Players reveal cells with left-click (` handleCellClick()` -> `revealCell()`) and place flags with right-click (`handleCellRightClick()` -> `toggleFlag()`), while the UI updates live (`updateBoardUI()` + `updateUI()`). 
Victory is triggered by `checkWinCondition()` when all non-mine cells are revealed. 
Loss occurs on mine click (`revealCell()` -> `endGame(false)`), revealing all mines and shaking the screen with `shakeScreenWhenLose()`.