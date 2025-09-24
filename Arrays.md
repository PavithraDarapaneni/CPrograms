## 1.Rotate an array by 180 and 360 degrees.
```c
#include<stdio.h>
int main(){
        int arr[10]={2,3,5,6,1,3,2,1,4,5};
        int length=sizeof(arr)/sizeof(arr[0]);
        for(int i=0,j=length-1;i<j;i++,j--){
                int temp;
                temp=arr[i];
                arr[i]=arr[j];
                arr[j]=temp;
        }
        printf("Array in 180 degrees:");
        for(int i=0;i<length;i++){
                printf("%d ",arr[i]);
        }
        for(int i=0,j=length-1;i<j;i++,j--){
                int temp;
                temp=arr[i];
                arr[i]=arr[j];
                arr[j]=temp;
        }
        printf("\nArray in 360 degrees:");
        for(int i=0;i<length;i++){
                printf("%d ",arr[i]);
        }

}
```
## 2.Find the largest element in an array using pointer notation.
```c
#include<stdio.h>
void largest(int arr[],int len){
        int max=*(arr);
        for(int i=0;i<len;i++){
                if(*(arr+i)>max){
                        max=*(arr+i);
                }
        }
        printf("Largest element=%d",max);
}
int main(){
        int arr1[]={4,5,6,7,10,8};
        int length=sizeof(arr1)/sizeof(arr1[0]);
        largest(arr1,length);
}
```
## 3.Write a program to rotate a 3×3 matrix by 90 degrees clockwise.
```c
#include<stdio.h>
#define r 2
#define c 3
int main(){
        int arr[r][c],tran[c][r],rev[c][r];
        for(int i=0;i<r;i++){
                for(int j=0;j<c;j++){
                        scanf("%d",&arr[i][j]);
                }
        }
        for(int i=0;i<r;i++){
                for(int j=0;j<c;j++){
                        tran[j][i]=arr[i][j];
                }
        }
        for(int i=0;i<c;i++){
                for(int j=0;j<r;j++){
                        rev[i][j]=tran[c-1-i][c];
                }
        }
        printf("Matrix after Rotated to 90 degrees in clockwise\n");
        for(int i=0;i<c;i++){
                for(int j=0;j<r;j++){
                        printf("%d ",rev[i][j]);
                }
                printf("\n");
        }
}
```
## 4.Write a program to rotate a 3×3 matrix by 90 degrees Anti-clockwise.
```c
#include<stdio.h>
#define r 2
#define c 3
int main(){
        int arr[r][c],tran[c][r],rev[c][r];
        for(int i=0;i<r;i++){
                for(int j=0;j<c;j++){
                        scanf("%d",&arr[i][j]);
                }
        }
        for(int i=0;i<r;i++){
                for(int j=0;j<c;j++){
                        tran[j][i]=arr[i][j];
                }
        }
        for(int i=0;i<c;i++){
                for(int j=0;j<r;j++){
                        rev[i][j]=tran[r][r-1-j];
                }
        }
        printf("Matrix after Rotated to 90 degrees in anticlockwise\n");
        for(int i=0;i<c;i++){
                for(int j=0;j<r;j++){
                        printf("%d ",rev[i][j]);
                }
                printf("\n");
        }
}
```
## 5.Write a program to rotate a matrix by 180 degrees.
```c
#include<stdio.h>
#define r 2
#define c 3
int main(){
        int arr[r][c],rev[r][c];
        for(int i=0;i<r;i++){
                for(int j=0;j<c;j++){
                        scanf("%d",&arr[i][j]);
                }
        }
        for(int i=0;i<r;i++){
                for(int j=0;j<c;j++){
                        rev[i][j]=arr[r-1-i][c-1-j];

                }
        }
        printf("Matrix after Rotated to 180 degrees\n");
        for(int i=0;i<r;i++){
                for(int j=0;j<c;j++){
                        printf("%d ",rev[i][j]);
                }
                printf("\n");
        }
}
```
## 6.Print the address and value of each element in an integer array using pointer arithmetic.
```c
#include<stdio.h>
int main(){
        int arr[]={2,3,4,6,7,8};
        int len=sizeof(arr)/sizeof(arr[0]);
        int *ptr=arr;
        for(int i=0;i<len;i++){
                printf("Address=%p and Values=%d\n",ptr+i,*(ptr+i));
        }
}
```
## 7.Swap two arrays of equal size using pointers.
```c
#include<stdio.h>
int main(){
        int arr1[]={1,2,3,4,5};
        int arr2[]={6,7,8,9,10};
        int *p1,*p2;
        int len=sizeof(arr1)/sizeof(arr1[0]);
        p1=arr1;
        p2=arr2;
        for(int i=0;i<len;i++){
                int temp=*(p1+i);
                *(p1+i)=*(p2+i);
                *(p2+i)=temp;
        }
        printf("first array:\n");
        for(int i=0;i<len;i++){
                printf("%d ",arr1[i]);
        }
        printf("\nSecond array:\n");
        for(int i=0;i<len;i++){
                printf("%d ",arr2[i]);
        }

}
```
## 8.Write a C program to print highest sum of adjacent elements in an array.
```c
#include<stdio.h>
int main(){
    int arr[]={1,4,7,2,3,8};
    int sum=0;
    int len=sizeof(arr)/sizeof(arr[0]);
    int max=0;
    for(int i=0;i<len-1;i++){
        sum=arr[i]+arr[i+1];
        if(max<sum){
            max=sum;
        }
    }
    printf("Highest sum=%d",max);
}
```
## 9.Write a program to find the sum of rows and columns of a 2-d array and store the sums in the same array.
```c
#include<stdio.h>
#define r 3
#define c 3
int main(){
        int arr[r+1][c+1]={0};
        for(int i=0;i<r;i++){
                for(int j=0;j<c;j++){
                        scanf("%d",&arr[i][j]);\
                }
        }
        for(int i=0;i<r;i++){
                for(int j=0;j<c;j++){
                        arr[i][c]+=arr[i][j];
                        arr[r][j]+=arr[i][j];
                        arr[r][c]+=arr[i][j];
                }
        }
        for(int i=0;i<=r;i++){
                for(int j=0;j<=c;j++){
                        printf("%d ",arr[i][j]);
                }
                printf("\n");
        }
}
```
## 10.Write a C Program to Print all Non Repeated Elements in an Array.
```c
#include<stdio.h>
int main(){
    int arr[]={2,3,4,5,1,2,6,9,6,4,3};
    int len=sizeof(arr)/sizeof(arr[0]);
    int freq[len];
    for(int i=0;i<len;i++){
        freq[i]=-1;
    }
    for(int i=0;i<len;i++){
        if(freq[i]==-1){
            for(int j=i+1;j<len;j++){
                if(arr[i]==arr[j]){
                    freq[i]=freq[j]=0;
                    break;
                }
            }
        }
    }
    for(int i=0;i<len;i++){
        if(freq[i]!=0)
           printf("%d ",arr[i]);
    }
}
```
## 11.Write a program in C to print all unique elements in an array.
```c
#include<stdio.h>
int main(){
    int arr[]={2,3,4,5,1,2,6,9,6,4,3};
    int len=sizeof(arr)/sizeof(arr[0]);
    int freq[len];
    for(int i=0;i<len;i++){
        freq[i]=-1;
    }
    for(int i=0;i<len;i++){
        if(freq[i]==-1){
            for(int j=i+1;j<len;j++){
                if(arr[i]==arr[j]){
                    freq[j]=0;
                    break;
                }
            }
        }
    }
    for(int i=0;i<len;i++){
        if(freq[i]!=0)
           printf("%d ",arr[i]);
    }
}
```
## 12.Write a program to find the sum of rows and columns of a 2-d array and store the sums in the same array.
```c
#include<stdio.h>
#define r 3
#define c 3
int main(){
    int arr[r+1][c+1]={0};
    for(int i=0;i<r;i++){
        for(int j=0;j<c;j++){
            scanf("%d",&arr[i][j]);
        }
    }
    for(int i=0;i<r;i++){
        for(int j=0;j<c;j++){
            arr[i][c]+=arr[i][j];
            arr[r][j]+=arr[i][j];
            arr[r][c]+=arr[i][j];
        }
    }
    for(int i=0;i<=r;i++){
        for(int j=0;j<=c;j++){
            printf("%d ",arr[i][j]);
        }
        printf("\n");
    }
    
}
```
## 13.Maximum Average of Subarrays of Size 4.
```c
#include<stdio.h>
int main(){
        int arr1[6]={1,12,-5,-6,50,3};
        float sum=0,k=4;
        float len,max=-10000;
        len=sizeof(arr1)/sizeof(arr1[0]);
        for(int i=0;i<=len-k;i++){
                sum=0;
                for(int j=i;j<(i+k);j++){
                        sum=sum+arr1[j];
                }
                if((sum/k)>max)
                    max=sum/k;
        }
        printf("\naverage highest sum=%2f",max);
}
```
## 14.Write a C Program to find largest and secondlargest of an array.
```c
#include<stdio.h>
int main(){
    int arr[6]={10,30,28,46,87,67};
    int len=sizeof(arr)/sizeof(arr[0]);
    int largest=arr[0];
    int secondlargest=arr[0];
    for(int i=0;i<len;i++){
        if(arr[i]>largest){
            secondlargest=largest;
            largest=arr[i];
        }
        else if(arr[i]>secondlargest && arr[i]!=largest){
            secondlargest=arr[i];
        }
    }
    printf("largest=%d \nsecondlargest=%d",largest,secondlargest);
}
```
## 15.Write a C program to perform left rotation of an array by k positions.
```c
#include<stdio.h>
int main(){
        int arr[5]={1,2,3,4,5};
        int len=sizeof(arr)/sizeof(arr[0]);
        int temp,k=3;
        for(int i=0;i<k;i++){
            temp=arr[0];
            for(int j=0;j<len-1;j++){
                arr[j]=arr[j+1];
            }
            arr[len-1]=temp;
        }
        for(int i=0;i<5;i++){
            printf("%d ",arr[i]);
        }
        
}
```
## 16.Write a C program to perform right rotation of an array by k positions.
```c
#include<stdio.h>
int main(){
        int arr[5]={1,2,3,4,5};
        int temp,k=3;
        int len=sizeof(arr)/sizeof(arr[0]);
        for(int i=0;i<k;i++){
                temp=arr[len-1];
                for(int j=len-1;j>0;j--){
                        arr[j]=arr[j-1];
                }
                arr[0]=temp;
        }
        for(int i=0;i<len;i++){
                printf("%d ",arr[i]);
        }
}
```
## 17.Count the Number of Subarrays with Sum Less Than or Equal to K.
```c
#include<stdio.h>
int main(){
        int n,k,sum=0,count=0;
        printf("Enter the number of elements in the array:");
        scanf("%d",&n);
        int arr[n];
        printf("Enter the elements in the array:");
        for(int i=0;i<n;i++){
                scanf("%d",&arr[i]);
        }
        printf("Enter k value:");
        scanf("%d",&k);
        for(int i=0;i<n;i++){
                sum=0;
                for(int j=i;j<n;j++){
                        sum=sum+arr[j];
                        if(sum<=k)
                                count++;
                        else
                                break;
                }
        }
        printf("count=%d",count);
}
```
## 18.Find the smallest subarray with a sum ≥ k.
```c
#include<stdio.h>
int main(){
        int n,k,sum=0,min=999,m=0;
        printf("Enter the number of elements in the array:");
        scanf("%d",&n);
        int arr[n],arr1[n];
        printf("Enter the elements in the array:");
        for(int i=0;i<n;i++){
                scanf("%d",&arr[i]);
        }
        printf("Enter k value:");
        scanf("%d",&k);
        for(int i=0;i<n;i++){
                sum=0,m=0;
                for(int j=i;j<n;j++){
                        sum=sum+arr[j];
                        m++;
                        if(sum>=k){
                                if(m<min)
                                    min=m;
                                break;
                        }

                }
        }
        printf("m=%d",min);
}
```
## 19.Write a C program to calculate the sum of both diagonals of a 3×3 matrix.
```c
#include<stdio.h>
int main(){
    int arr[3][3]={{1,2,3},{4,5,6},{7,8,9}};
    int sum1=0,sum2=0;
    for(int i=0;i<3;i++){
        sum1+=arr[i][i];
        sum2+=arr[i][2-i];
    }
    printf("sum of the diagnols=%d",sum1+sum2);
}
```
## 20.Program to find missing number in an array.
```c
#include<stdio.h>
int main(){
        int totalsum,n,sum=0;
        printf("Enter number of elements in the array:");
        scanf("%d",&n);
        int arr[n];
        for(int i=0;i<n;i++){
                scanf("%d",&arr[i]);
        }
        for(int i=0;i<n;i++){
                sum=sum+arr[i];
        }
        totalsum=(n+1)*(n+2)/2;
        printf("Missing element=%d",totalsum-sum);
}
```
## 21.Program to find second smallest element in an array.
```c
#include<stdio.h>
int main(){
        int n,smallest,secondsmallest;
        printf("Enter size of the array:");
        scanf("%d",&n);
        int arr[n];
        for(int i=0;i<n;i++){
                scanf("%d",&arr[i]);
        }
        if(arr[0]>arr[1]){
                smallest=arr[1];
                secondsmallest=arr[0];
        }
        else{
                smallest=arr[0];
                secondsmallest=arr[1];
        }
        for(int i=0;i<n;i++){
                if(arr[i]<smallest){
                    secondsmallest=smallest;
                    smallest=arr[i];
                }
                else if(arr[i]!=smallest&&arr[i]<secondsmallest){
                        secondsmallest=arr[i];
                }
        }
        printf("Second Smallest:%d",secondsmallest);
}
```
## 22.Write a C Program to dynamically allocate memory for an array of num integers,read the elements,and find their sum.Free the allocated memory at end.
```c
#include<stdio.h>
#include<stdlib.h>
int main(){
        int num,sum=0;
        int *ptr;
        printf("Enter the number of elements:");
        scanf("%d",&num);
        ptr=(int *)malloc(num*sizeof(int));
        printf("Enter the elements:");
        for(int i=0;i<num;i++){
                scanf("%d",&ptr[i]);
        }
        for(int i=0;i<num;i++){
                sum=sum+ptr[i];
        }
        printf("sum=%d",sum);
        free(ptr);
}
```
## 23.Write a program for searching of an element using binary search algorithm.
```c
#include<stdio.h>
int main(){
        int n;
        printf("Enter the array size:");
        scanf("%d",&n);
        int arr[n],search,right=n-1,left=0,mid,found=0;
        printf("Enter the elements:\n");
        for(int i=0;i<n;i++){
                scanf("%d",&arr[i]);
        }
        printf("Enter the saerching element:");
        scanf("%d",&search);
        while(left<=right){
                mid=(left+right)/2;
                if(search==arr[mid]){
                        printf("element found at position %d",mid);
                        found=1;
                        break;
                }
                else if(search<arr[mid])
                        right=mid-1;
                else if(search>arr[mid])
                        left=mid+1;
        }
         if(found==0)
                printf("Element is not found");
}
```
## 24.Merge two arrays into one sorted array.
```c
#include<stdio.h>
int main(){
        int arr1[]={1,3,4,6,2};
        int arr2[]={5,7,9,3,8};
        int len1=sizeof(arr1)/sizeof(arr1[0]);
        int len2=sizeof(arr2)/sizeof(arr2[0]);
        int arr[len1+len2],k=0;
        for(int i=0;i<len1;i++){
                arr[k++]=arr1[i];
        }
        for(int i=0;i<len2;i++){
                arr[k++]=arr2[i];
        }
        for(int i=0;i<k;i++){
                for(int j=i+1;j<k;j++){
                        if(arr[i]>arr[j]){
                                int temp=arr[i];
                                arr[i]=arr[j];
                                arr[j]=temp;
                        }
                }
        }
        printf("Merged and sorted array:");
        for(int i=0;i<k;i++){
                printf("%d ",arr[i]);
        }
        printf("\n");
}
```
## 25.Insert an element at a given position in an array.
```c
#include<stdio.h>
int main(){
        int arr[100],n,pos,ele;
        printf("Enter the array size:");
        scanf("%d",&n);
        printf("Enter the elements:\n");
        for(int i=0;i<n;i++){
                scanf("%d",&arr[i]);
        }
        printf("Enter the position:");
        scanf("%d",&pos);
        printf("Enter the element:");
        scanf("%d",&ele);
        if(pos<0||pos>n){
                printf("Invalid");
        }
        else{
              for(int i=n;i>pos;i--){
                    arr[i]=arr[i-1];
              }
              arr[pos]=ele;
              n++;
              printf("Array after insertion:");
              for(int i=0;i<n;i++){
                      printf(" %d",arr[i]);
              }
              printf("\n");
        }
}
```
 ## 26.Delete an element at a given position in an array.
 ```c
#include<stdio.h>
int main(){
        int arr[]={1,2,3,4,5,6};
        int len=sizeof(arr)/sizeof(arr[0]);
        int pos;
        printf("Enter the position(index starts from 0):");
        scanf("%d",&pos);
        for(int i=pos;i<len;i++){
                arr[i]=arr[i+1];
        }
        len--;
        for(int i=0;i<len;i++){
                printf(" %d",arr[i]);
        }
        printf("\n");
}
```
## 27.Find the majority element (appears more than n/2 times).
```c
#include<stdio.h>
int main(){
        int arr[]={1,1,1,2,2};
        int len=sizeof(arr)/sizeof(arr[0]);
        int freq[len];
        int count=1;
        for(int i=0;i<len;i++){
                freq[i]=-1;
        }
        for(int i=0;i<len;i++){
                count=1;
                if(freq[i]==-1){
                     for(int j=i+1;j<len;j++){
                        if(arr[i]==arr[j]){
                                freq[j]=0;
                                count++;
                        }
                     }
                     freq[i]=count;
                }
        }
        int found=0;
        for(int i=0;i<len;i++){
                if(freq[i]>(len/2)){
                        printf("Majority element: %d\n",arr[i]);
                        found=1;
                }
        }
        if(!found)
                printf("No Majority element in the array\n");
}
```
## 28.Find the subarray with the maximum sum.
```c
#include<stdio.h>
int main(){
        int arr[]={-2, 1, -3, 4, -1, 2, 1, -5, 4};
        int n=sizeof(arr)/sizeof(arr[0]);
        int maxsum=arr[0],currentsum=arr[0];
        int start=0,end=0,tempstart=0;
        for(int i=1;i<n;i++){
                if(arr[i]>currentsum+arr[i]){
                        currentsum=arr[i];
                        tempstart=i;
                }
                else{
                        currentsum=currentsum+arr[i];
                }
                if(currentsum>maxsum){
                        maxsum=currentsum;
                        start=tempstart;
                        end=i;
                }
        }
        printf("Maximumsum=%d\n",maxsum);
        printf("Subarray:");
        for(int k=start;k<=end;k++){
                printf("%d ",arr[k]);
        }
        printf("\n");
}
```
## 29.Find the intersection of two arrays.
```c
#include<stdio.h>
int main(){
        int arr1[]={1,2,3,4,5};
        int arr2[]={3,4,5,6,7};
        int n1=sizeof(arr1)/sizeof(arr1[0]);
        int n2=sizeof(arr2)/sizeof(arr2[0]);
        int arr[n1],k=0;
        for(int i=0;i<n1;i++){
                for(int j=0;j<n2;j++){
                        if(arr1[i]==arr2[j]){
                                int exit=0;
                                for(int x=0;x<k;x++){
                                        if(arr[x]==arr[i]){
                                                exit=1;
                                                break;
                                        }
                                }
                                if(!exit){
                                        arr[k++]=arr1[i];
                                }
                        }
                }
        }
        printf("Intersection of two arrays:");
        for(int i=0;i<k;i++){
                printf("%d ",arr[i]);
        }
        printf("\n");
}
```
## 30.Find the union of two arrays.
```c
#include<stdio.h>
int main(){
        int arr1[]={1,2,3,4,5};
        int arr2[]={3,4,5,6,7};
        int n1=sizeof(arr1)/sizeof(arr1[0]);
        int n2=sizeof(arr2)/sizeof(arr2[0]);
        int arr[n1+n2],k=0;
        for(int i=0;i<n1;i++){
                arr[k++]=arr1[i];
        }
        for(int i=0;i<n2;i++){
                int exit=0;
                for(int j=0;j<k;j++){
                        if(arr2[i]==arr[j]){
                                exit=1;
                                break;
                        }
                }
                        if(!exit)
                             arr[k++]=arr2[i];
        }
        printf("Union of array:");
        for(int i=0;i<k;i++){
                printf("%d ",arr[i]);
        }
}
```
## 31.Find the first repeating element in an array.
```c
#include<stdio.h>
int main(){
        int arr[]={10,5,3,4,3,5,6};
        int len=sizeof(arr)/sizeof(arr[0]);
        int element,found=0;
        for(int i=0;i<len;i++){
                for(int j=i+1;j<len;j++){
                        if(arr[i]==arr[j]){
                                element=arr[j];
                                found=1;
                                break;
                        }
                }
                if(found){
                        printf("First non-repeating element:%d\n",element);
                        break;
                }

        }
}
```
## 32.Find the first non-repeating element in an array.
```c
#include<stdio.h>
int main(){
        int arr[]={10,5,3,4,3,10,5,6};
        int element,found=0;
        int len=sizeof(arr)/sizeof(arr[0]);
        for(int i=0;i<len;i++){
                int repeat=0;
                for(int j=0;j<len;j++){
                        if(i!=j && arr[i]==arr[j]){
                                repeat=1;
                                break;
                        }
                }
                        if(repeat==0){
                             element=arr[i];
                             found=1;
                             printf("First repeating element:%d\n",element);
                             break;
                }
        }
        if(!found){
                printf("No repeating element found");
        }
}
```
## 33.Union of matrix.
```c
#include<stdio.h>
int main(){
        int arr1[3][3],arr2[3][3];
        printf("Enter the elements in the matrix1:\n");
        for(int i=0;i<3;i++){
                for(int j=0;j<3;j++){
                        scanf("%d",&arr1[i][j]);
                }
        }
        printf("Enter the elements in the matrix2:\n");
        for(int i=0;i<3;i++){
                for(int j=0;j<3;j++){
                        scanf("%d",&arr2[i][j]);
                }
        }
        for(int i=0;i<3;i++){
                for(int j=0;j<3;j++){
                        for(int x=0;x<3;x++){
                                for(int y=0;y<3;y++){
                                        if(arr1[i][j]==arr2[x][y])
                                                arr2[x][y]=0;
                                }
                        }
                }
        }
        for(int i=0;i<3;i++){
                for(int j=0;j<3;j++){
                        printf("%3d",arr1[i][j]);
                }
                for(int j=0;j<3;j++){
                        printf("%3d",arr2[i][j]);
                }
                printf("\n");
        }
}
```
## 34. C Program to Find Union  of Two Array
```c
#include<stdio.h>
int main(){
        int arr1[]={1,2,3,4,5};
        int arr2[]={2,3,4,6,8};
        int a[10],k=0,flag=0;
        for(int i=0;i<5;i++){
                a[k++]=arr1[i];
        }
        for(int i=0;i<5;i++){
                flag=0;
                for(int j=0;j<5;j++){
                        if(arr2[i]==a[j]){
                                flag=1;
                                break;
                        }
                }
                if(flag==0)
                        a[k++]=arr2[i];
        }
        printf("Union of two arrays:");
        for(int i=0;i<k;i++){
                printf("%d ",a[i]);
        }
        printf("\n");
}
```
## 35.C Program to Find Intersection  of Two Array
```c
#include<stdio.h>
int main(){
        int arr1[]={1,2,3,4,5};
        int arr2[]={2,3,4,6,8};
        int a[10],k=0;
        for(int i=0;i<5;i++){
                for(int j=0;j<5;j++){
                        if(arr1[i]==arr2[j])
                                a[k++]=arr1[i];
                }
        }
        printf("Intersection of two arrays:");
        for(int i=0;i<k;i++){
                printf("%d ",a[i]);
        }
        printf("\n");
}
```
## 36.Write a program in C for adding two matrices of the same size.
```c
#include<stdio.h>
#define r1 3
#define c1 3
#define r2 3
#define c2 3
int main(){
        int arr1[r1][c1],arr2[r2][c2],arr[r1][c1];
        printf("Enter the elements in matrix1:");
        for(int i=0;i<r1;i++){
                for(int j=0;j<c1;j++){
                        scanf("%d",&arr1[i][j]);
                }
        }
        printf("Enter the elements in matrix2:");
        for(int i=0;i<r2;i++){
                for(int j=0;j<c2;j++){
                        scanf("%d",&arr2[i][j]);
                }
        }
        if(r1==r2 && c1==c2){
                printf("Matrix after addition:\n");
                for(int i=0;i<r1;i++){
                     for(int j=0;j<c1;j++){
                        arr[i][j]=arr1[i][j]+arr2[i][j];
                     }
                }
                for(int i=0;i<r1;i++){
                for(int j=0;j<c1;j++){
                        printf("%d ",arr[i][j]);
                }
                printf("\n");
                }
        }
        else
                printf("Matrix addition is not possible");
}
```
## 37.Write a program in C for the subtraction of two matrices.
```c
#include<stdio.h>
#define r1 3
#define c1 3
#define r2 3
#define c2 3
int main(){
        int arr1[r1][c1],arr2[r2][c2],arr[r1][c1];
        printf("Enter the elements in matrix1:");
        for(int i=0;i<r1;i++){
                for(int j=0;j<c1;j++){
                        scanf("%d",&arr1[i][j]);
                }
        }
        printf("Enter the elements in matrix2:");
        for(int i=0;i<r2;i++){
                for(int j=0;j<c2;j++){
                        scanf("%d",&arr2[i][j]);
                }
        }
        if(r1==r2 && c1==c2){
                printf("Matrix after subtraction:\n");
                for(int i=0;i<r1;i++){
                     for(int j=0;j<c1;j++){
                        arr[i][j]=arr1[i][j]-arr2[i][j];
                     }
                }
                for(int i=0;i<r1;i++){
                for(int j=0;j<c1;j++){
                        printf("%d ",arr[i][j]);
                }
                printf("\n");
                }
        }
        else
                printf("Matrix subtraction is not possible");
}
```
## 38.Write a program in C for the multiplication of two square matrices.
```c
#include<stdio.h>
#define r1 3
#define c1 3
#define r2 3
#define c2 3
int main(){
        int arr1[r1][c1],arr2[r2][c2],arr[r1][c1];
        printf("Enter the elements in matrix1:");
        for(int i=0;i<r1;i++){
                for(int j=0;j<c1;j++){
                        scanf("%d",&arr1[i][j]);
                }
        }
        printf("Enter the elements in matrix2:");
        for(int i=0;i<r2;i++){
                for(int j=0;j<c2;j++){
                        scanf("%d",&arr2[i][j]);
                }
        }
        if(c1==r2){
                for(int i=0;i<r1;i++){
                        for(int j=0;j<c2;j++){
                                arr[i][j]=0;
                        }
                }
                printf("Matrix after multiplication:\n");
                for(int i=0;i<r1;i++){
                        for(int j=0;j<c2;j++){
                                for(int k=0;k<c1;k++){
                                        arr[i][j] += arr1[i][k] * arr2[k][j];
                                }
                        }
                }
                for(int i=0;i<r1;i++){
                        for(int j=0;j<c2;j++){
                                printf("%d ",arr[i][j]);
                        }
                        printf("\n");
                }
        }
        else
                printf("Matrix multiplication is not possible");
}
```
## 39.Write a program in C to find the sum of the left diagonals of a matrix.
```c
#include<stdio.h>
#define r 3 
#define c 3
int main(){
        int arr[r][c],sum=0;
        printf("Enter the elements in the 2D array:");
        for(int i=0;i<r;i++){
                for(int j=0;j<c;j++){
                        scanf("%d",&arr[i][j]);
                }
        }
        for(int i=0;i<r;i++){
                for(int j=0;j<c;j++){
                        if(i==j){
                                sum += arr[i][j];
                        }
                }
        }
        printf("Sum of the left diagonals:%d\n",sum);
}
```
## 40.Write a program in C to find the sum of the right diagonals of a matrix
```c
#include<stdio.h>
#define r 3 
#define c 3
int main(){
        int arr[r][c],sum=0;
        printf("Enter the elements in the 2D array:");
        for(int i=0;i<r;i++){
                for(int j=0;j<c;j++){
                        scanf("%d",&arr[i][j]);
                }
        }
        for(int i=0;i<r;i++){
                for(int j=0;j<c;j++){
                        if(i+j==c-1){
                                sum += arr[i][j];
                        }
                }
        }
        printf("Sum of the right diagonals:%d\n",sum);
}
```
## 41.Write a C program to read a 4×4 matrix from the user and print its elements in spiral order traversal (clockwise).
```c
#include<stdio.h>
int main(){
        int arr[4][4];
        printf("Enter the elements in the array:");
        for(int i=0;i<4;i++){
                for(int j=0;j<4;j++){
                        scanf("%d",&arr[i][j]);
                }
        }
        int top=0,bottom=3,left=0,right=3;
        while(left<=right && top<=bottom){
                for(int i=left;i<=right;i++){
                        printf("%d->",arr[top][i]);
                }
                top++;
                for(int i=top;i<=bottom;i++){
                        printf("%d->",arr[i][right]);
                }
                right--;
                for(int i=right;i>=left;i--){
                        printf("%d->",arr[bottom][i]);
                }
                bottom--;
                for(int i=bottom;i>=top;i--){
                        printf("%d->",arr[i][left]);
                }
                left++;
        }
        printf("NULL\n");
}
```
## 42.Write a program to create an array next_ge for an unsorted array arr containing n elements such that next_ge[i] = next greater element of arr [1] in array arr i.e. first greater element on the right of arr[i]. -1 if no such element exists.
```c
#include<stdio.h>
int main(){
        int arr[]={3,1,6,2,5,8,9,4,7};
        int next_ge[10];
        int len=sizeof(arr)/sizeof(arr[0]);
        for(int i=0;i<len;i++){
                next_ge[i]=-1;
                for(int j=i+1;j<len;j++){
                        if(arr[j]>arr[i]){
                                next_ge[i]=arr[j];
                                break;
                        }
                }
        }
        for(int i=0;i<len;i++){
                printf("%d ",next_ge[i]);
        }
}
```
## 43.Write a program to find the kth smallest element in an array.
```c
#include<stdio.h>
int main(){
        int arr[]={2,4,6,9,3};
        int len=sizeof(arr)/sizeof(arr[0]);
        int k;
        printf("enter the k values:");
        scanf("%d",&k);
        for(int i=0;i<len;i++){
                for(int j=i+1;j<len;j++){
                        if(arr[i]>arr[j]){
                                int temp=arr[i];
                                arr[i]=arr[j];
                                arr[j]=temp;
                        }
                }
        }
        if(k>0 && k<=len)
                printf("%d\n",arr[k-1]);
        else
                printf("Invalid k value outf bound");

}
```
## 44.Write a program to reverse a portion of an array.
```c
#include<stdio.h>
int main(){
        int arr[]={1,2,3,4,5,6,7,8,9};
        int len=sizeof(arr)/sizeof(arr[0]);
        int startindex,endindex;
        printf("Enter the strating index value:");
        scanf("%d",&startindex);
        printf("Enter the ending index value:");
        scanf("%d",&endindex);
        for(int i=startindex,j=endindex;j>i;i++,j--){
                int temp=arr[i];
                arr[i]=arr[j];
                arr[j]=temp;
        }
        printf("Array after reversing of particular portion of array:");
        for(int i=0;i<len;i++){
                printf("%d ",arr[i]);
        }
}
```
## 45. Write a c program to print all possible subarrays.
```c
#include<stdio.h>
int main(){
        int arr[]={1,2,3,4,5};
        for(int i=0;i<5;i++){
                for(int j=i;j<5;j++){
                        for(int k=i;k<=j;k++){
                                printf("%d",arr[k]);
                        }
                        printf("\n");
                }
        }
}
```
