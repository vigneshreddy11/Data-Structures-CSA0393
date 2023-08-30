#include <stdio.h>
#include <stdlib.h>
struct Graph {
    int V;
    int** adjMatrix;
};
struct Graph* createGraph(int V) {
    struct Graph* graph = (struct Graph*)malloc(sizeof(struct Graph));
    graph->V = V;
    graph->adjMatrix = (int**)malloc(V * sizeof(int*));
    for (int i = 0; i < V; i++) {
        graph->adjMatrix[i] = (int*)malloc(V * sizeof(int));
        for (int j = 0; j < V; j++) {
            graph->adjMatrix[i][j] = 0;
        }
    }
    return graph;
}
void addEdge(struct Graph* graph, int src, int dest) {
    graph->adjMatrix[src][dest] = 1;
    graph->adjMatrix[dest][src] = 1;
}
void DFS(struct Graph* graph, int startVertex, int* visited) {
    visited[startVertex] = 1;
    printf("%d ", startVertex);
    for (int i = 0; i < graph->V; i++) {
        if (graph->adjMatrix[startVertex][i] == 1 && visited[i] == 0) {
            DFS(graph, i, visited);
        }
    }
}
int main() {
    struct Graph* graph = createGraph(6);
    addEdge(graph, 0, 1);
    addEdge(graph, 0, 2);
    addEdge(graph, 1, 2);
    addEdge(graph, 2, 3);
    addEdge(graph, 3, 4);
    addEdge(graph, 4, 5);
    int* visited = (int*)malloc(graph->V * sizeof(int));
    for (int i = 0; i < graph->V; i++) {
        visited[i] = 0;
    }
    printf("Depth First Traversal: ");
    DFS(graph, 2, visited);
    return 0;
}
