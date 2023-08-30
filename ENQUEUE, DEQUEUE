#include <stdio.h>
#include <stdlib.h>
#define MAX 5
int queue[MAX];
int front = -1;
int rear = -1;
void enqueue(int data) {
   if(rear == MAX-1) {
      printf("Queue is full!\n");
   } else {
      if(front == -1) {
         front = 0;
      }
      rear++;
      queue[rear] = data;
   }
}
void dequeue() {
   if(front == -1 || front > rear) {
      printf("Queue is empty!\n");
   } else {
      printf("Dequeued element: %d\n", queue[front]);
      front++;
   }
}
void display() {
   if(front == -1 || front > rear) {
      printf("Queue is empty!\n");
   } else {
      int i;
      printf("Queue elements: ");
      for(i=front; i<=rear; i++) {
         printf("%d ", queue[i]);
      }
      printf("\n");
   }
}
int main() {
   int choice, data;
   while(1) {
      printf("1. Enqueue\n");
      printf("2. Dequeue\n");
      printf("3. Display\n");
      printf("4. Exit\n");
      printf("Enter your choice: ");
      scanf("%d", &choice);
      switch(choice) {
         case 1:
            printf("Enter data to enqueue: ");
            scanf("%d", &data);
            enqueue(data);
            break;
         case 2:
            dequeue();
            break;
         case 3:
            display();
            break;
         case 4:
            exit(0);
         default:
            printf("Invalid choice!\n");
            break;
      }
   }

   return 0;
}
