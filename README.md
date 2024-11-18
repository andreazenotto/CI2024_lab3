#### Andrea Zenotto - s327473  

---

# Lab3: N-Puzzle Solver  

## Overview  
This project implements a solver for the \( n^2-1 \) puzzle (e.g., 8-puzzle, 15-puzzle) using the A* algorithm. The goal is to solve puzzles of varying dimensions efficiently by leveraging heuristic-based search methods.  

---

## Algorithm  

### A* Algorithm  
- **Description**: A heuristic-based path-search algorithm that evaluates states using the \( f(n) = g(n) + h(n) \) cost function:  
  - \( g(n) \): Cost of the path from the start to the current state.  
  - \( h(n) \): Heuristic estimate of the cost to reach the goal state.  
- **Heuristic Used**:  
  - **Manhattan Distance**: Measures the total distance each tile must travel to reach its goal position, ignoring obstacles.  

### Implementation Details  
- **Puzzle State Representation**:  
  - Uses a `PuzzleState` class to encapsulate the puzzle's state, cost information (\( g, h, f \)), and path taken.  
- **Shuffling**:  
  - Puzzles are randomized through a series of valid moves to ensure solvability.  
- **Goal State**:  
  - Defined as a puzzle where tiles are ordered sequentially with the blank space (0) at the bottom-right corner.  

---

## Results  

The following results were obtained by solving 8-puzzle and 15-puzzle instances with 100,000 randomization steps:  

### 8-Puzzle (3x3)  
- **Start State**:  
  ```plaintext  
  [[8 6 7]  
   [2 5 4]  
   [3 0 1]]  
  ```  
- **Solution**: Found in 31 moves.  
- **Total Actions Evaluated**: 201.  

### 15-Puzzle (4x4)  
- **Start State**:  
  ```plaintext  
  [[ 1  2  3  4]  
   [ 5  6  0  8]  
   [ 9 10  7 11]  
   [13 14 15 12]]  
  ```  
- **Solution**: Found in 50 moves.  
- **Total Actions Evaluated**: 600.  

---

## Customization  

- **Puzzle Size**: Change `PUZZLE_DIM` to solve puzzles of different dimensions (e.g., 3 for 8-puzzle, 4 for 15-puzzle).  
- **Randomization Steps**: Adjust `RANDOMIZE_STEPS` to control the difficulty. Example:  
  ```python  
  solve_puzzle(PUZZLE_DIM=5, RANDOMIZE_STEPS=200000)  
  ```  
