#include <stdio.h>
#include <stdlib.h>

#define TABLE_SIZE 10

struct Node {
    int key;
    int value;
};

struct Node* hashTable[TABLE_SIZE];

int hashFunction(int key) {
    return key % TABLE_SIZE;
}

void insert(int key, int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->key = key;
    newNode->value = value;

    int index = hashFunction(key);

    while (hashTable[index] != NULL) {
        index = (index + 1) % TABLE_SIZE;
    }

    hashTable[index] = newNode;
}

int search(int key) {
    int index = hashFunction(key);

    while (hashTable[index] != NULL) {
        if (hashTable[index]->key == key) {
            return hashTable[index]->value;
        }

        index = (index + 1) % TABLE_SIZE;
    }

    return -1;
}

void display() {
    printf("Hash Table:\n");
    printf("-----------\n");

    for (int i = 0; i < TABLE_SIZE; i++) {
        if (hashTable[i] != NULL) {
            printf("%d -> %d\n", hashTable[i]->key, hashTable[i]->value);
        } else {
            printf("%d -> NULL\n", i);
        }
    }
}

int main() {
    for (int i = 0; i < TABLE_SIZE; i++) {
        hashTable[i] = NULL;
    }

    insert(10, 5);
    insert(25, 10);
    insert(35, 15);
    insert(16, 20);
    insert(26, 25);

    display();

    int key = 16;
    int value = search(key);
    if (value != -1) {
        printf("Value for key %d is %d\n", key, value);
    } else {
        printf("Key not found in hash table\n");
    }

    return 0;
}
