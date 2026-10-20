# Puzzle-Fordge-Game
Puzzle Forge is an interactive puzzle-solving platform designed to challenge users with logic-based and strategic problems. The application allows users to engage with different puzzle types while also showcasing algorithmic problem-solving techniques.  
- Java
- Data Structures & Algorithms
- BFS, Dijkstra, Dynamic Programming
---

## 🧠 Algorithm Design & Implementation Details

### 1. Bitmask-Based State Representation
Each grid configuration is represented using an integer bitmask, where individual bits encode the states of grid cells.

- **Space-efficient representation:** Stores multiple binary cell states in a single integer.
- **Fast state operations:** Uses bitwise operators to inspect and modify configurations.
- **State comparison:** Enables efficient comparison and hashing of puzzle configurations.

### 2. Graph-Based State-Space Search
The puzzle is modeled as a state-space graph:

- **Nodes:** Valid grid configurations.
- **Edges:** Legal moves between configurations.
- **Goal state:** The configuration that satisfies the puzzle's completion condition.

This representation allows standard graph-search algorithms to explore possible solutions.

### 3. Search Algorithms

| Algorithm | Purpose | Key Property |
|---|---|---|
| Breadth-First Search (BFS) | Finds shortest paths when all moves have equal cost | Complete and optimal for unweighted graphs |
| Dijkstra's Algorithm | Finds minimum-cost paths when edge weights are non-negative | Optimal for weighted graphs |

### 4. Complexity Analysis

For a puzzle with \(N\) binary cells, there can be at most \(2^N\) distinct bitmask configurations.

- **State-space size:** \(O(2^N)\)
- **BFS time complexity:** \(O(V+E)\)
- **BFS space complexity:** \(O(V)\)
- **Dijkstra time complexity:** \(O((V+E)\log V)\) with a suitable priority queue implementation

Here, \(V\) is the number of reachable states and \(E\) is the number of valid transitions between states. Actual complexity depends on the implementation and reachable state space.

### 5. Software Architecture

The application separates puzzle logic from the graphical interface:

- **`DijakPaths.java`:** Core puzzle-state representation and solver logic.
- **`RealtimeUI.java`:** Java Swing interface, user interactions, and game controls.

This separation improves code organization, maintainability, and future extensibility.

### 6. Future Enhancements

- Implement A* search with an admissible heuristic.
- Add step-by-step visualization of algorithm execution.
- Introduce solver performance comparisons across different board sizes.
- Add automated tests for state transitions and solution correctness.
- Improve scalability with search pruning and compact state representations.


---

## 🎮 Game Mechanics & Rules

### 🕹️ Gameplay Overview

PuzzleForge is an interactive grid-based puzzle game that combines player decision-making with algorithm-driven AI solving. Players interact with the board through the Java Swing interface while the underlying solver explores possible game states.

### 🎯 Objective

- Reach the target configuration by making valid moves.
- Solve the puzzle within the available time.
- Complete the challenge while minimizing unnecessary moves.
- Compete against the AI solver to compare problem-solving strategies.

### ⚙️ How the Game Works

1. **Initialize the Board:** The application creates a grid with an initial configuration and a target state.
2. **Player Interaction:** The player makes moves through the graphical interface.
3. **State Update:** The game updates the board configuration using its internal state representation.
4. **AI Computation:** The solver searches possible configurations using the implemented graph-search algorithms.
5. **Progress Evaluation:** The application checks the current configuration against the goal condition.
6. **Game Completion:** The game ends when the puzzle is solved or the configured time limit expires.

### 🤖 AI Solver

The AI uses graph-search techniques to find solutions to the puzzle.

- **Breadth-First Search (BFS):** Explores states level by level to find a shortest path when every move has equal cost.
- **Dijkstra's Algorithm:** Finds a minimum-cost path when transitions have non-negative weights.
- **Bitmask Encoding:** Represents grid configurations compactly, enabling efficient state comparison and storage.

### 🏆 Challenge and Scoring

The game can be described in terms of its challenge elements:

- **Time Limit:** A countdown adds a time-management element.
- **Move Efficiency:** Fewer moves can be used as a measure of solution efficiency.
- **Player vs. AI:** Compare human decisions with algorithm-generated solutions.

### 🔄 Core Game Loop

```text
Initialize Puzzle
       ↓
Display Grid
       ↓
Accept Player Move
       ↓
Update Game State
       ↓
Check Goal Condition
       ↓
Continue or End Game
```

### 💡 Design Goals

- Make Data Structures and Algorithms concepts interactive.
- Demonstrate state-space search in a visual application.
- Explore compact state representation through bit manipulation.
- Separate game logic from graphical interface code.



