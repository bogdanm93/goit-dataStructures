# Depth-First Search (DFS) algorithm
def depth_first_search(graph, start_node):
    visited = set()
    stack = [start_node]
    traversal_path = []

    while stack:
        current_node = stack.pop()
        if current_node not in visited:
            visited.add(current_node)
            traversal_path.append(current_node)
            stack.extend(reversed(list(graph[current_node])))

    return traversal_path

# Breadth-First Search (BFS) algorithm
from collections import deque

def breadth_first_search(graph, start_node):
    visited = set()
    queue = deque([start_node])
    traversal_path = []

    while queue:
        current_node = queue.popleft()
        if current_node not in visited:
            visited.add(current_node)
            traversal_path.append(current_node)
            queue.extend(graph[current_node] - visited)

    return traversal_path

# Define the graph as an adjacency list for DFS and BFS
graph_adjacency_list = {
    0: {1, 2, 3, 4, 5},
    1: {0, 11, 12},
    2: {0, 21, 22},
    3: {0, 31, 32},
    4: {0, 41, 42},
    5: {0, 51, 52},
    11: {1},
    12: {1},
    21: {2},
    22: {2},
    31: {3},
    32: {3},
    41: {4},
    42: {4},
    51: {5},
    52: {5},
}

# Execute DFS and BFS
dfs_result = depth_first_search(graph_adjacency_list, 0)
bfs_result = breadth_first_search(graph_adjacency_list, 0)

# Output the results of DFS and BFS
print(f"DFS Traversal Path: {dfs_result}")
print(f"BFS Traversal Path: {bfs_result}")