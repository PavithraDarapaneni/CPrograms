## Write a function to count the number of occurrences of an element in a single linked list.
```c
#include<stdio.h>
#include<stdlib.h>
struct Node{
	int data;
	struct Node* next;
};
struct Node* createNode(int data)
{
	struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
	newNode ->data = data;
	newNode ->next = NULL;
	return newNode;
}
int countOccurances(struct Node* head, int key)
{
	int count = 0;
	struct Node*current = head;
	while(Current != NULL)
	{
		if(current ->data == key)
			count ++;
		current = current ->next;
	}
	return count;
}
void insertEnd(struct Node**head,int data)
{
	struct Node* newNode = createNode(data);
	if(*head == NULL)
	{
		temp = temp ->next;
	}
	temp ->next = newNode;
}
void displayList(struct Node* head)
{
	struct Node* temp = head;
	while(temp!= NULL)
	{
		printf("%d -> ",temp->data);
		temp = temp->next;
	}
	printf("NULL\n");
	int main()
	{
		struct Node* head = NULL;
		insertEnd(&head,1);
		insertEnd(&head,2);
		insertEnd(&head,3);
		insertEnd(&head,2);
		insertEnd(&head,2);
		insertEnd(&head,4);
		printf("Linked List: ");
		displayList(head);
		int key =2;
		printf("The element %d occurs %d times in the Linkedlist\n",key,countOccurances(head, key));
		return 0;
	}
	```
