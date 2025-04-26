# Maze Solver (C++) 🧩

A memory-efficient C++ Maze Solver implementing four pathfinding algorithms: **DFS**, **BFS**, **Dijkstra**, and **A\***.  
The maze is built using graphs with minimal vertices for efficient traversal.

## Features 🌟
- Efficient graph-based maze structure (only important vertices are created)
- Four pathfinding algorithms:
  - Depth-First Search (DFS)
  - Breadth-First Search (BFS)
  - Dijkstra's Algorithm
  - A* Algorithm (Manhattan distance)
- Customizable Maze Reader (`IMazeReader`) for any input format
- Animation to visualize pathfinding (Windows only)

## Usage 🚀
1. Include the `MazeSolver.h` header:
   ```cpp
   #include "MazeSolver.h"
   Create a Maze Reader by inheriting from IMazeReader and implementing:
   ```

2. Create a Maze Reader by inheriting from IMazeReader and implementing:

   ```cpp
      void isVertex(int row, int column, bool &top, bool &down, bool &left, bool &right, bool &isGoal);
      void setSize(size_t &row, size_t &col);
   ```
3. Build and solve the maze:
   ```cpp
      Maze maze;
      MazeStringReader msb;
      maze.setMaze(msb);

      DepthFirstSearch dfs;
      dfs.findPath(maze.maze_begin(), maze.maze_end());
   ```
4. Retrieve the path:
   ```cpp
       auto path = dfs.getPath();
    ```
## Running Example 💻
* To solve a maze from file, run:
    example/driver.cpp

* To view pathfinding animations, run:
    example/animate.cpp
    (Adjust speed and window size using macros in animate.cpp.)

## Notes 📝
* If start and end points are not manually set, they are automatically assigned.
* Further improvements can optimize vertex minimization and add more algorithms.

