# Question 1: Shortest Road Distance Between Indian Cities Using Dijkstra's Algorithm

## 1. Introduction

In this task, I implemented Dijkstra's Algorithm to find the shortest road-distance route between Indian cities.

The idea is to find the minimum distance between a starting city and a destination without manually checking every possible route. The algorithm explores cities based on their current shortest known distance and updates the route whenever a better option is found.

This problem is represented using a weighted graph, where cities are nodes and roads are edges.

## 2. Objective

The main objectives are:

- Represent Indian cities as a graph.
- Assign road distances as edge weights.
- Implement Dijkstra's Algorithm using Python.
- Find the shortest route between the selected source and destination.
- Display the shortest path and total distance.

## 3. Algorithm Used: Dijkstra's Algorithm

Dijkstra's Algorithm is a greedy shortest-path algorithm that works on graphs with non-negative edge weights.

### Working Procedure

1. Initialize the source city distance as 0.
2. Set the distance of all other cities to infinity.
3. Select the unvisited city with the smallest known distance.
4. Explore its neighboring cities.
5. Update a neighbor's distance if a shorter route is found.
6. Repeat until the destination is reached.
7. Reconstruct the shortest route using the stored parent information.

## 4. Dataset and Representation

The road network is represented using an adjacency list in Python.

Each city stores its connected cities and the corresponding road distances.

Example representation:

```python
graph = {
    "Hyderabad": {"Vijayawada": 275, "Bengaluru": 570},
    "Vijayawada": {"Hyderabad": 275, "Chennai": 450},
    "Bengaluru": {"Hyderabad": 570, "Chennai": 350},
    "Chennai": {"Vijayawada": 450, "Bengaluru": 350}
}
```

The above distances are only illustrative. The actual results depend on the graph used in the implementation.

## 5. Implementation

The program uses a priority queue to efficiently select the city with the minimum known distance.

Whenever a shorter route is discovered, the distance and previous city are updated.

After reaching the destination, the program reconstructs the route and displays the total distance.

## 6. Output

The program displays:

- Source city
- Destination city
- Shortest route
- Total road distance in kilometres

### Output Format

```text
Source City: <Source>
Destination City: <Destination>

Shortest Route:
<City 1> -> <City 2> -> <Destination>

Total Distance: <Calculated Distance> km
```

The actual route and distance are obtained from the program execution.

## 7. Time and Space Complexity

**Time Complexity:** O((V + E) log V)

**Space Complexity:** O(V + E)

Where:

- V = Number of cities
- E = Number of road connections

## 8. Result

Dijkstra's Algorithm successfully identifies the shortest route between the selected cities based on the supplied road-distance graph.

## 9. Learning Outcome

Through this task, I understood how real-world road networks can be represented using graphs and how a priority queue helps in finding shortest paths efficiently.

It also helped me connect the theoretical concept of greedy search with a practical route-planning problem.

## 10. Conclusion

This experiment demonstrates the application of Dijkstra's Algorithm for shortest-distance calculation in a weighted graph. The same concept can be extended to larger road networks and navigation systems, provided accurate road-distance data is available.
