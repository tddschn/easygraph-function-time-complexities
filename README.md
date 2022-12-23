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

It's worth noting that these time complexities are for the worst case scenario, and the actual time complexity may be lower in practice, depending on the specific input graph and the implementation of the algorithm.

### `average_clustering` - `O(V^3)` ([source](https://github.com/easy-graph/Easy-Graph/blob/19d2b0597efe18b405b13213294ce3a70202dc0d/easygraph/functions/basic/cluster.py#L248))

The time complexity of the average_clustering function with respect to the number of nodes (V) and number of edges (E) of the input graph G depends on the time complexity of the clustering function, as well as the time complexity of the average computation.

If the graph is represented as an adjacency matrix, the time complexity of the clustering function is O(V^3), and the time complexity of computing the average is O(V). Therefore, the overall time complexity of the average_clustering function would be O(V^3 + V), which is O(V^3).

If the graph is represented as an adjacency list, the time complexity of the clustering function is O(E^3), and the time complexity of computing the average is O(V). Therefore, the overall time complexity of the average_clustering function would be O(E^3 + V), which is O(E^3).

It's worth noting that these time complexities are for the worst case scenario, and the actual time complexity may be lower in practice, depending on the specific input graph and the implementation of the algorithm.