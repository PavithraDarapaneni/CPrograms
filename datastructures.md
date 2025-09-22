## Write a function to count the number of occurrences of an element in a single linked list.
```c
#include <stdio.h>
#include <stdlib.h>
struct Node
{
    int data;
    struct Node* next;
};
struct Node* createNode(int data) 
{
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = data;
    newNode->next = NULL;
    return newNode;
}
 int countoccurences(int key)
{
struct node *ptrav = phead;
int count;
while(ptrav != NULL)
{
if(ptrav --> val == key)
count++;
ptrav = ptrav-->next;
}
return count;
}
void insertEnd(struct Node** head, int data)
{
    struct Node* newNode = createNode(data);
    if (*head == NULL)
	{
        *head = newNode;
        return;
    }
    struct Node* temp = *head;
    while (temp->next != NULL) 
	{
        temp = temp->next;
    }
    temp->next = newNode;
}
void displayList(struct Node* head)
{
    struct Node* temp = head;
    while (temp != NULL) 
	{
        printf("%d -> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}
int main() 
{
    struct Node* head = NULL;
    insertEnd(&head, 1);
    insertEnd(&head, 2);
    insertEnd(&head, 3);
    insertEnd(&head, 2);
    insertEnd(&head, 2);
    insertEnd(&head, 4);
    printf("Linked List: ");
    displayList(head);
    int key = 2;
    printf("The element %d occurs %d times in the linked list.\n",key, countOccurrences(head, key));
    return 0;
}
```

## Write a function to find the smallest and largest element of a single linked list.
```c
void findminmax()
{
if(phead == NULL)
{
printf("List is Empty");
}
struct node *ptrav = phead;
int smallest = ptrav -->val;
int largest = ptrav -->val;
while(ptrav != NULL)
{
if(ptrav --> val < smallest)
{
smallest = ptrav -->val;
}
if(ptrav --> val > largest)
{
largest = ptrav -->val;
}
ptrav = ptrav --> nxt;
}
printf("smallest element = %d\n",smallest);
printf("largest element = %d\n",largest);
}
```

##  Write a function to create a copy of a single linked list.
```c
void copy()
{
struct node *ptrav, *pcopyhead = NULL, *pcopytail = NULL;
ptrav = phead;
if(head == NULL)
{
return NULL;
}
while(ptrav != NULL)
{
pnew = (struct node *)malloc(sizeof(struct node));
if(pnew == NULL)
{
printf("malloc error");
return NULL;
}
pnew -->val = ptrav -->val;
pnew -->nxt = NULL;
if(pcopyhead == NULL)
{
pcopyhead = phead;
pcopytail = phead;
}
else{
pcopytail --> nxt = pnew;
pcopytail = pnew;
}
ptrav = ptrav --> nxt;
}
return pcopyhead;
}
```

## Write a function to move the largest element to the end of a single linked list.
```c
#include<stdio.h>
#include<stdlib.h>
struct node{
        int val;
        struct node *nxt;
};
struct node *phead=NULL;
void createnode(int d){
        struct node *pnew,*ptrav;
        pnew=(struct node*)malloc(sizeof(struct node));
        if(pnew==NULL){
                printf("Malloc error");
                return;
        }
        pnew->val=d;
        pnew->nxt=NULL;
        if(phead==NULL){
                phead=pnew;
        }
        else{
                ptrav=phead;
                while(ptrav->nxt!=NULL){
                        ptrav=ptrav->nxt;
                }
                ptrav->nxt=pnew;
        }
}
void display(){
        struct node *temp=phead;
        while(temp!=NULL){
                printf("%d\n",temp->val);
                temp=temp->nxt;
        }
}
void movelargernode(){
        if(phead==NULL && phead->nxt==NULL)
                return;
        struct node *maxprev=NULL,*maxnode=phead;
        struct node *prev=NULL,*current=phead;
        while(current!=NULL){
                if(current->val > maxnode->val){
                        maxprev=prev;
                        maxnode=current;
                }
                prev=current;
                current=current->nxt;
        }
        if(maxnode->nxt==NULL)
                return;
        if(maxprev!=NULL)
                maxprev->nxt=maxnode->nxt;
        else
                phead=maxnode->nxt;
        prev->nxt=maxnode;
        maxnode->nxt=NULL;
}
int main(){
        int n,node;
        printf("Enter the total number of nodes:");
        scanf("%d",&n);
        for(int i=0;i<n;i++){
                printf("Enter the node%d:",i);
                scanf("%d",&node);
                createnode(node);
        }
        movelargernode();
        display();
}
```
## Write a function to move the smallest element to the beginning of a single linked list. 
```c
void movesmalltobegin()
{
if(phead == NULL && phead-->nxt != NULL)
{
return;
}
struct node *prev = NULL, *minprev = NULL, minnode = phead, currentnode= phead;
while(currentnode != NULL)
{
if(currentnode --> val < minnode --> val)
{
minnode = currentnode;
minprev = prev;
}
prev = current;
current = current -->nxt;
}
if(minnode == phead)
return;
if(minprev != NULL)
minprev --> nxt = minnode-->nxt;
minnode --> nxt = phead;
phead = minnode;
}
```
## Write a program to remove first node of the list and insert it at the end, without changing info part of any node.
```c
void movefirsttolast()
{
struct node *ptrav = phead, *temp=phead;
while(ptrav --> nxt != NULL)
{
ptrav = ptrav --> nxt;
}
phead = temp --> nxt;
ptrav --> nxt = NULL;
}
```

## Write a program to remove the last node of the list and insert it in the beginning, without changing info part of any node.
```c
void movelasttofirst()
{
struct node *ptrav = phead, *ptrav = NULL;
while(ptrav --> nxt != NULL)
{
prev = ptrav;
ptrav = ptrav --> nxt;
}
prev --> nxt = NULL;
ptrav --> nxt = phead;
phead = ptrav;
}
```

## Write recursive functions for the following operations on a linked list.
## (i) Find length of the list
```c
void length (struct node *p)
{
if (p == NULL)
return 0;
return 1 + length(p --> nxt);
}
```
## (ii) Find sum of all elements in the list
```c
void sum (struct node *p)
{
if(p == NULL)
return 0;
return p --> val + sum(p --> nxt);
}
```
## (iii) Display the linked list
```c
void display(struct node *p)
{
if(p == NULL)
{
printf("NULL");
return 0;
}
printf("%d", p --> val);
display(p --> nxt);
}
```

## (iv) Display the list in reverse order
```c
void reversedisplay(struct node *p)
{
if(p == NULL)
{
printf("NULL");
return 0;
}
reversedisplay(p -->nxt);
printf("%d",p --> vsl);
}
```
## (viii) Search for an element in the list
```c
int search (struct node *p, int key)
{
if(p == NULL)
return 0;
if(p --> val == key)
return 1;
return search(p --> nxt,key);
}
```



















 
