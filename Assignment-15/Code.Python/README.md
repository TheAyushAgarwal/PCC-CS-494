```python
class Graph:
    def __init__(self, edges, n):
        self.adjList = [[] for _ in range(n)]
        for (src, dest) in edges:
            self.adjList[src].append(dest)
            self.adjList[dest].append(src)
 
 
def hamiltonianPaths(graph, v, visited, path, n):
    if len(path) == n:
        print(path)
        return
    for w in graph.adjList[v]:
        if not visited[w]:
            visited[w] = True
            path.append(w)
            hamiltonianPaths(graph, w, visited, path, n)
            visited[w] = False
            path.pop()
 
 
def findHamiltonianPaths(graph, n):
    for start in range(n):
        path = [start]
        visited = [False] * n
        visited[start] = True
    
        hamiltonianPaths(graph, start, visited, path, n)
 
 
if __name__ == '__main__':
    edges = [(0, 1), (0, 2), (0, 3), (1, 2), (1, 3), (2, 3)]
    n = 4
    graph = Graph(edges, n)
 
    findHamiltonianPaths(graph, n)
```
 
