[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/ulyILqqB)
# Weekly Coding #9: Midnight Monster Delivery

## Summary

This program finds the cheapest delivery route through a haunted city of monster customers. It uses Dijkstra's algorithm with a heap-based priority queue to compute the lowest travel cost from one location to every other location, and it reconstructs the shortest path between a start and target location.

## Approach

- The graph is represented as a dictionary where each location maps to a dictionary of neighboring locations and their positive travel costs.
- `monster_delivery_costs` initializes all node costs to `math.inf` and sets the start cost to 0.
- A `heapq` priority queue explores the lowest-cost frontier first, relaxing edges and updating costs when a better path is found.
- `shortest_monster_delivery` uses the same Dijkstra process while also tracking a `previous` map so the shortest path can be reconstructed from the target back to the start.

## Complexity

- `monster_delivery_costs`:
  - Time: O((V + E) log V)
  - Space: O(V)
  - Why: Each edge is relaxed once and heap operations for V nodes dominate the runtime.

- `shortest_monster_delivery`:
  - Time: O((V + E) log V)
  - Space: O(V)
  - Why: It uses Dijkstra's algorithm plus O(V) extra space for the `previous` map used to rebuild the path.

## Edge-Case Checklist

- [x] start equals target
- [x] target is unreachable
- [x] start node is missing
- [x] target node is missing
- [x] node has no outgoing edges
- [x] graph contains cycles
- [x] tied shortest paths
- [x] negative edge weight
- [x] zero edge weight
- [x] neighbor not listed as a graph node

## Tests I Added

No additional tests were added beyond the starter tests.

## Assistance & Sources

AI used? N

Other sources used:

- None

## Notes for Instructor

The required functions `validate_haunted_map`, `monster_delivery_costs`, and `shortest_monster_delivery` are implemented as described in the assignment. The optional stretch function `best_next_monster_stop` is not implemented.
