# Question 3: UGV Navigation in an Unknown Environment with Obstacle Detection and Replanning

## 1. Introduction

In Question 2, the UGV was provided with a map containing the obstacle locations in advance.

However, in a real-world environment, a robot may not know the complete layout before starting its journey. It must observe its surroundings, detect obstacles, and modify its route whenever the current path becomes blocked.

In this task, I implemented a simplified unknown-environment navigation system using A* Search, local sensor observations, and replanning.

The UGV begins without complete map information, discovers obstacles while moving, and calculates an alternative route when required.

## 2. Objective

- Simulate a UGV operating in an initially unknown environment.
- Use a local sensor to detect nearby obstacles.
- Maintain an updated map of the discovered environment.
- Implement A* Search for path planning.
- Recalculate the route when an obstacle blocks the current path.
- Measure navigation performance using MOE.

## 3. Environment Details

| Parameter | Value |
|---|---|
| Grid Size | 70 × 70 |
| Obstacle Density | 20% |
| Starting Position | (0, 0) |
| Goal Position | (69, 69) |
| Sensor Range | Local 3 × 3 area |
| Path Planning | A* Search |
| Navigation | Obstacle detection and replanning |

## 4. Dataset Used

```text
grid_20pct.csv
```

The actual environment contains the obstacle positions, but the UGV initially does not know the complete map.

Two maps are maintained:

**Actual Map:** Contains the true obstacle locations.

**Known Map:** Contains only the information discovered by the UGV.

The known map uses:

- -1 = Unknown cell
- 0 = Free cell
- 1 = Obstacle

## 5. Algorithms and Techniques Used

### A. A* Search

A* is used to calculate the route from the current position to the goal.

The evaluation function is:

**f(n) = g(n) + h(n)**

The Manhattan Distance heuristic is used because the UGV moves in four directions.

### B. Sensor-Based Obstacle Detection

The UGV observes a local 3 × 3 area around its current position.

The discovered information is used to update its known map.

### C. Replanning

When the UGV discovers an obstacle that blocks its remaining route, it runs A* again from its current position.

The new route is then followed towards the goal.

## 6. Working Procedure

1. Load the actual grid environment.
2. Initialize the known map with unknown cells.
3. Calculate the initial route using A*.
4. Move the UGV towards the goal.
5. Observe nearby cells using the sensor.
6. Update the known map.
7. Check whether a newly detected obstacle blocks the planned route.
8. If blocked, calculate an alternative path.
9. Continue navigation using the updated route.
10. Stop when the goal is reached.
11. Record the performance measures and display the final path.

## 7. Output Visualization

The final visualization contains:

- Red line: Actual path travelled by the UGV
- Black cells: Detected obstacles
- Green circle: Starting position
- Blue star: Goal
- Gray cells: Unknown areas in the discovered map

The red path shows the route actually travelled, including the detour after replanning.

## 8. Experimental Results

The successful simulation produced the following results:

| Metric | Result |
|---|---:|
| Goal Status | Success |
| Travel Distance | 148 moves |
| Replanning Count | 1 |
| Total Nodes Explored | 467 |
| Execution Time | Approximately 0.016 seconds |

Execution time may vary slightly depending on the runtime environment.

## 9. Result Analysis

The UGV successfully reached the goal despite initially having incomplete information about the environment.

The replanning count of 1 indicates that the UGV discovered an obstacle affecting its planned route and calculated an alternative path.

The travel distance of 148 moves represents the actual movement made by the UGV, including the detour.

The final visualization confirms successful navigation from the starting position to the destination.

## 10. Measures of Effectiveness (MOE)

| Metric | Purpose |
|---|---|
| Goal Status | Confirms successful navigation |
| Travel Distance | Measures total movement |
| Replanning Count | Indicates route recalculations |
| Nodes Explored | Measures search effort |
| Execution Time | Measures computational time |

## 11. Discussion

The main difference between Question 2 and Question 3 is the availability of obstacle information.

In Question 2, the UGV knows the obstacle locations before planning.

In Question 3, the UGV discovers obstacles during navigation. This makes the task more realistic because the initial route may not always remain valid.

By combining local sensing with A* Search, the UGV can respond to new information and continue towards its destination.

## 12. Learning Outcome

This task helped me understand that autonomous navigation is not always a one-time path calculation.

A robot must combine sensing, planning, and decision-making to operate in unfamiliar environments.

Replanning is important because it allows the UGV to adapt when newly discovered information makes its current route unsuitable.

## 13. Limitation

The current implementation simulates an initially unknown environment with obstacle detection and replanning. It does not simulate obstacles physically moving over time.

A future improvement would be to introduce moving obstacles and trigger replanning whenever their positions change and affect the planned route.

## 14. Conclusion

The experiment demonstrates how a UGV can navigate an initially unknown environment using sensor-based obstacle discovery and A* Search.

The successful result, with one replanning event, shows that the vehicle can adapt its route and reach the destination even when its initial map is incomplete.
