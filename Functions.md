## 1.Write a function to swap to numbers using call by reference.
```c
#include<stdio.h>
int swap(int *x,int *y){
    int temp;
    temp=*x;
    *x=*y;
    *y=temp;
}
int main(){
    int a=10,b=20;
    printf("before Swapping: %d %d\n",a,b);
    swap(&a,&b);
    printf("After swapping: %d %d",a,b);
}
```
## 2.Write a function to reverse a number using pointer.
```c
#include<stdio.h>
int reverse(int,int*);
int main(){
    int num,x=0;
    printf("Enter the number:");
    scanf("%d",&num);
    reverse(num,&x);
    printf("Reverse of the number:%d",x);
}
int reverse(int n,int *rev){
    int rem;
    while(n>0){
        rem=n%10;
        *rev=*rev*10+rem;
        n=n/10;
    }
}
```
## 3.Write a function to print sum of even numbers in a number and product of odd numbers in a number.
```c
#include<stdio.h>
void sumprod(int num){
    int rem,sum=0,prod=1;
    while(num>0){
        rem=num%10;
        if(rem%2==0){
            sum=sum+rem;
        }
        else{
            prod=prod*rem;
        }
        num=num/10;
    }
    printf("Sum of Even numbers in a number=%d\n",sum);
    printf("Product of odd numbers in a number=%d",prod);
}
int main(){
    int a;
    printf("Enter the number:");
    scanf("%d",&a);
    sumprod(a);
}
