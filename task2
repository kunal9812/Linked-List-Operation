#include<stdio.h>
#include<stdlib.h>

// Node structure
struct Node {
    int data;
    struct Node* next;
};

struct Node * headinsersion(struct Node * head, int newdata){
    struct Node *newnode = (struct Node *)malloc(sizeof(struct Node));
    newnode -> data = newdata;
    newnode -> next = head;

    return newnode;
}

struct Node * insersionatIndex(struct Node * head, int newdata, int Index){
    struct Node *newnode = (struct Node *)malloc(sizeof(struct Node));
    newnode -> data = newdata;
    struct Node * ptr = head;
    int i = 0;
    while(i != Index - 1){
        ptr = ptr -> next;
        i++;
    }
    newnode -> next = ptr -> next;
    ptr -> next = newnode;

    return head;
}

struct Node * insersionatEnd(struct Node * head, int newdata){
    struct Node *newnode = (struct Node *)malloc(sizeof(struct Node));
    newnode -> data = newdata;
    struct Node * p = head;

    while(p -> next!= NULL){
        p = p -> next;
    }

    p -> next = newnode;
    newnode -> next = NULL;

    return head;
}

void delete(struct Node** head, int value) {
    struct Node* temp = *head, *prev = NULL;

    if (temp != NULL && temp->data == value) {
        *head = temp->next;
        free(temp);
        return;
    }

    while (temp != NULL && temp->data != value) {
        prev = temp;
        temp = temp->next;
    }

    if (temp == NULL) return;

    prev->next = temp->next;
    free(temp);
}

void traverse(struct Node* head) {
    printf("Linked List: ");
    while (head != NULL) {
        printf("%d -> ", head->data);
        head = head->next;
    }
    printf("NULL\n");
}

int main() {
    struct Node* head, *second, *third;
    int choice, value, value1, value2, value3, choice2, index;

    head = (struct Node *)malloc(sizeof(struct Node));
    second = (struct Node *)malloc(sizeof(struct Node));
    third = (struct Node *)malloc(sizeof(struct Node));

    printf("Enter the value for First node : \n");
    scanf("%d",&value1);
    head -> data = value1;
    head -> next = second;

    printf("Enter the value for second node : \n");
    scanf("%d",&value2);
    second -> data = value2;
    second -> next = third;

    printf("Enter the value for third node : \n");
    scanf("%d",&value3);
    third -> data = value1;
    third -> next = NULL;

    printf("Linked List Operations : \n");

    while (1) {
        printf("\n1. Insert\n2. Delete\n3. Traverse\n4. Exit\nEnter choice: ");
        scanf("%d", &choice);
        switch (choice) {
            case 1:
                printf("\n1. Insert at First Position\n2. insert at Given Index \n3. Insert at End\nEnter choice: ");
                scanf("%d",&choice2);
                switch (choice2){
                    case 1: 
                        printf("Enter value to insert: ");
                        scanf("%d", &value);
                        head = headinsersion(head,value);
                        break;
                    
                    case 2:
                        printf("Enter value to insert: ");
                        scanf("%d", &value);
                        printf("Enter value to Index: ");
                        scanf("%d", &index);
                        head = insersionatIndex(head, value, index);
                        break;
                    
                    case 3:
                        printf("Enter value to insert: ");
                        scanf("%d", &value);
                        head = insersionatEnd(head,value);
                        break;

                    default:
                        printf("Invalid choice!\n");

                }
                break;

            case 2:
                printf("Enter value to delete: ");
                scanf("%d", &value);
                delete(&head, value);
                break;

            case 3:
                traverse(head);
                break;

            case 4:
                exit(0);

            default:
                printf("Invalid choice!\n");
        }
    }
    return 0;
}
