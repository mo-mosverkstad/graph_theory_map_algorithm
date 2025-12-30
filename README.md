# Graph Theory Algorithms

A collection of Python implementations for fundamental graph theory algorithms and data structures.

## Overview

This repository contains implementations of various graph theory concepts including:
- Graph data structure with basic operations
- Eulerian path detection
- Additional algorithms (planned: Dijkstra's algorithm, 4-color problem)

## Structure

```
graph_theory_map_algorithm/
├── raw/
│   ├── eulerian/
│   │   └── eulerian.py          # Eulerian path detection
│   └── graph/
│       ├── graph.py             # Graph class implementation
│       └── test.py              # Unit tests for graph operations
└── README.md
```

## Implementations

### 1. Graph Data Structure (`raw/graph/graph.py`)

A basic undirected graph implementation with the following operations:

**Features:**
- Add vertices to the graph
- Add edges between vertices (undirected)
- Delete edges and vertices
- Internal validation for vertex and neighbor relationships

**Usage:**
```python
from graph import Graph

g = Graph()
g.add_vertex(1)
g.add_vertex(2)
g.add_edge(1, 2)
print(g)  # {1: [2], 2: [1]}
```

**Methods:**
- `add_vertex(vertex)`: Add a new vertex to the graph
- `add_edge(start, end)`: Add an undirected edge between two vertices
- `delete_edge(start, end)`: Remove an edge between two vertices
- `delete_vertex(vertex)`: Remove a vertex and all its connections

### 2. Eulerian Path Detection (`raw/eulerian/eulerian.py`)

Implements Eulerian path detection based on the mathematical property that a graph has an Eulerian path if and only if it has exactly 0 or 2 vertices with odd degree.

**Features:**
- Check if a graph has an Eulerian path or circuit
- Identify vertices with odd degree
- Returns both the result and the list of odd-degree vertices

**Usage:**
```python
graph = {1:[2,3,5], 2:[1,3], 3:[1,4,5], 4:[2,3], 5:[1,3]}
result, odd_vertices = check_eulerian(graph)
print(f"Has Eulerian path: {result}, Odd vertices: {odd_vertices}")
```

**Algorithm Logic:**
- A graph has an Eulerian circuit if all vertices have even degree (0 odd vertices)
- A graph has an Eulerian path if exactly 2 vertices have odd degree
- Otherwise, no Eulerian path exists

## Testing

The repository includes comprehensive tests for the graph data structure:

```bash
cd raw/graph
python test.py
```

Test cases cover:
- Adding vertices and edges
- Deleting edges and vertices
- Error handling for invalid operations
- Edge cases and boundary conditions

## Requirements

- Python 3.x
- No external dependencies required

## Running the Code

### Graph Operations
```bash
cd raw/graph
python test.py
```

### Eulerian Path Detection
```bash
cd raw/eulerian
python eulerian.py
```

## Future Implementations

Planned algorithms to be added:
- **Dijkstra's Algorithm**: Shortest path finding in weighted graphs
- **4-Color Problem**: Graph coloring algorithm
- **Additional graph traversal algorithms** (BFS, DFS)
- **Minimum Spanning Tree algorithms** (Kruskal's, Prim's)

## Contributing

Feel free to contribute by:
1. Adding new graph algorithms
2. Improving existing implementations
3. Adding more comprehensive tests
4. Optimizing performance

## License

This project is for educational purposes and practice with graph theory algorithms.