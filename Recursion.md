## 1.Factorial of a number using recursion.
```c
#include<stdio.h>
int factorial(int x){
        int fact;
        if(x==1)
                return 1;
        fact=x*factorial(x-1);
        return fact;
}
int main(){
        int n,f;
        printf("Enter the number:");
        scanf("%d",&n);
        f=factorial(n);
        printf("factorial of %d = %d",n,f);
}
```
## 2.Fibonacci series of a number using recursion.
```c
#include<stdio.h>
int fibonacci(int x){
        int f;
        if(x<0){
                printf("Invalid input");
                return -1;
        }
        if(x==0)
                return 0;
        if(x==1)
                return 1;
        f=fibonacci(x-1)+fibonacci(x-2);
        return f;
}
int main(){
        int n,f;
        printf("Enter the number:");
        scanf("%d",&n);
        for(int i=0;i<n;i++){
                printf("%d ",fibonacci(i));
        }
        return 0;
}
```
## 3.Finding prime number using recursion.
```c
#include<stdio.h>
int isprime(int x,int y){
        if(x<2)
                return 0;
        if(y==1)
                return 1;
        if(x%y==0)
                return 0;
        return isprime(x,y-1);
}
int main(){
        int n;
        printf("Enter the number:");
        scanf("%d",&n);
        if(isprime(n,n/2))
                printf("%d is a prime number",n);
        else
                printf("%d is not a prime number",n);
}
```
## 4.Program to display and find out the sum of series.
```c
#include<stdio.h>
int sumofdigits(int n){
    int s=0;
    if(n==1){
        printf("1");
       return 1;
    }
    else{
        s=sumofdigits(n-1);
        printf(" + %d",n);
        return s+n;
    }
}
int main(){
    int sum;
    sum=sumofdigits(5);
    printf("\nSum=%d",sum);
}
```
## 5.Program to convert a positive decimal number to Binary,Octal and Hexadecimal using recursion.
```c
#include<stdio.h>
void convert(int num,int base){
    int rem=num%base;
    if(num==0)
      return;
    convert(num/base,base);
    if(rem<10)
    printf("%d ",rem);
    else
    printf("%c ",rem-10+'A');
}
int main(){
    int n;
    printf("Enter the number:");
    scanf("%d",&n);
    printf("Number in Binary form:");
    convert(n,2);
    printf("\n");
    printf("Number in Octal form:");
    convert(n,8);
    printf("\n");
    printf("Number in Hexadecimal form:");
    convert(n,16);
    printf("\n");
}
```
## 6.Program to raise a floating point number to Positive number using recursion.
```c
#include<stdio.h>
#include<math.h>
float power(float a,int n){
    if(n==0)
       return 1;
    else
        return a*power(a,n-1);
}
int main(){
    float a,p;
    int n;
    printf("Enter the a value:");
    scanf("%f",&a);
    printf("Enter the n value:");
    scanf("%d",&n);
    p=power(a,n);
    printf("%f raised to power %d is %f",a,n,p);
    
}
```
## 7.The recursive function for printing the prime factors of a number.
```c
#include<stdio.h>
void PFactors(int num){
    int i=2;
    if(num==1)
      return;
    while(num%i!=0)
        i++;
    printf("%d ",i);
    return PFactors(num/i);
}
int main(){
    int n;
    printf("Enter the number:");
    scanf("%d",&n);
    PFactors(n);
}
```
## 8.GCD of a number using Recursion.
```c
#include<stdio.h>
int gcd(int x,int y){
    if(y==0)
    return x;
    else 
    return gcd(y,x%y);
}
int main(){
    int a,b,c;
    printf("Enter the a value:");
    scanf("%d",&a);
    printf("Enter the b value:");
    scanf("%d",&b);
    c=gcd(a,b);
    printf("%d",c);
}
```
