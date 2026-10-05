# Question 2: UGV Path Planning in a Grid with Static Obstacles Using A* Search

## 1. Introduction

In this task, I simulated an Unmanned Ground Vehicle (UGV) navigating through a grid environment containing static obstacles.

The UGV starts from one position and must reach a goal while avoiding blocked cells. To solve this problem, I implemented A* Search and tested it using three different obstacle densities: 10%, 20%, and 30%.

The main purpose was to understand how obstacle density affects pathfinding and the overall performance of the search algorithm.

## 2. Objective

- Create a 70 × 70 grid environment.
- Place static obstacles at different densities.
- Find the shortest valid path from the start to the goal.
- Implement A* Search using Python.
- Visualize the generated paths.
- Compare performance using Measures of Effectiveness (MOE).

## 3. Environment Details

| Parameter | Value |
|---|---|
| Grid Size | 70 × 70 |
| Start Position | (0, 0) |
| Goal Position | (69, 69) |
| Obstacle Density | 10%, 20%, 30% |
| Movement | Up, Down, Left, Right |
| Movement Cost | 1 per move |

The grid is represented using CSV files.

- 0 represents a free cell.
- 1 represents an obstacle.

The supplied maps preserve a clear corridor so that a valid route is available.

## 4. Algorithm Used: A* Search

A* is an informed search algorithm that uses both the actual cost travelled and an estimated cost to the goal.

The evaluation function is:

**f(n) = g(n) + h(n)**

Where:

- g(n) = Cost from the starting cell to the current cell.
- h(n) = Estimated cost from the current cell to the goal.
- f(n) = Total estimated path cost.

### Heuristic Function: Manhattan Distance

Since the UGV moves only in four directions, Manhattan Distance is used.

**h(n) = |current row - goal row| + |current column - goal column|**

This heuristic helps A* prioritize cells that are closer to the destination.

## 5. Dataset Used

Three CSV datasets were used:

```text
grid_10pct.csv
grid_20pct.csv
grid_30pct.csv
```

Each dataset represents a 70 × 70 grid with a different obstacle density.

## 6. Working Procedure

1. Load the grid dataset.
2. Initialize the start and goal positions.
3. Insert the starting cell into the priority queue.
4. Select the cell with the lowest f(n) value.
5. Explore its valid neighboring cells.
6. Ignore obstacles and cells outside the grid.
7. Update the path cost and parent information.
8. Continue until the goal is reached.
9. Reconstruct the shortest path.
10. Display the path and record the performance metrics.
11. Repeat for all three obstacle densities.

## 7. Measures of Effectiveness (MOE)

The following metrics are used to evaluate the algorithm:

| Metric | Description |
|---|---|
| Path Length | Total number of moves |
| Nodes Explored | Number of cells expanded by A* |
| Execution Time | Time taken by the algorithm |
| Obstacle Density | Percentage of blocked cells |
| Goal Status | Whether the UGV reached the destination |

## 8. Output Visualization

The generated grid visualization contains:

- Black cells: Obstacles
- Red line: Shortest path found by A*
- Green marker: Starting position
- Blue marker: Goal
- White cells: Free space

The program also generates a `moe_results.csv` file containing the performance measurements.

## 9. Results

The experiment is performed for all three obstacle densities.

| Obstacle Density | Goal Status | Path Length | Nodes Explored | Execution Time |
|---|---|---|---|---|
| 10% | Success/Failure | Actual output | Actual output | Actual output |
| 20% | Success/Failure | Actual output | Actual output | Actual output |
| 30% | Success/Failure | Actual output | Actual output | Actual output |

*The values should be taken directly from the generated MOE results.*

## 10. Discussion

As obstacle density increases, the available free space decreases, which can make navigation more challenging.

The number of explored cells and execution time may increase depending on how the obstacles are distributed.

The visualization also helps verify that the generated path avoids obstacles and connects the starting point to the goal.

## 11. Learning Outcome

This task helped me understand how heuristic search works in practical path-planning problems.

By testing different obstacle densities, I could observe how environmental complexity affects the search process and why selecting an appropriate heuristic is important.

## 12. Conclusion

A* Search provides an effective approach for finding a shortest path in a grid environment with static obstacles.

The experiment demonstrates how search algorithms can be used for autonomous ground vehicle navigation and how MOE metrics help evaluate their performance.
