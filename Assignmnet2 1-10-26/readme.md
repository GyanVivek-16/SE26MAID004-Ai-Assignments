# UGV Path Planning and Navigation Using Search Algorithms

## About the Project

This project explores how search algorithms can be used to solve shortest-path and autonomous navigation problems.

It consists of three tasks, starting with finding the shortest road distance between Indian cities and progressing towards UGV navigation in environments with static and initially unknown obstacles.

The implementations are developed using Python, with visualizations and performance metrics to understand how the algorithms behave in different scenarios.

## Project Tasks

### Question 1: Shortest Road Distance Using Dijkstra's Algorithm

Implemented Dijkstra's Algorithm to find the shortest route between Indian cities using a weighted graph.

**Key concepts:**
- Graph representation
- Weighted edges
- Shortest-path calculation
- Priority queue

### Question 2: UGV Navigation with Static Obstacles

Implemented A* Search to find the shortest path for a UGV in a 70 × 70 grid environment.

The algorithm was tested with three obstacle densities:

- 10%
- 20%
- 30%

Performance was evaluated using path length, nodes explored, and execution time.

### Question 3: UGV Navigation in an Unknown Environment

Extended the navigation system to simulate an initially unknown environment.

The UGV uses local sensor observations to discover obstacles and replans its route whenever a detected obstacle blocks its current path.

**Observed Results:**

| Metric | Result |
|---|---:|
| Goal Status | Success |
| Travel Distance | 148 moves |
| Replanning Count | 1 |
| Nodes Explored | 467 |
| Execution Time | ~0.016 seconds |

## Technologies Used

- Python
- Google Colab
- NumPy
- Pandas
- Matplotlib
- Heapq
- CSV datasets

## Repository Structure

```text
UGV-Path-Planning/
│
├── Question-1/
├── Question-2/
└── Question-3/
```

Each question folder contains its respective implementation, dataset where applicable, output, and detailed README.

## Learning Outcomes

Through this project, I gained practical experience with graph-based search, heuristic pathfinding, obstacle avoidance, and route replanning.

It helped me understand how search algorithms move beyond theory and can be applied to real-world problems such as navigation and autonomous systems.

## Conclusion

This project demonstrates the use of Dijkstra's Algorithm and A* Search for shortest-path problems, along with sensor-based replanning for navigation in an initially unknown environment.
