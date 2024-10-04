# Step 1: Import necessary libraries
import networkx as nx
import matplotlib.pyplot as plt

# Step 2: Create the graph
graph = nx.Graph()

# Add the central node and peripheral nodes
central_node = 0
graph.add_node(central_node)
num_peripheral_nodes = 5

for i in range(1, num_peripheral_nodes + 1):
    graph.add_node(i)
    graph.add_edge(central_node, i)
    # Add two child nodes for each peripheral node
    child1 = i * 10 + 1
    child2 = i * 10 + 2
    graph.add_node(child1)
    graph.add_node(child2)
    graph.add_edge(i, child1)
    graph.add_edge(i, child2)

# Step 3: Visualize the graph
plt.figure(figsize=(10, 8))
position = nx.spring_layout(graph)
nx.draw(graph, position, with_labels=True, node_color='lightblue', node_size=700, edge_color='gray')
plt.title("Graph with Central Node and Two Children for Each Peripheral Node")
plt.show()

# Step 4: Graph analysis
total_nodes = graph.number_of_nodes()
total_edges = graph.number_of_edges()
node_degrees = dict(graph.degree())

print(f"Total number of nodes: {total_nodes}")
print(f"Total number of edges: {total_edges}")
print("Degree of each node:")
for node, degree in node_degrees.items():
    print(f"Node {node}: {degree}")

# Display degree distribution
degree_sequence = sorted([d for n, d in graph.degree()], reverse=True)
plt.figure(figsize=(10, 8))
plt.bar(range(len(degree_sequence)), degree_sequence, color='lightblue')
plt.title("Degree Distribution")
plt.xlabel("Node")
plt.ylabel("Degree")
plt.show()