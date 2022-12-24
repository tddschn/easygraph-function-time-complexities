# Time Complexities of EasyGraph Functions

- [Time Complexities of EasyGraph Functions](#time-complexities-of-easygraph-functions)
  - [Centrality](#centrality)
    - [`betweenness_centrality` - `O(VE)` (source)](#betweenness_centrality---ove-source)
    - [`closeness_centrality` - `O(V(V+E))` (source)](#closeness_centrality---ovve-source)
  - [`structural_holes/evaluation.py`](#structural_holesevaluationpy)
    - [`effective_size` - `O(V^2)` (source)](#effective_size---ov2-source)
    - [`efficiency` - `O(V^2)` (source)](#efficiency---ov2-source)
    - [`constraint` - `O(V^2)` (source)](#constraint---ov2-source)
    - [`hierarchy` - `O(V^2)` (source)](#hierarchy---ov2-source)
  - [clustering coefficient](#clustering-coefficient)
    - [`clustering` - `O(V^3)` (source)](#clustering---ov3-source)
    - [`average_clustering` - `O(V^3)` (source)](#average_clustering---ov3-source)
  - [Shortest Path](#shortest-path)
    - [`Dijkstra` - `O(V^2 + E log V)` - (source)](#dijkstra---ov2--e-log-v---source)
    - [`Floyd` - `O(V^3)` - (source)](#floyd---ov3---source)
    - [`Prim` - `O(E log V)` - (source)](#prim---oe-log-v---source)
    - [`Kruskal` - `O(E log E)` - (source)](#kruskal---oe-log-e---source)
  - [Minimum Spanning Tree](#minimum-spanning-tree)
    - [`minimum_spanning_tree` - (source)](#minimum_spanning_tree---source)
  - [biconnected](#biconnected)
    - [`is_biconnected` - `O(V + E)` - (source)](#is_biconnected---ov--e---source)
    - [`biconnected_components` - `O(V + E)` - (source)](#biconnected_components---ov--e---source)

<!-- ## Prompt

ChatGPT links
- centrality and evaluation: https://chat.openai.com/chat/7ba4a771-fd17-4d7c-a677-51481215186f
- clustering: 

```
calculate the time complexity of `betweenness_centrality` function with respect to the number of nodes (V) and number of edges (E) of in input graph parameter G, from the python code below:
``` -->

## Centrality

### `betweenness_centrality` - `O(VE)` ([source](https://github.com/easy-graph/Easy-Graph/blob/19d2b0597efe18b405b13213294ce3a70202dc0d/easygraph/functions/structural_holes/evaluation.py#L337))

The time complexity of the betweenness_centrality function is O(VE), where V is the number of nodes in the input graph and E is the number of edges.

This is because the function first calculates the shortest paths between all pairs of nodes in the graph, using either Dijkstra's algorithm or breadth-first search. Dijkstra's algorithm has a time complexity of O((E+V)logV) for a weighted graph, or O(VE) for an unweighted graph. Breadth-first search has a time complexity of O(V+E).

After the shortest paths are calculated, the function then iterates through all the nodes in the graph and accumulates the betweenness centrality values for each node. This has a time complexity of O(V).

Therefore, the overall time complexity of the function is O(VE).

### `closeness_centrality` - `O(V(V+E))` ([source](https://github.com/easy-graph/Easy-Graph/blob/19d2b0597efe18b405b13213294ce3a70202dc0d/easygraph/functions/centrality/closeness.py#L27))

The time complexity of the closeness_centrality function is O(V(V+E)), where V is the number of nodes in the input graph and E is the number of edges.

This is because the function calculates the shortest paths from each node to all other nodes in the graph, using either Dijkstra's algorithm or breadth-first search. Dijkstra's algorithm has a time complexity of O((E+V)logV) for a weighted graph, or O(VE) for an unweighted graph. Breadth-first search has a time complexity of O(V+E).

After the shortest paths are calculated, the function then iterates through all the nodes in the graph and calculates the closeness centrality values for each node. This has a time complexity of O(V).

Therefore, the overall time complexity of the function is O(V(V+E)).

## `structural_holes/evaluation.py`

### `effective_size` - `O(V^2)` ([source](https://github.com/easy-graph/Easy-Graph/blob/19d2b0597efe18b405b13213294ce3a70202dc0d/easygraph/functions/structural_holes/evaluation.py#L85))

The time complexity of the effective_size function is O(V^2), where V is the number of nodes in the input graph.

This is because the function calculates the normalized mutual weights between all pairs of nodes in the graph, using the normalized_mutual_weight function. The normalized_mutual_weight function has a time complexity of O(1) since it uses memoization to store previously calculated values.

After the normalized mutual weights are calculated, the function then iterates through all pairs of nodes in the graph and calculates the redundancy value for each pair of nodes. This has a time complexity of O(V^2).

The effective_size_borgatti_parallel function has a similar time complexity, as it iterates through all nodes in the graph and calculates the ego subgraph for each node, which has a time complexity of O(V+E). It then iterates through the nodes in the ego subgraph and calculates the effective size for each node, which has a time complexity of O(V).

The redundancy function has a time complexity of O(V^2), as it iterates through all pairs of nodes in the graph and calculates the redundancy value for each pair of nodes.

Therefore, the overall time complexity of the effective_size function is O(V^2).

### `efficiency` - `O(V^2)` ([source](https://github.com/easy-graph/Easy-Graph/blob/19d2b0597efe18b405b13213294ce3a70202dc0d/easygraph/functions/structural_holes/evaluation.py#L175))

The time complexity of the efficiency function is O(V^2), where V is the number of nodes in the input graph.

This is because the function calculates the shortest paths between all pairs of nodes in the graph, using the shortest_path function. The shortest_path function has a time complexity of O(VE + V^2logV) for a weighted graph, or O(VE + V^2) for an unweighted graph, using Dijkstra's algorithm.

After the shortest paths are calculated, the function then iterates through all pairs of nodes in the graph and calculates the efficiency for each pair of nodes. This has a time complexity of O(V^2).

Therefore, the overall time complexity of the efficiency function is O(V^2).

### `constraint` - `O(V^2)` ([source](https://github.com/easy-graph/Easy-Graph/blob/19d2b0597efe18b405b13213294ce3a70202dc0d/easygraph/functions/structural_holes/evaluation.py#L220))

The time complexity of the constraint function is O(V^2), where V is the number of nodes in the input graph.

This is because the function calculates the shortest paths between all pairs of nodes in the graph, using the shortest_path function. The shortest_path function has a time complexity of O(VE + V^2logV) for a weighted graph, or O(VE + V^2) for an unweighted graph, using Dijkstra's algorithm.

After the shortest paths are calculated, the function then iterates through all nodes in the graph and calculates the constraint value for each node. This has a time complexity of O(V).

Therefore, the overall time complexity of the constraint function is O(V^2).

### `hierarchy` - `O(V^2)` ([source](https://github.com/easy-graph/Easy-Graph/blob/19d2b0597efe18b405b13213294ce3a70202dc0d/easygraph/functions/structural_holes/evaluation.py#L337))

The time complexity of the hierarchy function is O(V^2), where V is the number of nodes in the input graph.

This is because the function calculates the shortest paths between all pairs of nodes in the graph, using the shortest_path function. The shortest_path function has a time complexity of O(VE + V^2logV) for a weighted graph, or O(VE + V^2) for an unweighted graph, using Dijkstra's algorithm.

After the shortest paths are calculated, the function then iterates through all nodes in the graph and calculates the hierarchy value for each node. This has a time complexity of O(V).

Therefore, the overall time complexity of the hierarchy function is O(V^2).

## clustering coefficient

### `clustering` - `O(V^3)` ([source](https://github.com/easy-graph/Easy-Graph/blob/19d2b0597efe18b405b13213294ce3a70202dc0d/easygraph/functions/basic/cluster.py#L444))

The time complexity of the clustering function with respect to the number of nodes (V) and number of edges (E) of the input graph G depends on how the graph is represented and how the triangles are counted.

If the graph is represented as an adjacency matrix, the time complexity for counting the number of triangles would be O(V^3). However, if the graph is represented as an adjacency list, the time complexity for counting the number of triangles would be O(E * E * E), which is O(E^3).

Overall, the time complexity of the clustering function would be O(V^3) if the graph is represented as an adjacency matrix, and O(E^3) if the graph is represented as an adjacency list.



### `average_clustering` - `O(V^3)` ([source](https://github.com/easy-graph/Easy-Graph/blob/19d2b0597efe18b405b13213294ce3a70202dc0d/easygraph/functions/basic/cluster.py#L248))

The time complexity of the average_clustering function with respect to the number of nodes (V) and number of edges (E) of the input graph G depends on the time complexity of the clustering function, as well as the time complexity of the average computation.

If the graph is represented as an adjacency matrix, the time complexity of the clustering function is O(V^3), and the time complexity of computing the average is O(V). Therefore, the overall time complexity of the average_clustering function would be O(V^3 + V), which is O(V^3).

If the graph is represented as an adjacency list, the time complexity of the clustering function is O(E^3), and the time complexity of computing the average is O(V). Therefore, the overall time complexity of the average_clustering function would be O(E^3 + V), which is O(E^3).



## Shortest Path

### `Dijkstra` - `O(V^2 + E log V)` - ([source](https://github.com/easy-graph/Easy-Graph/blob/19d2b0597efe18b405b13213294ce3a70202dc0d/easygraph/functions/path/path.py#L16))

The time complexity of the Dijkstra function with respect to the number of nodes (V) and number of edges (E) of the input graph G is O(V^2 + E log V). This is because the function uses a priority queue (implemented as a heap) to store the distances of the nodes from the source node, and the time complexity of inserting and extracting elements from a heap is O(log V). The function also iterates over all the edges once, so the time complexity is also O(E).

### `Floyd` - `O(V^3)` - ([source](https://github.com/easy-graph/Easy-Graph/blob/19d2b0597efe18b405b13213294ce3a70202dc0d/easygraph/functions/path/path.py#L43))

The time complexity of the Floyd function with respect to the number of nodes (V) and number of edges (E) of the input graph G is O(V^3). This is because the function uses a nested loop structure to iterate over all pairs of nodes, and the time complexity of this type of loop is O(V^2).

### `Prim` - `O(E log V)` - ([source](https://github.com/easy-graph/Easy-Graph/blob/19d2b0597efe18b405b13213294ce3a70202dc0d/easygraph/functions/path/path.py#L88))

The time complexity of the Prim function with respect to the number of nodes (V) and number of edges (E) of the input graph G is O(E log V). This is because the function uses a priority queue (implemented as a heap) to store the distances of the nodes from the source node, and the time complexity of inserting and extracting elements from a heap is O(log V). The function also iterates over all the edges once, so the time complexity is also O(E).

### `Kruskal` - `O(E log E)` - ([source](https://github.com/easy-graph/Easy-Graph/blob/19d2b0597efe18b405b13213294ce3a70202dc0d/easygraph/functions/path/path.py#L141))

The time complexity of the Kruskal function with respect to the number of nodes (V) and number of edges (E) of the input graph G is O(E log E). This is because the function sorts the edges by weight, and the time complexity of sorting is O(E log E). The function also iterates over all the edges once, so the time complexity is also O(E).

## Minimum Spanning Tree

### `minimum_spanning_tree` - ([source](https://github.com/easy-graph/Easy-Graph/blob/19d2b0597efe18b405b13213294ce3a70202dc0d/easygraph/functions/path/mst.py#L389))

The time complexity of the minimum_spanning_tree function depends on the algorithm used to find the minimum spanning tree. The function can use one of three algorithms: Kruskal's algorithm, Prim's algorithm, or Borůvka's algorithm.

Kruskal's algorithm has a time complexity of O(E log E) with respect to the number of edges (E) in the input graph.

Prim's algorithm has a time complexity of O(E log V) with respect to the number of edges (E) and the number of nodes (V) in the input graph.

Borůvka's algorithm has a time complexity of O(E log V) with respect to the number of edges (E) and the number of nodes (V) in the input graph.

Therefore, the overall time complexity of the minimum_spanning_tree function is O(E log E) for Kruskal's algorithm, O(E log V) for Prim's and Borůvka's algorithms, with respect to the number of edges (E) and the number of nodes (V) in the input graph.

## biconnected

### `is_biconnected` - `O(V + E)` - ([source](https://github.com/easy-graph/Easy-Graph/blob/19d2b0597efe18b405b13213294ce3a70202dc0d/easygraph/functions/components/biconnected.py#L16))

The time complexity of the is_biconnected function is O(V+E), where V is the number of nodes and E is the number of edges in the input graph. This is because the function performs a single depth-first search (DFS) on the graph, which has a time complexity of O(V+E).

### `biconnected_components` - `O(V + E)` - ([source](https://github.com/easy-graph/Easy-Graph/blob/19d2b0597efe18b405b13213294ce3a70202dc0d/easygraph/functions/components/biconnected.py#L44))

The time complexity of the biconnected_components function is also O(V+E), because it performs a single DFS on the graph and returns a list of the biconnected components, which is a linear operation with respect to the number of components.