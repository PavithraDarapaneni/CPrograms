## 1. Write a program in C to store elements in an array and print them.
```c
#include<stdio.h>
#define n 5
void elements(int array[]){
        for(int i=0;i<n;i++){
                printf("%d ",array[i]);
        }
        printf("\n");
}
int main(){
        int arr[n];
        void (*ptr)(int [])=&elements;
        printf("Enter the elements:");
        for(int i=0;i<n;i++){
                scanf("%d",&arr[i]);
        }
        printf("Elements in an array: ");
        ptr(arr);
}

```

## 2. Write a program in C to read n number of values in an array and display them in reverse order.
```c
#include<stdio.h>
#define n 5
void reverse(int array[]){
        for(int i=n-1;i>=0;i--){
                printf("%d ",array[i]);
        }
         printf("\n");
}
int main(){
        int arr[n];
        void (*ptr)(int [])=&reverse;
        for(int i=0;i<n;i++){
                scanf("%d",&arr[i]);
        }
        printf("Reversed Array:");
        ptr(arr);
}
```
## 3. Write a program in C to find the sum of all elements of the array.
```c
#include<stdio.h>
#define n 5
void sum(int array[]){
        int s=0;
        for(int i=0;i<n;i++){
                s=s+array[i];
        }
        printf("sum=d",s);
}
int main(){
        int arr[n];
        void (*ptr)(int [])=&sum;
        for(int i=0;i<n;i++){
                scanf("%d",&arr[i]);
        }
        ptr(arr);
}
```
## 4. Write a program in C to copy the elements of one array into another array.
```c
#include<stdio.h>
#define n 5
void copying(int array[]){
        int newarray[n];
        for(int i=0;i<n;i++){
                newarray[i]=array[i];
        }
        for(int i=0;i<n;i++){
                printf("%d ",newarray[i]);
        }
}
int main(){
        int arr[n];
        void (*ptr)(int [])=&copying;
        printf("Enter the elements of array:");
        for(int i=0;i<n;i++){
                scanf("%d",&arr[i]);
        }
        ptr(arr);
}
```
## 5. Write a program in C to count the total number of duplicate elements in an array.
```c
#include<stdio.h>
void duplicates(int array1[],int array2[]){
        for(int i=0;i<9;i++){
                if(array2[i]>=1){
                        printf("%d\t",array1[i]);
                }
        }
}
int main(){
        int arr[]={1,2,3,1,2,4,6,3,2};
        int freq[9],count=0;
        void (*ptr)(int [],int [])=&duplicates;
        for(int i=0;i<9;i++){
                freq[i]=-1;
        }
        for(int i=0;i<9;i++){
                count=0;
                if(freq[i]!=0){
                for(int j=i+1;j<9;j++){
                        if(arr[i]==arr[j]){
                                count++;
                                freq[j]=0;
                        }
                }
                freq[i]=count;
                }
        }
                ptr(arr,freq);
}
```


## 6. Write a program in C to print all unique elements in an array.
```c
#include<stdio.h>
void unique(int array[]){
        for(int i=0;i<9;i++){
                if(array[i]!=0){
                int count=0;
                for(int j=i+1;j<9;j++){
                        if(array[i]==array[j]){
                                count++;
                                array[j]=0;
                        }
                }
                if(count==0)
                        printf("%d ",array[i]);
        }

}
}
int main(){
        int arr[]={1,2,3,1,2,4,6,3,2};
        void (*ptr)(int [])=&unique;
        ptr(arr);
}

```
## 7. Write a program in C to merge two arrays of the same size sorted in descending order.
```c
#include<stdio.h>
void merge(int array1[],int array2[],int len){
        int array3[2*len];
        for(int i=0;i<len;i++){
                array3[i]=array1[i];
                }
        for(int i=len,j=0;i<2*len;i++,j++){
                array3[i]=array2[j];
        }
        for(int i=0;i<2*len;i++){
            for(int j=i+1;j<2*len;j++){
                if(array3[i]<array3[j]){
                    int temp=array3[i];
                    array3[i]=array3[j];
                    array3[j]=temp;
                }
            }
        }
        for(int i=0;i<2*len;i++){
                printf("%d ",array3[i]);
        }
        printf("\n");
}
int main(){
        int arr1[]={5,4,3,2,1};
        int arr2[]={10,9,8,7,6};
        int len1=sizeof(arr1)/sizeof(arr1[0]);
        void (*ptr)(int [],int [],int )=&merge;
        ptr(arr1,arr2,len1);
}
```
## 8. Write a program in C to count the frequency of each element of an array.
```c
#include<stdio.h>
#define n 10
void countfreq(int array[],int freq[]){
        for(int i=0;i<n;i++){
                if(freq[i]!=0){
                        printf("%d counts %d times\n",array[i],freq[i]);
                }
        }
        printf("\n");
}
int main(){
        int arr[n],frequency[n];
        int count;
        void (*ptr)(int [],int [])=&countfreq;
        for(int i=0;i<n;i++){
                scanf("%d",&arr[i]);
        }
        for(int i=0;i<n;i++){
                frequency[i]=-1;
        }
        for(int i=0;i<n;i++){
                count=1;
                if(frequency[i]!=0){
                        for(int j=i+1;j<n;j++){
                                if(arr[i]==arr[j]){
                                        count++;
                                        frequency[j]=0;
                                }
                        }
                        frequency[i]=count;
                }
        }
        ptr(arr,frequency);
}
```
## 9. Write a program in C to find the maximum and minimum elements in an array
```c
#include<stdio.h>
#define n 5
void minmax(int min,int max){
        printf("Minimum number in array:%d\n",min);
        printf("Maximum number in array:%d",max);
}
int main(){
        int arr[n]={3,5,2,3,8};
        int maximum=minimum=arr[0];
        void (*ptr)(int,int)=&minmax;
        for(int i=0;i<n;i++){
                if(arr[i]>maximum)
                        maximum=arr[i];
                if(arr[i]<minimum)
                        minimum=arr[i];
        }
        ptr(minimum,maximum);
}
```
## 10. Write a program in C to separate odd and even integers into separate arrays.
```c
#include<stdio.h>
#define n 6
void evenodd(int array[]){
        int k=0,l=0,even[100],odd[100];
        for(int i=0;i<n;i++){
                if(array[i]%2==0)
                        even[k++]=array[i];
                else
                        odd[l++]=array[i];
        }
        printf("Even numbers are :");
        for(int i=0;i<k;i++){
                printf("%d ",even[i]);
        }
        printf("\nOdd numbers are :");
        for(int i=0;i<l;i++){
                printf("%d ",odd[i]);
        }
}
int main(){
        int arr[]={1,2,3,4,5,6};
        void (*ptr)(int [])=&evenodd;
        ptr(arr);
}
```
