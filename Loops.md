## 1.WRITE A PROGRAM IN C TO PRINT THE ARMSTRONG NUMBERS BETWEEN 1 AND 1000 USING A FOR LOOP?
```c
#include<stdio.h>
int main(){
    int rem,sum,cube,temp;
    for(int i=0;i<1000;i++){
        temp=i;
        sum=0;
        while(temp>0){
            rem=temp%10;
            cube=rem*rem*rem;
            sum=sum+cube;
            temp=temp/10;
        }
        if(sum==i)
        printf("%d\n",i);
    }
}
```
## 2..WRITE A PROGRAM IN C TO IMPLEMENT A SIMPLE CALCULATOR USING SWITCH-CASE STATEMENTS?
```c
#include<stdio.h>
int c;
 void add(int x,int y){
        c=x+y;
        printf("Addition=%d",c);
    }
    void sub(int x,int y){
        c=x-y;
        printf("Subtraction=%d",c);
    }
    void mult(int x,int y){
        c=x*y;
        printf("Multiplication=%d",c);
    }
    void divi(int x,int y){
        if(y!=0){
        c=x/y;
        printf("Divison=%d",c);
        }
        else
        printf("denominator cannot be zero");
    }
    void mdiv(int x,int y){
        if(y!=0){
             c=x%y;
        printf("Divison=%d",c);
        }
        else
        printf("denominator cannot be zero");
    }
int main(){
    int op;
    int a,b;
    printf("Enter 1 for addition\n");
    printf("Enter 2 for subtraction\n");
    printf("Enter 3 for Multiplication\n");
    printf("Enter 4 for divison\n");
    printf("Enter 5 for Modular divison\n");
    printf("Enter option:");
    scanf("%d",&op);
    printf("Enter a and b values:\n");
    scanf("%d %d",&a,&b);
    switch(op){
        case 1:
             add(a,b);
             break;
        case 2:
             sub(a,b);
             break;
        case 3:
              mult(a,b);
              break;
        case 4:
              divi(a,b);
              break;
        case 5:
              mdiv(a,b);
              break;
        default:
            printf("Inavalid");
    }
    
}
```
## 3.WRITE A C PROGRAM TO FIND THE SUM OF ALL PRIME NUMBERS BETWEEN 1 AND 1000 USING LOOPS AND IF-ELSE STATEMENTS?
```c
#include<stdio.h>
int main(){
    int found=1;
    for(int i=2;i<=1000;i++){
        found=1;
        for(int j=2;j<i/2;j++){
            if(i%j==0){
                found=0;
                break;
            }
        }
        if(found==1){
            sum=sum+i;
         }
    }
    printf("%d",sum);
}
```
## 4.Write a C Program to reverse a given number.
```c
#include<stdio.h>
int main(){
        int num,rev=0,isnegative=0;
        printf("Enter the number:");
        scanf("%d",&num);
        if(num<0){
                num=-num;
                isnegative=1;
        }
        while(num>0){
                rev=(rev*10)+(num%10);
                num=num/10;
        }
        if(isnegative)
                rev=-rev;
        printf("Number after reversing:%d",rev);
}

```
## 5.WRITE A C PROGRAM TO CHECK WHETHER A GIVEN NUMBER IS A PALINDROME IN BOTH DECIMAL AND BINARY REPRESENTATIONS USING LOOPS AND IF-ELSE STATEMENTS?
```c
#include<stdio.h>
int main(){
        int num,rem,arr1[15],arr2[15];
        int temp;
        int flag=1;
        printf("Enter the number:");
        scanf("%d",&num);
        temp=num;
        int rev=0;
        int original=num;
        while(num>0){
                rem=num%10;
                rev=rev*10+rem;
                num=num/10;
        }
        if(original==rev)
                printf("Palindrome\n");
        else
                printf("Not a Palindrome\n");
        int k=0;
        while(temp>0){
                arr1[k++]=temp%2;
                temp=temp/2;
        }
        printf("Binary format of %d is : ",original);
        for(int i=0;i<k;i++){
                printf("%d",arr1[i]);
        }
        int j=0;
        for(int i=k-1;i>=0;i--){
                arr2[j++]=arr1[i];
        }
        printf("\nBinary format of %d after revesing:",original);
        for(int i=0;i<j;i++){
                printf("%d",arr2[i]);
        }
        printf("\n");
        for(int i=0;i<j;i++){
                if(arr1[i]!=arr2[i]){
                        flag=0;
                        break;
                }
        }
        if(flag)
                printf("Two binary formats are equal\n");
        else
                printf("Binary formats are not equal\n");

}
```
## 6.WRITE A C PROGRAM TO ENTER WEEK NUMBER AND PRINT DAY OF WEEK?
```c
#include<stdio.h>
int main(){
        int n;
        printf("Enter the number of day:");
        scanf("%d",&n);
        switch(n){
                case 1:printf("Monday");
                         break;
                case 2:printf("Tuesday");
                         break;
                case 3:printf("Wednesday");
                         break;
                case 4:printf("Thrusday");
                         break;
                case 5:printf("Friday");
                         break;
                case 6:printf("Saturday");
                         break;
                case 7:printf("Sunday");
                         break;
                default :printf("Invalid");
        }
}
```
## 7.WRITE A C PROGRAM TO FIND NUMBER OF DAYS IN MONTH?
```c
#include<stdio.h>
int main(){
        int n,year;
        printf("Enter the month number:");
        scanf("%d",&n);
        printf("Enter the year:");
        scanf("%d",&year);
        switch(n){
                case 1:
                case 3:
                case 5:
                case 7:
                case 8:
                case 10:
                case 12:printf("31 Days\n");
                        break;
                case 4:
                case 6:
                case 9:
                case 11:printf("30 Days\n");
                        break;
                case 2:
                        if(year%400==0||(year%4==0 && year%100!=0)){
                                printf("29 Days\n");
                        }
                        else{
                                printf("28 Days\n");
                        }
                        break;
                default :printf("Inavalid Input\n");
        }
}
```
## 8.WRITE A C PROGRAM TO FIND MAXIMUM BETWEEN TWO NUMBERS USING SWITCH CASE?
```c
#include<stdio.h>
int main(){
        int a,b;
        printf("Enter the a and values:");
        scanf("%d %d",&a,&b);
        switch(a>b){
                case 1 :printf("Maximum number:%d\n",a);
                        break;
                case 0 :
                        switch(b>a){
                                case 1:printf("Maximum number:%d\n",b);
                                       break;
                                case 0:printf("Both numbers are equal\n");
                                       break;
                        }
                        break;
                }
}
```
## 9.WRITE A C PROGRAM TO FIND THE FACTORIAL OF A GIVEN NUMBER USING A FOR LOOP?
```c
#include<stdio.h>
int main(){
        int n,fact=1;
        printf("Enter the number:");
        scanf("%d",&n);
        if(n<0){
                printf("Factrorial is not defined for negative numbers\n");
        }
        else{
                   for(int i=1;i<=n;i++){
                        fact=fact*i;
                   }
                   printf("factorial of %d : %d\n",n,fact);
        }
}
```
## 10.WRITE A C PROGRAM TO CHECK WHETHER A GIVEN NUMBER IS PRIME OR NOT USING A WHILE LOOP?
```c
#include<stdio.h>
int main(){
        int n,flag=0;
        printf("Enter the number:");
        scanf("%d",&n);
        if(n<=1)
                printf("%d is not a prime number\n",n);
        int i=2;
        while(i<=n/2){
                if(n%i==0){
                        flag=1;
                        break;
                }
                i++;
        }
        if(flag)
                printf("%d is not a prime number\n",n);
        else
                printf("%d is a prime number\n",n);
}
```
## 11.WRITE A C PROGRAM TO PRINT FIBONACCI SERIES UP TO N TERMS USING A FOR LOOP?
```c
#include<stdio.h>
int main(){
        int a,b,c,n;
        a=0,b=1;
        printf("Enter the number:");
        scanf("%d",&n);
        printf("Fibanacci series:");
        for(int i=1;i<=n;i++){
                printf("%d ",a);
                c=a+b;
                a=b;
                b=c;
        }
        printf("\n");
}
```
## 12.WRITE A C PROGRAM TO FIND THE POWER OF A NUMBER USING A FOR LOOP?
```c
#include<stdio.h>
int main(){
        int base,exp,i=1;
        int result=1;
        printf("Enter the base:");
        scanf("%d",&base);
        printf("Enter the exponent:");
        scanf("%d",&exp);
        if(exp<0)
                printf("power should be a non-negative number\n");
        else{
                while(i<=exp){
                        result=result*base;
                        i++;
                }
                printf("%d^%d = %d\n",base,exp,result);
        }
}
```
## 13.WRITE A C PROGRAM TO CHECK WHETHER A GIVEN NUMBER IS A PERFECT SQUARE OR NOT USING LOOPS AND IF-ELSE STATEMENTS.
```c
#include<stdio.h>
int main(){
        int n,flag=0;
        printf("Enter the number:");
        scanf("%d",&n);
        int i=1;
        if(n<=0)
                printf("%d is not a perfect square\n",n);
        while(i*i<=n){
                if(i*i==n){
                        flag=1;
                        break;
                }
                i++;
        }
        if(flag)
                printf("%d is a perfect square\n",n);
        else
                printf("%d is not a perfect square\n",n);
}
```
## 13.WRITE A C PROGRAM TO FIND THE ASCII VALUE OF A CHARACTER USING LOOPS AND IF-ELSE STATEMENTS?
```c
#include<stdio.h>
int main(){
        char ch;
        int i=0;
        printf("Enter the character:");
        scanf("%c",&ch);
        while(i<=127){
                if(ch==i){
                        printf("Ascii value of %c is %d\n",ch,i);
                        break;
                }
                i++;
        }
}
```
## 14.WRITE A C PROGRAM TO FIND THE LARGEST ELEMENT IN AN ARRAY USING A FOR LOOP?
```c
#include<stdio.h>
#include<limits.h>
int main(){
        int arr[]={2,3,6,4,9,1};
        int i=0,max=INT_MIN;
        int len=sizeof(arr)/sizeof(arr[0]);
        while(i<len){
                if(arr[i]>max){
                        max=arr[i];
                }
                i++;
        }
        printf("Largest element in an array:%d\n",max);
}
```
## 15.WRITE A C PROGRAM TO FIND THE SMALLEST ELEMENT IN AN ARRAY USING A WHILE LOOP?
```c
#include<stdio.h>
#include<limits.h>
int main(){
        int arr[]={2,3,6,4,9,1};
        int i=0,min=INT_MAX;
        int len=sizeof(arr)/sizeof(arr[0]);
        while(i<len){
                if(arr[i]<min){
                        min=arr[i];
                }
                i++;
        }
        printf("Smallest element in an array:%d\n",min);
}
```
## 16.WRITE A C PROGRAM TO PRINT ALL THE ELEMENTS OF AN ARRAY USING A FOR LOOP?
```c
#include<stdio.h>
int main(){
        int n;
        printf("Enter array size:");
        scanf("%d",&n);
        int arr[n];
        printf("Enter the elements in the array:");
        for(int i=0;i<n;i++){
                scanf("%d",&arr[i]);
        }
        printf("\n");
        printf("Elements in array are:");
        for(int i=0;i<n;i++){
                printf("%d ",arr[i]);
        }
        printf("\n");
}
```
## 17.WRITE A C PROGRAM TO FIND THE SUM OF ELEMENTS IN AN ARRAY USING A WHILE LOOP?
```c
#include<stdio.h>
int main(){
        int n,sum=0;
        printf("Enter array size:");
        scanf("%d",&n);
        int arr[n];
        printf("Enter the elements in the array:");
        for(int i=0;i<n;i++){
                scanf("%d",&arr[i]);
        }
        for(int i=0;i<n;i++){
                sum+=arr[i];
        }
        printf("sum of the elements:%d\n",sum);
}
```
## 18.WRITE A PROGRAM IN C TO FIND THE SUM OF ELEMENTS IN THE LOWER TRIANGULAR MATRIX USING LOOPS AND IF-ELSE STATEMENTS?
```c
#include<stdio.h>
#define r 3
#define c 3
int main(){
        int arr[r][c],sum=0;
        printf("Enter the elements in the matrix:\n");
        for(int i=0;i<r;i++){
                for(int j=0;j<c;j++){
                        scanf("%d",arr[i][j]);
                }       
        }       
        for(int i=0;i<r;i++){
                for(int j=0;j<=i;j++){
                        sum+=arr[i][j];
                }       
        }       
        printf("sum of elements in lower triangular matrix:%d",sum);
}
```
## 19.WRITE A PROGRAM IN C TO FIND THE SUM OF ELEMENTS IN THE UPPER TRIANGULAR MATRIX USING LOOPS AND IF-ELSE STATEMENTS?
```c
#include<stdio.h>
#define r 3
#define c 3
int main(){
        int arr[r][c],sum=0;
        printf("Enter the elements in the matrix:\n");
        for(int i=0;i<r;i++){
                for(int j=0;j<c;j++){
                        scanf("%d",&arr[i][j]);
                }
        }
        for(int i=0;i<r;i++){
                for(int j=i;j<c;j++){
                        sum+=arr[i][j];
                }
        }
        printf("sum of elements in upper triangular matrix:%d\n",sum);
}
```
## 20.WRITE A PROGRAM IN C TO CHECK WHETHER A MATRIX IS AN IDENTITY MATRIX OR NOT USING LOOPS AND IF-ELSE STATEMENTS?
```c
#include<stdio.h>
#define r 3
#define c 3
int main(){
        int arr[r][c],flag=0;
        printf("Enter the elements in the matrix:\n");
        for(int i=0;i<r;i++){
                for(int j=0;j<c;j++){
                        scanf("%d",&arr[i][j]);
                }
        }
        for(int i=0;i<r;i++){
                for(int j=0;j<c;j++){
                        if(i==j && arr[i][j]!=1){
                                flag=1;
                                break;
                        }
                        if(i!=j && arr[i][j]!=0){
                                flag=1;
                                break;
                        }
                }
                if(flag==1)
                        break;
        }
        if(flag==0)
                printf("Identity matrix\n");
        else
                printf("Not an identity matrix\n");
}
```
## 21.WRITE A PROGRAM IN C TO FIND THE SUM OF ELEMENTS IN EACH ROW OF A MATRIX USING LOOPS AND IF-ELSE STATEMENTS?
```c
#include<stdio.h>
#define r 3
#define c 3
int main(){
        int arr[r][c],sum=0;
        printf("Enter the elements in the matrix:\n");
        for(int i=0;i<r;i++){
                for(int j=0;j<c;j++){
                        scanf("%d",&arr[i][j]);
                }
        }
        for(int i=0;i<r;i++){
                sum=0;
                for(int j=0;j<c;j++){
                        sum+=arr[i][j];
                }
                printf("sum of %d row : %d\n",i,sum);
        }
}
```
## 22.WRITE A PROGRAM IN C TO FIND THE SUM OF ELEMENTS IN EACH COLUMN OF A MATRIX USING LOOPS AND IF-ELSE STATEMENTS?
```c
#include<stdio.h>
#define r 3
#define c 3
int main(){
        int arr[r][c],sum=0;
        printf("Enter the elements in the matrix:\n");
        for(int i=0;i<r;i++){
                for(int j=0;j<c;j++){
                        scanf("%d",&arr[i][j]);
                }
        }
        for(int i=0;i<r;i++){
                sum=0;
                for(int j=0;j<c;j++){
                        sum+=arr[j][i];
                }
                printf("sum of %d column : %d\n",i,sum);
        }
}
```
## 23..WRITE A C PROGRAM TO PRINT THE PATTERN OF STARS IN A HOLLOW SQUARE SHAPE USING LOOPS AND IF-ELSE STATEMENTS?
```c
#include<stdio.h>
int main(){
        int n;
        printf("Enter the size of square:");
        scanf("%d",&n);
        for(int i=0;i<n;i++){
                for(int j=0;j<n;j++){
                        if(i==0||i==n-1||j==0||j==n-1)
                                printf("* ");
                        else
                                printf("  ");
                }
                printf("\n");
        }
}
```
## 24.WRITE A C PROGRAM TO PRINT THE PATTERN OF STARS IN A RIGHT TRIANGLE SHAPE USING LOOPS AND IF-ELSE STATEMENTS.
```c
#include<stdio.h>
#define r 3
#define c 3
int main(){
        for(int i=0;i<r;i++){
                for(int j=0;j<=i;j++){
                        printf("* ");
                }
                printf("\n");
        }
}
```
## 25.WRITE A C PROGRAM TO PRINT THE PATTERN OF STARS IN A LEFT RIGHT TRIANGLE SHAPE USING LOOPS AND IF-ELSE STATEMENTS?
```c
#include<stdio.h>
#define r 3
#define c 3
int main(){
        for(int i=0;i<r;i++){
                for(int j=c-1;j>=i;j--){
                        printf("* ");
                }
                printf("\n");
        }
}
```
## 26.WRITE A C PROGRAM TO PRINT THE PATTERN OF STARS IN A MIRRORED RIGHT TRIANGLE SHAPE USING LOOPS AND IF-ELSE STATEMENTS?
```c
#include<stdio.h>
#define r 3
#define c 3
int main(){
        for(int i=0;i<r;i++){
                for(int j=0;j<c;j++){
                        if(j<c-i-1)
                                printf("  ");
                        else
                                printf("* ");
                }
                printf("\n");
        }
}
```
## 27.WRITE A C PROGRAM TO PRINT THE PATTERN OF STARS IN A PYRAMID SHAPE USING LOOPS AND IF-ELSE STATEMENTS?
```c
#include<stdio.h>
int main(){
        int n;
        printf("Enter the number of rows:");
        scanf("%d",&n);
        for(int i=0;i<n;i++){
                for(int j=0;j<n-i;j++){
                        printf(" ");
                }
                for(int j=0;j<=i;j++){
                        printf("* ");
                }
                printf("\n");
        }
}
```
## 28.WRITE A C PROGRAM TO PRINT THE PATTERN OF STARS IN A MIRRORED PYRAMID SHAPE USING LOOPS AND IF-ELSE STATEMENTS?
```c
#include<stdio.h>
int main(){
        int n;
        printf("Enter the number of rows:");
        scanf("%d",&n);
        for(int i=0;i<n;i++){
                for(int j=0;j<n-i-1;j++){
                        printf(" ");
                }
                for(int j=0;j<=i;j++){
                        printf("*");
                }
                printf("\n");
        }
}
```
## 29.WRITE A C PROGRAM TO PRINT THE PATTERN OF STARS IN A DIAMOND SHAPE USING LOOPS AND IF-ELSE STATEMENTS?
```c
#include<stdio.h>
int main(){
        int n;
        printf("Enter the number of rows:");
        scanf("%d",&n);
        for(int i=0;i<n;i++){
                for(int j=0;j<n-i-1;j++){
                        printf(" ");
                }
                for(int j=0;j<2*i+1;j++){
                        printf("*");
                }
                printf("\n");
        }
        for(int i=n-2;i>=0;i--){
                for(int j=0;j<n-i-1;j++){
                        printf(" ");
                }
                for(int j=0;j<2*i+1;j++){
                        printf("*");
                }
                printf("\n");
        }
}
```
## 30.WRITE A C PROGRAM TO PRINT THE PATTERN OF STARS IN A HOLLOW DIAMOND SHAPE USING LOOPS AND IF-ELSE STATEMENTS?
```c
#include<stdio.h>
int main(){
        int n;
        printf("Enter the number of rows:");
        scanf("%d",&n);
        for(int i=0;i<n;i++){
                for(int j=0;j<n-i-1;j++){
                        printf(" ");
                }
                for(int j=0;j<2*i+1;j++){
                        if(j==0 || j==2*i)
                                printf("*");
                        else
                                printf(" ");
                }
                printf("\n");
        }
        for(int i=n-2;i>=0;i--){
                for(int j=0;j<n-i-1;j++){
                        printf(" ");
                }
                for(int j=0;j<2*i+1;j++){
                        if(j==0 || j==2*i)
                                printf("*");
                        else
                                printf(" ");
                }
                printf("\n");
        }
}
```
## 31.WRITE A C PROGRAM TO PRINT THE PATTERN OF NUMBERS IN A PYRAMID SHAPE USING LOOPS AND IF-ELSE STATEMENTS?
```c
#include<stdio.h>
int main(){
        int n;
        printf("Enter the number of rows:");
        scanf("%d",&n);
        for(int i=1;i<=n;i++){
                for(int j=1;j<=n-i;j++){
                        printf(" ");
                }
                for(int j=1;j<=i;j++){
                        printf("%d ",j);
                }
                printf("\n");
        }
}
```
## 32.WRITE A C PROGRAM TO PRINT THE PATTERN OF NUMBERS IN A MIRRORED PYRAMID SHAPE USING LOOPS AND IF-ELSE STATEMENTS?
```c
#include<stdio.h>
int main(){
        int n;
        printf("Enter the number of rows:");
        scanf("%d",&n);
        for(int i=1;i<=n;i++){
                for(int j=1;j<=n-i;j++){
                        printf("  ");
                }
                for(int j=1;j<=i;j++){
                        printf("%d ",j);
                }
                for(int j=i-1;j>=1;j--){
                        printf("%d ",j);
                }
                printf("\n");
        }
}
```
## 33.WRITE A C PROGRAM TO PRINT THE PATTERN OF NUMBERS IN A RIGHT TRIANGLE SHAPE USING LOOPS AND IF-ELSE STATEMENTS?
```c
#include<stdio.h>
int main(){
        int n;
        printf("Enter the number of rows:");
        scanf("%d",&n);
        for(int i=1;i<=n;i++){
                for(int j=1;j<=i;j++){
                        printf("%d ",j);
                }
                printf("\n");
        }
}
```
## 34.WRITE A C PROGRAM TO PRINT THE PATTERN OF NUMBERS IN A MIRRORED RIGHT TRIANGLE SHAPE USING LOOPS AND IF-ELSE STATEMENTS?
```c
#include<stdio.h>
int main(){
        int n;
        printf("Enter the number of rows:");
        scanf("%d",&n);
        for(int i=1;i<=n;i++){
                for(int j=1;j<=n-i;j++){
                        printf("  ");
                }
                for(int j=1;j<=i;j++){
                        printf("%d ",j);
                }
                printf("\n");
        }
}
```
## 35.WRITE A C PROGRAM TO PRINT THE PATTERN OF ALPHABETS IN A PYRAMID SHAPE USING LOOPS AND IF-ELSE STATEMENTS?
```c
#include<stdio.h>
int main(){
        int n;
        printf("Enter the number of rows:");
        scanf("%d",&n);
        for(int i=1;i<=n;i++){
        for(int j=1;j<=n-i;j++){
                printf(" ");
        }
        for(int j=1;j<=i;j++){
                printf("%c ",j+64);
        }
        printf("\n");
        }
}
```
## 36.WRITE A C PROGRAM TO PRINT THE PATTERN OF ALPHABETS IN A MIRRORED PYRAMID SHAPE USING LOOPS AND IF-ELSE STATEMENTS?
```c
#include<stdio.h>
int main(){
        int n;
        printf("Enter the number of rows:");
        scanf("%d",&n);
        for(int i=1;i<=n;i++){
        for(int j=1;j<=n-i;j++){
                printf("  ");
        }
        for(int j=1;j<=i;j++){
                printf("%c ",j+64);
        }
        for(int j=i-1;j>=1;j--){
                printf("%c ",j+64);
        }
        printf("\n");
        }
}
```
## 37.WRITE A C PROGRAM TO PRINT THE PATTERN OF ALPHABETS IN A RIGHT TRIANGLE SHAPE USING LOOPS AND IF-ELSE STATEMENTS?
```c
#include<stdio.h>
int main(){
        int n;
        printf("Enter the number of rows:");
        scanf("%d",&n);
        for(int i=0;i<n;i++){
                for(int j=0;j<=i;j++){
                        printf("%c ",j+65);
                }
                printf("\n");
        }
}
```
## 38.A program in C to check whether the system stores data in Big Endian or Little Endian format.
```c
#include<stdio.h>
int main(){
        int num=1;
        char *p=(char *)&num;
        if(*p==1)
                printf("Little indian");
        else
                printf("Big indian");
}
```
