# Minesweeper System Development

**Course:** EECS 581 Software Engineering II, Fall 2025  
**Professor:** Hossein Saiedian  

**Creators:** Daniel, Tej, Jay, Brett, Arnvair  

---

## Overview
This project develops Minesweeper a  classic single-player puzzle game.  
Players interact with a uncovering cells to reveal numbers that indicate adjacent mines.  
The objective is to uncover all non-mine cells while avoiding detonating mines. Players may flag suspected mine locations.  

---

## How To Install and Run

* run ```git clone git@github.com:l33tdaniel/581-group-assignments.git```
* Open the folder and right click on the file minesweeper.html
* Open with your browser
* Enjoy Playing!

---

## Requirements

### Game Setup
- **Board Configuration:**
  - Size: 10x10 grid
  - Columns labeled **A–J**; rows numbered **1–10**

- **Mine Configuration:**
  - Number of mines: **User-specified (10–20)**
  - Randomly placed at game start
  - First clicked cell (and optionally adjacent cells) guaranteed mine-free

- **Initial State:**
  - All cells start covered
  - No flags placed

---

### Gameplay
- **Uncovering Cells:**
  - Selecting a cell uncovers it.
  - Uncovering a mine → **Game Over (loss)**.
  - Safe cells display a number (0–8) representing adjacent mines.
  - Cells with **zero adjacent mines** trigger **recursive uncovering** of neighbors.

- **Mine Flagging:**
  - Players toggle flags on covered cells to mark suspected mines.
  - Flagged cells cannot be uncovered until unflagged.
  - Remaining flag count displayed (**total mines – placed flags**).

- **Player Interface:**
  - 10x10 grid showing: covered, flagged, or uncovered states.
  - Remaining mine count.
  - Status indicator: *Playing*, *Game Over: Loss*, *Victory*.

- **Game Conclusion:**
  - **Loss:** uncovering a mine → all mines revealed.
  - **Win:** all non-mine cells uncovered without detonating any mines.

---

## Submission Requirements
- **Code Freeze:** Final commit on GitHub master branch by due date.
- **Demo:** Weekly GTA/team meeting, using frozen master branch.
- **Artifacts:** All code & documentation stored in GitHub master branch.
- **Peer Reviews:** Individual Team Peer Evaluation forms submitted on Canvas.

---

## System Architecture

**Purpose:**  
Describes the high-level structure to facilitate feature extensions by the Project 2 team.

**Components:**
- **Board Manager:** Manages the 10x10 grid as a 2D array, tracking cell states (covered, flagged, uncovered, mine).  
- **Game Logic:** Handles gameplay rules, including mine placement, cell uncovering, recursive revealing, and win/loss detection.  
- **User Interface:** Renders the grid, status indicators (mine count, game state), and user inputs (clicks for uncovering/flagging).  
- **Input Handler:** Processes user inputs (e.g., clicks, key presses) and communicates with Game Logic to update the Board.  

**Data Flow:**
- User input (click) → Input Handler validates and sends to Game Logic  
- Game Logic updates Board state (e.g., uncover cell, place flag)  
- Board state changes trigger UI updates (e.g., render number, flag, or mine)  

**Key Data Structures:**
- 2D array (10x10) for grid: stores cell states (0 = covered, 1 = flagged, 2 = uncovered number, 3 = mine).  
- Game state object: tracks mine count, flags remaining, and win/loss status.  

**Assumptions:**
- Fixed 10x10 grid size  
- Mine count user-specified (10–20) at game start  

**Language and Platform:**  
The game is written in **HTML and JavaScript**.  

---

## Grading Criteria (100 Points)

### 1. Working Product Demonstration (40 Points)
- **Exceeds Expectations (90–100%)**: All specified features are present; stable under stress testing; intuitive interface; modular and extensible code.  
- **Meets Expectations (80–89%)**: Most features present; mostly stable; user interface intuitive with minor guidance.  
- **Unsatisfactory (0–79%)**: Two or fewer features implemented; unstable or confusing interface.  

### 2. Estimate of Person-Hours (10 Points)
- **Exceeds Expectations (90–100%)**: Detailed methodology, clear and justified.  
- **Meets Expectations (80–89%)**: Provided but lacks clarity.  
- **Unsatisfactory (0–79%)**: None, or without explanation.  

### 3. Actual Accounting of Person-Hours (10 Points)
- **Exceeds Expectations (90–100%)**: Complete day-by-day accounting, clear and accurate.  
- **Meets Expectations (80–89%)**: Incomplete or minor inaccuracies.  
- **Unsatisfactory (0–79%)**: Missing or fabricated.  

### 4. System Documentation (20 Points)
- **Exceeds Expectations (90–100%)**: Comprehensive documentation, clear diagrams, enables extension.  
- **Meets Expectations (80–89%)**: Mostly complete with minor gaps.  
- **Unsatisfactory (0–79%)**: Missing major details or diagrams.  

### 5. Code Documentation and Comments (20 Points)
- **Exceeds Expectations (90–100%)**: Complete prologue comments, detailed in-code comments, full attribution.  
- **Meets Expectations (80–89%)**: Present but missing some elements.  
- **Unsatisfactory (0–79%)**: Lacking comments or attribution.  

## Source Attribution
All external code sources must be clearly identified and comments rephrased for clarity.  
Failure to attribute sources constitutes **academic misconduct**.  


## Peer Evaluation
Mandatory submission. Each member must act as a manager and divide a **$10,000 bonus** among team members (submitted via Canvas).  
Penalty: **-25 points** for non-submission.  

