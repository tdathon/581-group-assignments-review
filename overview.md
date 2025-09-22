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
Diagram
-----


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


