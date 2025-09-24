## 1.Write a Program to print the address of variables using the address operator.
```c
#include<stdio.h>
int main(){
        int a=10;
        printf("%x",&a);
}
```
## 2. Write a program to print size of pointer variables.
```c
#include<stdio.h>
int main(){
        int *ptr;
        printf("Size of int pointer:%zu",sizeof(ptr));
}
```
## 3. Write a program to print size of pointer variables and size of values Dereferenced by them.
```c
#include<stdio.h>
int main(){
        int a=10;
        int *p=&a;
        printf("size of pointer variables:%zu\n",sizeof(p));
        printf("size of values:%zu",sizeof(*p));
}
```
## 4. Write a program to illustrate the dereferencing of pointers.
```c
#include<stdio.h>
int main(){
        int a=10;
        int *p=&a;
        printf("value of a :%d\n",a);
        printf("address of value:%p\n",(void*)&a);
        printf("address of stored in pointer:%p\n",(void*)p);
        printf("value pointed to pointer:%d",*p);
}
```
## 5.C program to illustrate pointer arithmetic.
```c
#include<stdio.h>
int main(){
        int *ptr;
        printf("Initially address in p : %x\n",ptr);
        printf("Address after p+1 : %x\n",ptr+1);
        printf("Address after p+2 : %x\n",ptr+2);
        printf("Address after p+3 : %x\n",ptr+3);
}
```
## 6.Write a program to declare an integer variable a, assign it a value, then declare a pointer variable, assign it the address of a, and finally print the value of a using the pointer variable.
```c
#include<stdio.h>
int main(){
        int a=10;
        int *ptr=&a;
        printf("%d\n",*ptr);
}
```
## 7.Write a program to print postfix/prefix increment/decrement in a pointer variable of base type int*.
```c
#include<stdio.h>
int main(){
        int *ptr;
        printf("Intially ptr address  : %x\n",ptr);
        printf("After pre-increment of ptr address : %x\n",++ptr);
        printf("After post-increment of ptr address : %x\n",ptr++);
        printf("After pre-decrement of ptr address : %x\n",--ptr);
        printf("After post-decrement of ptr address : %x\n",ptr--);
}
```
## 8.Write a Program to print the value and address of elements of an array using pointers notation.
```c
#include<stdio.h>
int main(){
        int n;
        printf("Enter the size of the array:");
        scanf("%d",&n);
        int arr[n];
        printf("Enter the elements in the array:");
        for(int i=0;i<n;i++){
                scanf("%d",&arr[i]);
        }
        int *ptr=arr;
        printf("Values and their address\n");
        for(int i=0;i<n;i++){
                printf("Value=%d  Address=%x\n",arr[i],ptr++);
        }
}
```
## 9.Write a program to print the value of array elements using pointers and subscript notation.
```c
#include<stdio.h>
int main(){
        int n;
        printf("Enter the size of the array:");
        scanf("%d",&n);
        int arr[n];
        printf("Enter the elements in the array:\n");
        for(int i=0;i<n;i++){
                scanf("%d",&arr[i]);
        }
        int *ptr=arr;
        printf("values in the array:\n");
        for(int i=0;i<n;i++){
                printf("Value:%d\n",ptr[i]);
        }
}
```
## 10. program to print the values and address of elements of 2-d array.
```c
#include<stdio.h>
int main(){
        int r,c;
        printf("Enter the number of rows and columns:");
        scanf("%d %d",&r,&c);
        int arr[r][c];
        printf("Enter the elements in 2D array:");
        for(int i=0;i<r;i++){
                for(int j=0;j<c;j++){
                        scanf("%d",&arr[i][j]);
                }
        }
        int *ptr=&arr[0][0];
        printf("Values and its address:\n");
        for(int i=0;i<r;i++){
                for(int j=0;j<c;j++){
                        printf("values of arr[%d][%d]=%d\tAddress=%p\n",i,j,*(ptr+i*c+j),(ptr+i*c+j));
                }
        }
}
```
## 11.Program to print elements of a 2-D array by subscripting a pointer to an array variable.
```c
#include<stdio.h>
int main(){
        int arr[3][3];
        for(int i=0;i<3;i++){
                for(int j=0;j<3;j++){
                        scanf("%d",&arr[i][j]);
                }
        }
        int (*ptr)[3];
        ptr=arr;
        for(int i=0;i<3;i++){
                for(int j=0;j<3;j++){
                        printf("%2d",ptr[i][j]);
                }
                printf("\n");
        }
}
```
## 12.Program to print elements of a 3-D array using pointer notation.
```c
#include<stdlib.h>
int main(){
        int x,y,z;
        printf("Enter the x,y and z values:");
        scanf("%d %d %d",&x,&y,&z);
        int *arr=(int *)malloc(x*y*z*sizeof(int));
        if(arr==NULL){
                printf("malloc error");
                return 0;
        }
        printf("Enter the elements in 3D array:\n");
        for(int i=0;i<x;i++){
                for(int j=0;j<y;j++){
                        for(int k=0;k<z;k++){
                                scanf("%d",arr+i*y*z+j*z+k);
                        }
                }
        }
        for(int i=0;i<x;i++){
                for(int j=0;j<y;j++){
                        for(int k=0;k<z;k++){
                                printf("Value at arr[%d][%d][%d]=%d\tAddress=%p\n",i,j,k,*(arr+i*(y*x)+j*x+k),(arr+i*(y*x)+j*x+k));
                        }
                }
        }
}
```
## 13. Implement a function to copy one string into another using pointers, without using any standard library functions.
```c
#include<stdio.h>
#include<string.h>
int copystr(char *str1,char *str2){
        while(*str1!='\0'){
                *str2=*str1;
                str1++;
                str2++;
        }
        *str2='\0';
}
int main(){
        char str1[]="Linux";
        int len=strlen(str1);
        char str2[len];
        copystr(str1,str2);
        printf("%s",str2);
}
```
## 14. Write a program to print array of pointer.
```c
#include<stdio.h>
int main(){
        int a=1,b=2,c=3,d=4,e=5;
        int *arr[5];
        arr[0]=&a;
        arr[1]=&b;
        arr[2]=&c;
        arr[3]=&d;
        arr[4]=&e;
        for(int i=0;i<5;i++){
                printf("%d ",*arr[i]);
        }
}
```
## 15.Write a program to print pointer to an array.
```c
#include<stdio.h>
int main(){
        int arr[5];
        int (*ptr)[5]=&arr;
        printf("Enter the elements in an array:");
        for(int i=0;i<5;i++){
                scanf("%d",&(*ptr)[i]);
        }
        printf("Elements in the array are:");
        for(int i=0;i<5;i++){
                printf("%d ",(*ptr)[i]);
        }
}
```
## 16. Write a C program to remove all vowels in a string using pointer notations.
```c
#include<stdio.h>
#include<string.h>
#include<ctype.h>
int main(){
        char str[100],res[100];
        printf("Enter the string:");
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        int k=0;
        char *p=str;
        while(*p!='\0'){
                *p=tolower(*p);
                if(*p!='a'&&*p!='e'&&*p!='i'&&*p!='o'&&*p!='u'){
                        res[k++]=*p;
                }
                p++;
        }
        printf("string after removal of all vowels:%s",res);
}
```
## 17.Write a C program to Swap two arrays using pointers.
```c
#include<stdio.h>
int main(){
        int arr1[]={1,2,3,4,5};
        int arr2[]={6,7,8,9,10};
        int len1=sizeof(arr1)/sizeof(arr1[0]);
        int len2=sizeof(arr2)/sizeof(arr2[0]);
        int *ptr1=arr1;
        int *ptr2=arr2;
        for(int i=0;i<len1;i++){
                int temp=*(ptr1+i);
                *(ptr1+i)=*(ptr2+i);
                *(ptr2+i)=temp;
        }
        printf("Arrays after swapping:\n");
        for(int i=0;i<len1;i++){
                printf("%d ",arr1[i]);
        }
        printf("\n");
        for(int i=0;i<len2;i++){
                printf("%d ",arr2[i]);
        }
}
```
