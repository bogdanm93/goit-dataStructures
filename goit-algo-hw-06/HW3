import networkx as nx
import matplotlib.pyplot as plt
import heapq

# Initialize the graph with a central node and 2 children for each peripheral node
graph = nx.Graph()
center_node = 0
graph.add_node(center_node)
number_of_peripheral_nodes = 5

weighted_edges = []

for i in range(1, number_of_peripheral_nodes + 1):
    weight_to_peripheral = i  # Weight from central node to peripheral node
    weighted_edges.append((center_node, i, weight_to_peripheral))
    
    child_node1 = i * 10 + 1
    child_node2 = i * 10 + 2
    weight_to_child1 = i + 1  # Arbitrary weight to first child
    weight_to_child2 = i + 2  # Arbitrary weight to second child
    
    weighted_edges.append((i, child_node1, weight_to_child1))
    weighted_edges.append((i, child_node2, weight_to_child2))

# Add the edges with weights to the graph
graph.add_weighted_edges_from(weighted_edges)

# Visualize the graph with edge weights
positions = nx.spring_layout(graph)
plt.figure(figsize=(10, 8))
nx.draw(graph, positions, with_labels=True, node_color='skyblue', node_size=700, edge_color='gray')
edge_weights = nx.get_edge_attributes(graph, 'weight')
nx.draw_networkx_edge_labels(graph, positions, edge_labels=edge_weights)
plt.title("Graph with Weights")
plt.show()

# Dijkstra's algorithm for finding the shortest paths
def dijkstra_algorithm(graph, start_node):
    distances = {vertex: float('infinity') for vertex in graph}
    distances[start_node] = 0
    priority_queue = [(0, start_node)]
    
    while priority_queue:
        current_distance, current_node = heapq.heappop(priority_queue)
        
        if current_distance > distances[current_node]:
            continue
        
        for neighbor, weight in graph[current_node].items():
            distance = current_distance + weight['weight']
            
            if distance < distances[neighbor]:
                distances[neighbor] = distance
                heapq.heappush(priority_queue, (distance, neighbor))
    
    return distances

# Calculate the shortest paths from each vertex
shortest_paths = {}
for vertex in graph.nodes:
    shortest_paths[vertex] = dijkstra_algorithm(graph, vertex)

# Output the shortest paths
for start_node, distances in shortest_paths.items():
    print(f"Shortest paths from node {start_node}:")
    for end_node, distance in distances.items():
        print(f"  to node {end_node}: {distance}")
    print()