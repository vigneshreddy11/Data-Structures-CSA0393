#include <stdio.h>
#include <stdlib.h>
#include <limits.h>

#define V 6 // Number of vertices in the graph

// Function to find the vertex with the minimum distance value
int minDistance(int dist[], int visited[]) {
    int min = INT_MAX, min_index;

    for (int v = 0; v < V; v++)
        if (visited[v] == 0 && dist[v] <= min)
            min = dist[v], min_index = v;

    return min_index;
}

// Function to print the shortest path from source to destination
void printPath(int parent[], int j) {
    if (parent[j] == -1)
        return;

    printPath(parent, parent[j]);

    printf("%d ", j);
}

// Function to print the solution
void printSolution(int dist[], int n, int parent[], int src) {
    printf("Vertex   Distance from Source   Path\n");
    for (int i = 0; i < V; i++) {
        printf("%d \t\t %d \t\t\t\t ", i, dist[i]);
        printPath(parent, i);
        if (i != src)
            printf("%d ", src);
        printf("\n");
    }
}

// Dijkstra's algorithm to find the shortest path in a graph
void dijkstra(int graph[V][V], int src) {
    int dist[V];
    int visited[V];
    int parent[V];

    for (int i = 0; i < V; i++) {
        dist[i] = INT_MAX;
        visited[i] = 0;
        parent[i] = -1;
    }

    dist[src] = 0;

    for (int count = 0; count < V - 1; count++) {
        int u = minDistance(dist, visited);
        visited[u] = 1;

        for (int v = 0; v < V; v++) {
            if (visited[v] == 0 && graph[u][v] && dist[u] != INT_MAX && dist[u] + graph[u][v] < dist[v]) {
                dist[v] = dist[u] + graph[u][v];
                parent[v] = u;
            }
        }
    }

    printSolution(dist, V, parent, src);
}

// Driver program
int main() {
    int graph[V][V] = {{0, 3, 5, 0, 0, 0},
                       {3, 0, 1, 7, 0, 0},
                       {5, 1, 0, 2, 1, 0},
                       {0, 7, 2, 0, 4, 2},
                       {0, 0, 1, 4, 0, 6},
                       {0, 0, 0, 2, 6, 0}};

    dijkstra(graph, 0);

    return 0;
}
