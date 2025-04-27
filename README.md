<h1>ExpNo 2 : Implement Depth First Search Traversal of a Graph</h1> 
<h3>Name: </h3>
<h3>Register Number:     </h3>
<h3>Name: Janani Gowrisankar </h3>
<h3>Register Number: 212224100022    </h3>
<H3>Aim:</H3>
<p> To Implement Depth First Search Traversal of a Graph using Python 3.</p>
<h3>Theory:</h3>
@@ -54,6 +54,39 @@ Now, the Stack becomes empty, which means we have visited all the nodes, and our
 <li>If Not Visited, add it to the STACK. Else Call The Function Again Until No more nodes needs to be visited.</li>
</ol></B>

<h3>Program:</h3>

```

from collections import defaultdict

def dfs(graph, start, visited, path):
    path.append(start)
    visited[start] = True
    for neighbour in graph[start]:
        if not visited[neighbour]:
            dfs(graph, neighbour, visited, path)
    return path

graph = defaultdict(list)
n, e = map(int, input().split())
for _ in range(e):
    u, v = input().split()
    graph[u].append(v)
    graph[v].append(u)

# Optional: sort neighbors to get consistent order
for key in graph:
    graph[key].sort()

start = '0'
visited = defaultdict(bool)
path = []
traversed_path = dfs(graph, start, visited, path)
print(traversed_path)

```

<hr>
<h3>Sample Input</h3>
<hr>
8 9 <BR>
A B <BR>
A C <BR>
B E <BR>
C D <BR>
B D <BR>
C G <BR>
D F <BR>
G F <BR>
F H <BR>
<hr>
<h3>Sample Output</h3>
<hr>
['A', 'B', 'E', 'D', 'C', 'G', 'F', 'H']
<hr>
<hr>
<h3>Sample Input</h3>
<hr>
5 5 <BR>
0 1 <BR>
0 2 <BR>
0 3 <BR>
2 3 <BR>
2 4 <BR>
<hr>
<h3>Sample Output</h3>
<hr>
['0', '1', '2', '3', '4']
<hr>
<h3>Result:</h3>
<hr>
<p>Thus,a Graph was constructed and implementation of Depth First Search for the same graph was done successfully.</p>
