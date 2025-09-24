## 1.Creation of a single node.
```c
#include<stdio.h>
#include<stdlib.h>
struct node{
        int val;
        struct node *nxt;
};
struct node *phead=NULL;
int main(){
        phead=(struct node*)malloc(sizeof(struct node));
        phead->val=10;
        phead->nxt=NULL;
        printf("%d",phead->val);
}
```
## 2.Create  n nodes using Linked List.
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
int main(){
        int n,node;
        printf("Enter the total number of nodes");
        scanf("%d",&n);
        for(int i=0;i<n;i++){
                printf("Enter the node%d:",i);
                scanf("%d",&node);
                createnode(node);
        }
        display();
}
```
## 3.Adding a node at the end of the linked list
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
void Addnodeattail(int a){
        struct node *pretrav,*new;
        new=(struct node*)malloc(sizeof(struct node));
        if(new==NULL){
                printf("malloc error");
                return;
        }
        new->val=a;
        new->nxt=NULL;
        if(phead==NULL){
                phead=new;
        }
        else{
                pretrav=phead;
                while(pretrav->nxt!=NULL){
                     pretrav=pretrav->nxt;
                }
                pretrav->nxt=new;
        }
}
void display(){
        struct node *temp=phead;
        while(temp!=NULL){
                printf("%d\n",temp->val);
                temp=temp->nxt;
        }
}
int main(){
        createnode(10);
        createnode(20);
        createnode(30);
        createnode(40);
        createnode(50);
        Addnodeattail(60);
        display();
}
```
## 4. Adding a node at the beginning of the linked list.
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
void Addingnodeathead(int a){
        struct node *new;
        new=(struct node*)malloc(sizeof(struct node));
        if(new==NULL){
                printf("Malloc error");
                return;
        }
        new->val=a;
        new->nxt=phead;
        phead=new;
}
void display(){
        struct node *temp=phead;
        while(temp!=NULL){
                printf("%d\n",temp->val);
                temp=temp->nxt;
        }
}
int main(){
        createnode(10);
        createnode(20);
        createnode(30);
        createnode(40);
        createnode(50);
        Addingnodeathead(60);
        display();
}
```
## 5.Delete a node at the end of the Linked list.
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
void deletenodeatend(){
        struct node *pretrav,*trav;
        trav=phead;
        while(trav->nxt!=NULL){
                pretrav=trav;
                trav=trav->nxt;
        }
        free(trav);
        pretrav->nxt=NULL;
        trav=NULL;
}
void display(){
        struct node *temp=phead;
        while(temp!=NULL){
                printf("%d\n",temp->val);
                temp=temp->nxt;
        }
}
int main(){
        createnode(10);
        createnode(20);
        createnode(30);
        createnode(40);
        createnode(50);
        deletenodeatend();
        display();
}
```
## 6.Delete a node at the beginning of the Linked list.
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
void deletenodeathead(){
        struct node *ptemp;
        ptemp=phead;
        phead=phead->nxt;
        free(ptemp);
        ptemp=NULL;
}
void display(){
        struct node *temp=phead;
        while(temp!=NULL){
                printf("%d\n",temp->val);
                temp=temp->nxt;
        }
}
int main(){
        createnode(10);
        createnode(20);
        createnode(30);
        createnode(40);
        createnode(50);
        deletenodeathead();
        display();
}
```
## 7.Insertion of node at a particular position of the Linked list.
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
                printf("Error");
                return;
        }
        pnew->val=d;
        pnew->nxt=NULL;
        if(phead==NULL){
                phead=pnew;
                return;
        }
        else{
                ptrav=phead;
                while(ptrav->nxt != NULL){
                        ptrav=ptrav->nxt;
                }
                ptrav->nxt=pnew;
        }
}
void insertnode(int pos,int n,int d){
        struct node *temp,*pnew,*ins;
        if(pos>n || pos<1){
                printf("Invalid position");
                return;
        }
        else{
                pnew=(struct node*)malloc(sizeof(struct node));
                if(pnew==NULL){
                        printf("Error");
                        return;
                }
                pnew->val=d;
                pnew->nxt=NULL;
                if(pos==1){
                        temp=phead;
                        phead=pnew;
                        pnew->nxt=temp;
                }
                else{
                        temp=phead;
                        for(int i=1;i<pos-1;i++){
                                temp=temp->nxt;
                        }
                        ins=temp->nxt;
                        temp->nxt=pnew;
                        pnew->nxt=ins;
                }
        }
}
void display(){
        struct node *ptrav=phead;
        while(ptrav!=NULL){
                printf("%d->",ptrav->val);
                ptrav=ptrav->nxt;
        }
        printf("NULL");
}
int main(){
        int n,node,pos,d;
        printf("Enter total number of nodes:");
        scanf("%d",&n);
        for(int i=0;i<n;i++){
                printf("Enter the node%d : ",i+1);
                scanf("%d",&node);
                createnode(node);
        }
        display();
        printf("\n");
        printf("Enter the position to insert:");
        scanf("%d",&pos);
        printf("Enter the element to insert:");
        scanf("%d",&d);
        insertnode(pos,n,d);
        display();
}
```
## 8.Insertion of node at a middle position of the Linked list.
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
        pnew=(struct node *)malloc(sizeof(struct node));
        if(pnew==NULL){
                printf("malloc error");
                return;
        }
        pnew->val=d;
        pnew->nxt=NULL;
        if(phead==NULL){
                phead=pnew;
        }
        else{
                ptrav=phead;
                while(ptrav->nxt != NULL){
                        ptrav=ptrav->nxt;
                }
                ptrav->nxt=pnew;
        }
}
void middlenodeinsertion(int d){
    struct node *pnew,*prev,*slow,*fast;
    slow=fast=phead;
    pnew=(struct node*)malloc(sizeof(struct node));
    if(pnew==NULL){
            printf("malloc error");
            return;
    }
    pnew->val=d;
    pnew->nxt=NULL;
    while(fast!=NULL&&fast->nxt!=NULL){
            prev=slow;
            slow=slow->nxt;
            fast=fast->nxt->nxt;
    }
    pnew->nxt=prev->nxt;
    prev->nxt=pnew;
    return;
}
void display(){
        struct node *ptemp;
        ptemp=phead;
        while(ptemp!=NULL){
                printf("%d ",ptemp->val);
                ptemp=ptemp->nxt;
        }
}
int main(){
        int n,data,in,x;
        printf("Enter the total number of nodes: ");
        scanf("%d",&n);
        for(int i=0;i<n;i++){
                printf("Enter the data in the node:");
                scanf("%d",&data);
                createnode(data);
        }
        printf("Enter the insertion value:");
        scanf("%d",&in);
        middlenodeinsertion(in);
        printf("The elements in the list are:");
        display();
}
```
## 9.Deletion of middle node using Linked list.
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
        struct node *ptrav;
        ptrav=phead;
        while(ptrav!=NULL){
                printf("%d ",ptrav->val);
                ptrav=ptrav->nxt;
        }
}
void deletenode(){
        struct node *prev,*slow,*fast,*temp,*pnew;
        slow=fast=phead;
        if(phead==NULL||phead->nxt==NULL){
                printf("It have 0 or 1 node");
                return;
        }
        while(fast!=NULL&&fast->nxt!=NULL){
                prev=slow;
                slow=slow->nxt;
                fast=fast->nxt->nxt;
        }
        temp=prev->nxt;
        prev->nxt=prev->nxt->nxt;
        free(temp);
}
int main(){
        int n,data;
        printf("Enter total number of nodes:");
        scanf("%d",&n);
        printf("Enter the values of the nodes:");
        for(int i=0;i<n;i++){
                printf("Enter the value at node");
                scanf("%d",&data);
                createnode(data);
        }
        deletenode();
        display();
}
```
## 10.Reversing of linked list.
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
void reverse(){
        struct node *prev=NULL,*current=phead,*temp=NULL;
        while(current!=NULL){
                temp=current->nxt;
                current->nxt=prev;
                prev=current;
                current=temp;
        }
        phead=prev;
}
void display(){
        struct node *temp=phead;
        while(temp!=NULL){
                printf("%d\n",temp->val);
                temp=temp->nxt;
        }
}
int main(){
        int n,data;
        printf("Enter the total number of nodes:");
        scanf("%d",&n);
        printf("Enter the values in the nodes:");
        for(int i=0;i<n;i++){
                scanf("%d",&data);
                createnode(data);
        }
        printf("List after revesing:\n");
        reverse();
        display();
}
```
## 11.Sorting of Linked list.
```c
#include<stdio.h>
#include<stdlib.h>
struct node{
        int val;
        struct node *nxt;
};
struct node *phead=NULL;
void insertnode(int d){
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
                return;
        }
        else{
                ptrav=phead;
                while(ptrav->nxt!=NULL){
                        ptrav=ptrav->nxt;
                }
                ptrav->nxt=pnew;
        }
}
void sorted(){
        struct node *i,*j;
        int temp;
        for(i=phead;i!=NULL;i=i->nxt){
                for(j=i->nxt;j!=NULL;j=j->nxt){
                        if(i->val>j->val){
                                temp=i->val;
                                i->val=j->val;
                                j->val=temp;
                        }
                }
        }
}
void display(){
        struct node *ptrav;
        ptrav=phead;
        while(ptrav!=NULL){
                printf("%d ",ptrav->val);
                ptrav=ptrav->nxt;
        }
}

int main(){
        int n,data;
        printf("Enter the total number of nodes:");
        scanf("%d",&n);
        for(int i=0;i<n;i++){
                printf("Enter the node:");
                scanf("%d",&data);
                insertnode(data);
        }
        printf("Sorted Array:");
        sorted();
        display();
}
```
## 12.Merging and sorting of an array.
```c
#include<stdio.h>
#include<stdlib.h>
struct node{
        int val;
        struct node *nxt;
};
struct node *phead1=NULL;
struct node *phead2=NULL;
struct node* merge(struct node *phead1,struct node *phead2){
        if(phead1==NULL)
                return phead2;
        if(phead2==NULL)
                return phead1;
        struct node *result;
        if(phead1->val<=phead2->val){
                result=phead1;
                result->nxt=merge(phead1->nxt,phead2);
        }
        else{
                result=phead2;
                result->nxt=merge(phead1,phead2->nxt);
        }
        return result;
}
int createnode(int d,struct node **phead){
        struct node *pnew,*ptrav;
        pnew=(struct node*)malloc(sizeof(struct node));
        if(pnew==NULL){
                printf("Malloc error");
                return 0;
        }
        pnew->val=d;
        pnew->nxt=NULL;
        if(*phead==NULL){
                *phead=pnew;
                return 0;
        }
        else{
                ptrav=*phead;
                while(ptrav->nxt!=NULL){
                        ptrav=ptrav->nxt;
                }
                ptrav->nxt=pnew;
        }
}
void display(struct node *phead){
        struct node *ptrav=phead;
        while(ptrav!=NULL){
                printf("%d->",ptrav->val);
                ptrav=ptrav->nxt;
        }
        printf("NULL");
}
int main(){
        struct node *result;
        int n1,n2,node;
        printf("Enter the total number of nodes in linkedlist1:");
        scanf("%d",&n1);
        for(int i=0;i<n1;i++){
                printf("Enter the node%d:",i+1);
                scanf("%d",&node);
                createnode(node,&phead1);
        }
        printf("1st Linked list : ");
        display(phead1);
        printf("\n");
        printf("Enter the total number of nodes in linkedlist2:");
        scanf("%d",&n2);
        for(int i=0;i<n2;i++){
                printf("Enter the node%d:",i+1);
                scanf("%d",&node);
                createnode(node,&phead2);
        }
        printf("2nd Linked list : ");
        display(phead2);
        printf("\n");
        result=merge(phead1,phead2);
        display(result);
        printf("\n");
}

```
## 13.Count the number of nodes in a linked list.
```c
#include<stdio.h>
#include<stdlib.h>
struct node{
        int val;
        struct node *nxt;
};
struct node *phead=NULL;
void insertnode(int d){
        struct node *pnew,*ptrav;
        pnew=(struct node *)malloc(sizeof(struct node));
        if(pnew==NULL){
                printf("malloc error");
                return;
        }
        pnew->val=d;
        pnew->nxt=NULL;
        if(phead==NULL){
                phead=pnew;
                return;
        }
        else{
                ptrav=phead;
                while(ptrav->nxt!=NULL){
                        ptrav=ptrav->nxt;
                }
                ptrav->nxt=pnew;
        }
}
void count(){
        struct node *ptrav;
        int count=0;
        ptrav=phead;
        while(ptrav!=NULL){
                ptrav=ptrav->nxt;
                count++;
        }
        printf("count of the nodes:%d\n",count);
}
void display(){
        struct node *ptrav;
        ptrav=phead;
        while(ptrav!=NULL){
                printf("%d ",ptrav->val);
                ptrav=ptrav->nxt;
        }
        printf("\n");
}
int main(){
        insertnode(10);
        insertnode(20);
        insertnode(30);
        insertnode(40);
        insertnode(50);
        display();
        count();
        return 0;
}
```
## 14.Search for an element in a linked list.
```c
#include<stdio.h>
#include<stdlib.h>
struct node{
        int val;
        struct node *nxt;
};
struct node *phead=NULL;
void insertnode(int d){
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
                return;
        }
        else{
                ptrav=phead;
                while(ptrav->nxt!=NULL){
                        ptrav=ptrav->nxt;
                }
                ptrav->nxt=pnew;
        }
}
void search(int d){
        struct node *ptrav;
        int pos=1;
        ptrav=phead;
        while(ptrav!=NULL){
                if(ptrav->val==d){
                        printf("%d elements is at %d position",d,pos);
                        return;
                }
                pos++;
                ptrav=ptrav->nxt;
        }
        printf("Element is not found");

}
int main(){
        int n,data,node;
        printf("Enter the total number of nodes:");
        scanf("%d",&n);
        for(int i=0;i<n;i++){
                printf("Enter the node:");
                scanf("%d",&data);
                insertnode(data);
        }
        printf("Enter the node to search:");
        scanf("%d",&node);
        search(node);
}
```
## 15.Detect a loop in the linked list.
```c
#include<stdio.h> 
#include<stdlib.h>
struct node{
        int val;
        struct node *nxt;
};
struct node *phead=NULL;
void insertnode(int d){
        struct node *pnew,*ptrav;
        pnew=(struct node*)malloc(sizeof(struct node));
        if(pnew==NULL){
                printf("malloc error");
                return;
        }
        pnew->val=d;
        pnew->nxt=NULL;
        if(phead==NULL){
                phead=pnew;
                return;
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
        struct node *ptrav=phead;
        while(ptrav!=NULL){
                printf("%d ",ptrav->val);
                ptrav=ptrav->nxt;
        }
}
void loop(int x){
        struct node *ptrav=phead,*temp;
        int count=0;
        while(count!=x){
                ptrav=ptrav->nxt;
                count++; 
        }
        temp=ptrav;
        ptrav=phead;
        while(ptrav->nxt!=NULL){
                ptrav=ptrav->nxt;
        }
        ptrav->nxt=temp;
        return;
}
int detectloop(){
        struct node *slow,*fast;
        slow=fast=phead;
        while(fast!=NULL&&fast->nxt!=NULL){
                slow=slow->nxt;
                fast=fast->nxt->nxt;
                if(slow==fast)
                        return 1;
        }
        return 0;
}
int main(){
        int n,data,x,a;
        printf("Enter the total number of nodes:");
        scanf("%d",&n);
        for(int i=0;i<n;i++){
                printf("Enter the node:");
                scanf("%d",&data);
                insertnode(data);
        }
        display();
        printf("Enter the index of the node to create loop:");
        scanf("%d",&x);
        loop(x);
        a=detectloop();
        if(a){
                printf("Loop is detected");
        }
        else{
                printf("Loop is not detected");
        }
}
```
## 16.Write a function to count the number of occurrences of an element in a single linked list.
```c
#include<stdio.h>
#include<stdlib.h>
struct node{
        int val;
        struct node *nxt;
};
struct node *phead=NULL;
void insertnode(int d){
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
                return;
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
        struct node *ptrav=phead;
        while(ptrav!=NULL){
                printf("%d ",ptrav->val);
                ptrav=ptrav->nxt;
        }
}
int countoccurrences(int key){
        struct node *ptrav=phead;
        int count=0;
        while(ptrav!=NULL){
                if(ptrav->val==key){
                        count++;
                }
                ptrav=ptrav->nxt;
        }
        return count;
}
int main(){
        int n,node,count,value;
        printf("Enter the total number of nodes:");
        scanf("%d",&n);
        for(int i=0;i<n;i++){
                printf("Enter the node%d :",i);
                scanf("%d",&node);
                insertnode(node);
        }
        printf("Values in the linked list are:");
        display();
        printf("\n");
        printf("Enter the value to count its occurrences:");
        scanf("%d",&value);
        count=countoccurrences(value);
        printf("%d occurrs in %d times\n",value,count);
}
```
## 17.Write a function to find the smallest and largest element of a single linked list.
```c
#include<stdio.h>
#include<stdlib.h>
struct node{
        int val;
        struct node *nxt;
};
void insertnode(int d){
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
                return;
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
        struct node *ptrav=phead;
        while(ptrav!=NULL){
                printf("%d ",ptrav->val);
                ptrav=ptrav->nxt;
        }
}
void findminmax(){
        if(phead==NULL){
                printf("List is empty");
                return;
        }
        struct node *ptrav=phead;
        int min=ptrav->val;
        int max=ptrav->val;
        while(ptrav!=NULL){
                if(ptrav->val<min){
                        min=ptrav->val;
                }
                if(ptrav->val>max){
                        max=ptrav->val;
                }
                ptrav=ptrav->nxt;
        }
        printf("Smallest element in the linked list:%d\n",min);
        printf("Largest element in the linked list:%d\n",max);
}
int main(){
        int n,node,count,value;
        printf("Enter the total number of nodes:");
        scanf("%d",&n);
        for(int i=0;i<n;i++){
                printf("Enter the node%d :",i);
                scanf("%d",&node);
                insertnode(node);
        }
        printf("Valuse in the linked list are:");
        display();
        printf("\n");
        findminmax();
}
```
## 18.Write a function to create a copy of a single linked list.
```c
#include<stdio.h>
#include<stdlib.h>
struct node{
        int val;
        struct node *nxt;
};
struct node *phead=NULL;
void insertnode(int d){
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
                return;
        }
        else{
                ptrav=phead;
                while(ptrav->nxt!=NULL){
                        ptrav=ptrav->nxt;
                }
                ptrav->nxt=pnew;
        }
}
struct node* copylist(struct node *phead){
        if(phead==NULL)
                return NULL;
        struct node *pnew,*ptrav,*pcopyhead=NULL,*pcopytail=NULL;
        ptrav=phead;
        while(ptrav!=NULL){
                pnew=(struct node*)malloc(sizeof(struct node));
                if(pnew==NULL){
                        printf("Malloc error");
                        return NULL;
                }
                pnew->val=ptrav->val;
                pnew->nxt=NULL;
                if(pcopyhead==NULL){
                        pcopyhead=pnew;
                        pcopytail=pnew;
                }
                else{
                        pcopytail->nxt=pnew;
                        pcopytail=pnew;
                }
                ptrav=ptrav->nxt;
        }
        return pcopyhead;
}
void display(struct node *phead){
        struct node *ptrav=phead;
        while(ptrav!=NULL){
                printf("%d ",ptrav->val);
                ptrav=ptrav->nxt;
        }
}
int main(){
        int n,node;
        struct node *copied;
        printf("Enter the total number of nodes:");
        scanf("%d",&n);
        for(int i=0;i<n;i++){
                printf("Enter the node%d :",i);
                scanf("%d",&node);
                insertnode(node);
        }
        printf("Values in the linked list are:");
        display(phead);
        printf("\n");
        printf("Values in the linked list after copying:");
        copied=copylist(phead);
        display(copied);
}
```
## 19. Write a function to move the largest element to the end of a single linked list.
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
## 20.Write a function to move the smallest element to the beginning of a single linked list. 
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
void movesmalltobegin(){
        if(phead==NULL && phead->nxt!=NULL)
                return;
        struct node *prev=NULL,*minprev=NULL,*minnode=phead,*currentnode=phead;
        while(currentnode!=NULL){
                if(currentnode->val < minnode->val){
                        minnode=currentnode;
                        minprev=prev;
                }
                prev=currentnode;
                currentnode=currentnode->nxt;
        }
        if(minnode==phead)
                return;
        if(minprev!=NULL)
                minprev->nxt=minnode->nxt;
        minnode->nxt=phead;
        phead=minnode;
}
void display(){
        struct node *temp=phead;
        while(temp!=NULL){
                printf("%d\n",temp->val);
                temp=temp->nxt;
        }
}
int main(){
        int n,node;
        printf("Enter the total number of nodes");
        scanf("%d",&n);
        for(int i=0;i<n;i++){
                printf("Enter the node%d:",i);
                scanf("%d",&node);
                createnode(node);
        }
        movesmalltobegin();
        display();
}
```
## 21. Write a program to remove first node of the list and insert it at the end, without changing info part of any node.
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
void movefirstnodetolastnode(){
        struct node *ptrav=phead,*temp=phead;
        while(ptrav->nxt!=NULL){
                ptrav=ptrav->nxt;
        }
        phead=temp->nxt;
        ptrav->nxt=temp;
        temp->nxt=NULL;
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
        movefirstnodetolastnode();
        display();
}
```
## 22. Write a program to remove the last node of the list and insert it in the beginning, without changing info part of any node.
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
void movelastnodetofirst(){
        struct node *ptrav=phead,*prev=NULL;
        while(ptrav->nxt!=NULL){
                prev=ptrav;
                ptrav=ptrav->nxt;
        }
        prev->nxt=NULL;
        ptrav->nxt=phead;
        phead=ptrav;
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
        movelastnodetofirst();
        display();
}
```
## 23.Remove duplicates from the Linked list.
```c
#include<stdio.h>
#include<stdlib.h>
struct node{
        int val;
        struct node *nxt;
};
struct node *phead=NULL;
int createnode(int d){
        struct node *ptrav,*pnew;
        pnew=(struct node*)malloc(sizeof(struct node));
        if(pnew==NULL){
                printf("malloc error");
                return 0;
        }
        pnew->val=d;
        pnew->nxt=NULL;
        if(phead==NULL){
                phead=pnew;
                return 0;
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
        struct node *ptrav=phead;
        while(ptrav!=NULL){
                printf("%d->",ptrav->val);
                ptrav=ptrav->nxt;
        }
        printf("NULL");
}
void sort(){
        struct node *i,*j;
        int temp;
        for(i=phead;i!=NULL;i=i->nxt){
                for(j=i->nxt;j!=NULL;j=j->nxt){
                        if(i->val > j->val){
                                int temp=i->val;
                                i->val=j->val;
                                j->val=temp;
                        }
                }
        }
}
void removeduplicates(){
        struct node *p=phead;
        struct node *q;
        while(p!=NULL && p->nxt!=NULL){
                while(p->val == p->nxt->val){
                        q=p->nxt->nxt;
                        if(q==NULL){
                                p->nxt=NULL;
                                break;
                        }
                        p->nxt=q;
                }
                if(p->val!=p->nxt->val)
                        p=p->nxt;
        }
}
int main(){
        int n1,n2,node;
        printf("Enter the total number of nodes in ist linkedlist:");
        scanf("%d",&n1);
        for(int i=0;i<n1;i++){
                printf("Enter the %dnode:",i);
                scanf("%d",&node);
                createnode(node);
        }
        printf("Enter the total number of nodes in 2nd linkedlist:");
        scanf("%d",&n2);
        for(int i=n1;i<n1+n2;i++){
                printf("Enter the %dnode:",i);
                scanf("%d",&node);
                createnode(node);
        }
        display();
        printf("\n");
        sort();
        removeduplicates();
        display();
}
```
## 24.Delete node at particular position of the linked list.
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
                printf("Error");
                return;
        }
        pnew->val=d;
        pnew->nxt=NULL;
        if(phead==NULL){
                phead=pnew;
                return;
        }
        else{
                ptrav=phead;
                while(ptrav->nxt != NULL){
                        ptrav=ptrav->nxt;
                }
                ptrav->nxt=pnew;
        }
}
void display(){
        struct node *ptrav=phead;
        while(ptrav!=NULL){
                printf("%d->",ptrav->val);
                ptrav=ptrav->nxt;
        }
        printf("NULL");
}
void deletenode(int pos,int n){
        struct node *ptrav=phead,*temp,*del;
        if(pos>n||pos<1){
                printf("Position is outof limit");
                return;
        }
        else{
                if(pos==1){
                        temp=phead;
                        phead=temp->nxt;
                        printf("Deleting node at %d : %d\n",pos,temp->val);
                        free(temp);
                }
                else{
                        temp=phead;
                        for(int i=1;i<pos-1;i++){
                                temp=temp->nxt;
                        }
                        del=temp->nxt;
                        temp->nxt=del->nxt;
                        printf("Deleting node at %d : %d\n",pos,del->val);
                        free(del);
                }
        }

}
int main(){
        int n,node,pos;
        printf("Enter total number of nodes:");
        scanf("%d",&n);
        for(int i=0;i<n;i++){
                printf("Enter the node%d : ",i+1);
                scanf("%d",&node);
                createnode(node);
        }
        display();
        printf("\n");
        printf("Enter the position to delete:");
        scanf("%d",&pos);
        deletenode(pos,n);
        display();
}
```
## 25.Write a C program to create a singly linked list, display it, and delete all occurrences of a given node value.
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
                printf("Error");
                return;
        }
        pnew->val=d;
        pnew->nxt=NULL;
        if(phead==NULL){
                phead=pnew;
                return;
        }
        else{
                ptrav=phead;
                while(ptrav->nxt != NULL){
                        ptrav=ptrav->nxt;
                }
                ptrav->nxt=pnew;
        }
}
void display(){
        struct node *ptrav=phead;
        while(ptrav!=NULL){
                printf("%d->",ptrav->val);
                ptrav=ptrav->nxt;
        }
        printf("NULL");
}
void deletenode(int data){
        struct node *ptrav=phead,*prev=NULL;
        while(ptrav!=NULL){
                if(ptrav->val==data){
                        if(prev==NULL){
                                phead=ptrav->nxt;
                                free(ptrav);
                                ptrav=phead;
                        }
                        else{
                                prev->nxt=ptrav->nxt;
                                free(ptrav);
                                ptrav=prev->nxt;
                        }
                }
                else{
                        prev=ptrav;
                        ptrav=ptrav->nxt;
                }
        }
}
int main(){
        int n,node,data;
        printf("Enter total number of nodes:");
        scanf("%d",&n);
        for(int i=0;i<n;i++){
                printf("Enter the node%d : ",i+1);
                scanf("%d",&node);
                createnode(node);
        }
        display();
        printf("\n");
        printf("Enter the node to delete:");
        scanf("%d",&data);
        deletenode(data);
        display();
}
```
## 26.Check if a linked list is palindrome or not.
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
                printf("Error");
                return;
        }
        pnew->val=d;
        pnew->nxt=NULL;
        if(phead==NULL){
                phead=pnew;
                return;
        }
        else{
                ptrav=phead;
                while(ptrav->nxt!=NULL){
                        ptrav=ptrav->nxt;
                }
                ptrav->nxt=pnew;
        }
}
void palindromeornot(){
        int arr[100],k=0;
        struct node *ptrav=phead;
        while(ptrav!=NULL){
                arr[k++]=ptrav->val;
                ptrav=ptrav->nxt;
        }
        for(int i=0,j=k-1;i<j;i++,j--){
                if(arr[i]!=arr[j]){
                        printf("Not a palindrome\n");
                        return;
                }
        }
        printf("Palindrome\n");
}
void display(){
        struct node *ptrav=phead;
        while(ptrav!=NULL){
                printf("%d->",ptrav->val);
                ptrav=ptrav->nxt;
        }
        printf("NULL\n");
}
int main(){
        int n,node;
        printf("Enter the total number of nodes:");
        scanf("%d",&n);
        for(int i=0;i<n;i++){
                printf("Enter the node %d :",i+1);
                scanf("%d",&node);
                createnode(node);
        }
        display();
        palindromeornot();
}
```
## 27. create, detect and delete the loop.
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
                printf("Error");
                return;
        }
        pnew->val=d;
        pnew->nxt=NULL;
        if(phead==NULL){
                phead=pnew;
                return;
        }
        else{
                ptrav=phead;
                while(ptrav->nxt!=NULL){
                        ptrav=ptrav->nxt;
                }
                ptrav->nxt=pnew;
        }
}
void createloop(int x){
        struct node *ptrav,*ptemp;
        int count=0;
        ptrav=phead;
        while(count != x){
                count++;
                ptrav=ptrav->nxt;
        }
        ptemp=ptrav;
        ptrav=phead;
        while(ptrav->nxt!=NULL){
                ptrav=ptrav->nxt;
        }
        ptrav->nxt=ptemp;
        printf("Loop is created\n");
}
void detectionanddeletion(){
        struct node *slow=phead,*fast=phead;
        while(fast!=NULL && fast->nxt!=NULL){
                slow=slow->nxt;
                fast=fast->nxt->nxt;
                if(slow==fast){
                        printf("Loop is detected\n");
                slow=phead;
                while(slow!=fast){
                     slow=slow->nxt;
                     fast=fast->nxt;
                }
                struct node *loopstart=slow;
                struct node *ptrav=loopstart;
                while(ptrav->nxt != loopstart){
                       ptrav=ptrav->nxt;
                }
                ptrav->nxt=NULL;
                printf("Loop is removed\n");
                return;
             }
        }
        printf("No loop is found");
}
int main(){
        int n,node,x;
        printf("Enter the total number of nodes:");
        scanf("%d",&n);
        for(int i=0;i<n;i++){
                printf("Enter the node %d :",i+1);
                scanf("%d",&node);
                createnode(node);
        }
        printf("Enter the value where you want to create loop:");
        scanf("%d",&x);
        createloop(x);
        detectionanddeletion();
}
```
