# -graph-algorithms mini-project
Problems and Algorithmic Solutions

Task 1: Graph RepresentationProblem: Graphs need to be stored in memory efficiently based on the density of their edges and the specific algorithmic requirements.

Solution:Adjacency Matrix: A 2D array of size $V \times V$ (where $V$ is the number of vertices). We implemented this by initializing a grid of zeros and updating specific coordinates with edge weights. It provides $O(1)$ time complexity for edge lookups but requires $O(V^2)$ space, making it suitable for dense graphs.Adjacency List: A dictionary where each node points to a list of its neighbors. This uses $O(V + E)$ space, making it highly memory-efficient for sparse graphs.

Task 2: Graph Traversal (Friend Suggestions)Problem: In a social network, we need to find how closely related two users are (degrees of separation) and explore deep, nested friend groups.

Solution:Breadth-First Search (BFS): Uses a Queue to explore the graph level by level. It is the perfect solution for finding the shortest path (fewest edges) between two users, effectively calculating the "degrees of separation."Depth-First Search (DFS): Uses recursion (an implicit Stack) to explore as deeply as possible along a branch before backtracking. This is used to map out the furthest reach of a specific friend cluster.
Task 3: Topological Sorting (Task Dependency)Problem: Certain projects or build systems have strict prerequisites (e.g., Task B cannot start until Task A finishes). We need to determine a valid linear execution order.

Solution:Kahn’s Algorithm (In-Degree Method): We track the "in-degree" (number of incoming edges/prerequisites) for every node. Nodes with an in-degree of 0 are ready to execute and are placed in a queue. As each task is "processed," we reduce the in-degree of its dependent tasks. If a cycle exists (e.g., A depends on B, and B depends on A), the algorithm flags it as an impossible schedule.

Task 4: Shortest Path Algorithms (Emergency & Complex Routing)Problem: We need to route emergency vehicles via the fastest path, but we also need a system that can handle complex routing where negative weights (like extreme tailwinds or toll rebates) might exist.

Solution:Dijkstra's Algorithm: Implemented using a Priority Queue (Min-Heap). It greedily selects the closest unvisited node, updating the shortest known distances to its neighbors. It is highly efficient but fails if negative edge weights are present.Bellman-Ford Algorithm: Relaxes all edges in the graph $V - 1$ times. While slower than Dijkstra's, it correctly calculates shortest paths in graphs with negative weights and can successfully detect negative weight cycles (where a path's cost infinitely decreases).

Task 5: Minimum Spanning Tree (Network Cabling)Problem: We need to connect a series of buildings with fiber optic cables such that every building is connected, but the total length (and cost) of the cables is minimized.

Solution:Prim's Algorithm: Starts from a single central node and greedily adds the cheapest outward edge that connects to an unvisited node, using a Priority Queue. Excellent for dense networks.Kruskal's Algorithm: Sorts all edges in the graph from cheapest to most expensive. It iterates through the sorted edges, adding them to the tree only if they do not form a cycle (managed via a Disjoint Set / Union-Find data structure).
