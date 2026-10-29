<h1>Experiment No. 2: Implement Depth First Search Traversal of a Graph</h1>

<h3>Name: PRANAV S</h3>
<h3>Register Number: 212224040242</h3>

<hr>

<h2>AIM</h2>
<p>To implement Depth First Search (DFS) traversal of a graph using Python 3.</p>

<hr>

<h2>THEORY</h2>

<h3>Depth First Search (DFS)</h3>

<p>
Depth First Search (DFS) is a graph traversal algorithm used to explore the vertices of a graph. It starts from a selected vertex and explores as far as possible along each branch before backtracking.
</p>

<p>
Unlike trees, graphs may contain cycles, so a visited array or set is used to ensure that each vertex is processed only once. DFS can be implemented using recursion or an explicit stack data structure.
</p>

<p>
In this experiment, a graph is constructed using the given vertices and edges. The DFS algorithm starts from a specified vertex, visits its unvisited adjacent vertices, and continues until all reachable vertices have been visited.
</p>

<h3>Steps Involved in DFS Traversal</h3>

<ol>
    <li>Initially, the stack and visited collection are empty.</li>
    <li>Visit the starting vertex and mark it as visited.</li>
    <li>Push its unvisited adjacent vertices onto the stack.</li>
    <li>Pop a vertex from the stack and visit it if it has not already been visited.</li>
    <li>Continue exploring adjacent vertices and backtrack when no unvisited adjacent vertices remain.</li>
    <li>Stop when the stack becomes empty.</li>
</ol>

<hr>

<h2>ALGORITHM</h2>

<ol>
    <li>Start the program.</li>
    <li>Read the number of vertices and edges.</li>
    <li>Construct the graph using an adjacency list.</li>
    <li>Read the starting vertex.</li>
    <li>Initialize an empty stack and a visited set.</li>
    <li>Push the starting vertex onto the stack.</li>
    <li>While the stack is not empty, pop a vertex from it.</li>
    <li>If the vertex has not been visited, mark it as visited and add it to the traversal list.</li>
    <li>Push its unvisited adjacent vertices onto the stack in reverse order to preserve the expected traversal order.</li>
    <li>Repeat until the stack is empty.</li>
    <li>Display the DFS traversal.</li>
    <li>Stop the program.</li>
</ol>

<hr>

<h2>PYTHON 3 PROGRAM</h2>

<pre><code class="language-python">
def dfs(graph, start):
    visited = set()
    stack = [start]
    traversal = []

    while stack:
        node = stack.pop()

        if node not in visited:
            visited.add(node)
            traversal.append(node)
            for neighbor in reversed(graph[node]):
                if neighbor not in visited:
                    stack.append(neighbor)

    return traversal
V, E = map(int, input().split())

graph = {}
for _ in range(E):
    u, v = input().split()

    if u not in graph:
        graph[u] = []
    if v not in graph:
        graph[v] = []

    graph[u].append(v)
    graph[v].append(u)

start = input("Enter starting vertex: ")

result = dfs(graph, start)

print(result)
</code></pre>

<hr>

<h2>SAMPLE INPUT 1</h2>

<pre><code>
8 9
A B
A C
B E
C D
B D
C G
D F
G F
F H
A
</code></pre>

<h2>SAMPLE OUTPUT 1</h2>

<pre><code>
['A', 'B', 'E', 'D', 'C', 'G', 'F', 'H']
</code></pre>

<hr>

<h2>SAMPLE INPUT 2</h2>

<pre><code>
5 5
0 1
0 2
0 3
2 3
2 4
0
</code></pre>

<h2>SAMPLE OUTPUT 2</h2>

<pre><code>
['0', '1', '2', '3', '4']
</code></pre>

<hr>

<h2>RESULT</h2>

<p>
Thus, a graph was constructed and Depth First Search (DFS) traversal was implemented successfully using Python 3. The program visits the vertices of the graph using a stack and a visited set.
</p>
