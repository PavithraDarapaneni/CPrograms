## 1.Write a C program to demonstrate use of bitwise opeartors.
```c
#include<stdio.h>
int main(){
        int a,b;
        printf("Enter the a and b values:");
        scanf("%d %d",&a,&b);
        printf("a & b=%d\n",a & b);
        printf("a | b=%d\n",a | b);
        printf("a ^ b=%d\n",a ^ b);
        printf("~a=%d\n",~a);
        printf("b<<1=%d\n",b<<1);
        printf("b>>1=%d\n",b>>1);
        return 0;
}
```
## 2.Write a C program to check whether the k-th bit of a given integer n is set (i.e., 1) or not.
```c
#include<stdio.h>
void kthbit(int n,int k){
        if((n&(1<<(k-1)))!=0)
                printf("yes");
        else
                printf("no");
}
int main(){
        int n,k;
        printf("enter the n value:");
        scanf("%d",&n);
        printf("enter the kth value:");
        scanf("%d",&k);
        kthbit(n,k);
}
```
## 3.Set the ith bit of a number.
```c
#include<stdio.h>
int setithbit(int n,int i){
        return (1<<(i-1)|n);
                        }
int main(){
      int n,i,num;
      printf("Enter the n value:");
      scanf("%d",&n);
      printf("Enter the ith value:");
      scanf("%d",&i);
      num=setithbit(n,i);
      printf("Number after set the ith bit:%d",num);
      }
```
## 4. clear the ith bit of a number.
```c
#include<stdio.h>
int clearithbit(int n,int i){
        int mask=~(1<<(i-1));
        return (mask&n);
}
int main(){
        int n,i,num;
        printf("Enter the n value:");
        scanf("%d",&n);
        printf("Enter the i value:");
        scanf("%d",&i);
        num=clearithbit(n,i);
        printf("Number after clearing the ith bit:%d",num);
}
```
## 5. Remove the last set bit of a number.
```c
#include<stdio.h>
int removelastbit(int n){
        return (n&(n-1));
}
int main(){
        int n,num;
        printf("Enter the number:");
        scanf("%d",&n);
        num=removelastbit(n);
        printf("Number after removing last bit:%d",num);
}
```
## 6.Write a C program to clear 4th and 2nd bit of the number input by the user.
```c
#include<stdio.h>
int clear4and2bit(int a){
        int result;
        result = a & ~ ((1<<3)|(1<<1));
        return result;
}
int main(){
        int num,res;
        printf("Enter the number:");
        scanf("%d",&num);
        res=clear4and2bit(num);
        printf("result=%d",res);
}
```
## 7.Write a program to find state of 3rd and 2nd bit.
```c
#include<stdio.h>
void checkbit(int num){
        if(((1<<2)&num)!=0)
                printf("state of the 3rd position is 1\n");
        else
                printf("state of the 3rd position is 0\n");
        if(((1<<1)&num)!=0)
                printf("state of the 2nd position is 1\n");
        else
                printf("state of the 2nd position is 0\n");
}
int main(){
        int num;
        printf("Enter the number:");
        scanf("%d",&num);
        checkbit(num);
}
```
## 8.Write a program to toggle 7th,5th,4th and 1st bits.
```c
#include<stdio.h>
int toggle(int n){
        int mask,res;
        mask=((1<<6)|(1<<4)|(1<<3)|(1<<0));
        res=n^mask;
        return res;
}
int main(){
        int num,result;
        printf("Enter the number:");
        scanf("%d",&num);
        result=toggle(num);
        printf("Result=%d\n",result);
}
```
## 9.Write a program to count number of set bits in a number input by user.
```c
#include<stdio.h>
int countsetbit(int n){
        int count;
        while(n>0){
                if(n&1)
                        count++;
                n=n>>1;
        }
        return count;
}
int main(){
        int num,res;
        printf("Enter the number:");
        scanf("%d",&num);
        res=countsetbit(num);
        printf("Number of set bits=%d",res);
}
```
## 10.Find whether the number is odd or even
```c
#include<stdio.h>
void evenorodd(int n){
        if(n&1)
                printf("Odd Number");
        else
                printf("Even Number");
}
int main(){
        int num;
        printf("Enter the number:");
        scanf("%d",&num);
        evenorodd(num);
}
```
## 11.Check whether the given number is power of 2 or not.
```c
#include<stdio.h>
int ispowerof2(int n){
        if(n>0&&(n&(n-1))==0)
                printf("%d is power of 2\n",n);
        else
                printf("%d is not a power of 2\n",n);
}
int main(){
        int num;
        printf("Enter the number:");
        scanf("%d",&num);
        ispowerof2(num);
}
```
## 12.Write a program to multiply a number by 2.
```c
#include<stdio.h>
int main(){
        int num,res;
        printf("Enter the number:");
        scanf("%d",&num);
        res=num<<1;
        printf("%d after multiplied by 2 is %d",num,res);
}
```
## 13.Write a program to divide a number by 2.
```c
#include<stdio.h>
int main(){
        int num,res;
        printf("Enter the number:");
        scanf("%d",&num);
        res=num>>1;
        printf("%d after divided by 2 is %d",num,res);
}
```
## 14.Write a program to swap two numbers without using third variable.
```c
#include<stdio.h>
int main(){
        int a,b;
        printf("Enter the a and b numbers:");
        scanf("%d %d",&a,&b);
        printf("Numbers before swapping:%d %d\n",a,b);
        a=a^b;
        b=a^b;
        a=a^b;
        printf("Numbers after swapping:%d %d\n",a,b);
}
```
## 15.Write a program to swap lower and higher nibble of a number.
```c
#include<stdio.h>
int main(){
        int num;
        printf("Enter the number:");
        scanf("%d",&num);
        int swap=((num&0x0f)<<4)|((num&0xf0)>>4);
        printf("Orginal numbers:%d\n",num);
        printf("After swapping Nibbles:%d\n",swap);
}
```
## 16.Toggle a given range of bits.For example, take the number 245. The equivalent binary format is 11110101and the range is 4 to 7. So, the output should be 000001010 which is 5 in decimal.
```c
#include<stdio.h>
int main(){
        int num,r,l;
        printf("Enter the number:");
        scanf("%d",&num);
        printf("Enter the staring position:");
        scanf("%d",&l);
        printf("Enter the ending position:");
        scanf("%d",&r);
        int mask=((1<<(r-l+1))-1)<<l;
        int result=num^mask;
        printf("Original number:%d\n",num);
        printf("after toggling bit from %d to %d=%d\n",l,r,result);
}
```
## 17.Check whether the given number is power of 4 or not.
```c
#include<stdio.h>
int main(){
        int num;
        printf("Enter the number:");
        scanf("%d",&num);
        if(num>0&&((num&(num-1))==0)&&num%3==1)
                printf("number is a power of 4\n");
        else
                printf("number is not a power of 4\n");
}
```
## 18.Clear the last right side set a bit of a number.
```c
#include<stdio.h>
int main(){
    int num;
    printf("Enter the number:");
    scanf("%d",&num);
    num=num&(num-1);
    printf("After clearing of last set bit=%d",num);
}
```
## 19.Find the only odd-occurring number in an array where every other element occurs even times.
```c
#include<stdio.h>
int main(){
        int n;
        printf("Enter the size of array:");
        scanf("%d",&n);
        int arr[n],result=0;
        for(int i=0;i<n;i++){
                scanf("%d",&arr[i]);
        }
        for(int i=0;i<n;i++){
                result=result^arr[i];
        }
        printf("Odd Occurrence of element in an array:%d",result);
}
```
## 20.Reverse the bits of a number (Ex: 5 → 0101 → 1010 → 10).
```c
#include<stdio.h>
int main(){
        unsigned int num;
        unsigned int rev=0;
        int bitcount;
        printf("Enter the number:");
        scanf("%d",&num);
        printf("Enter the bit count:");
        scanf("%d",&bitcount);
        for(int i=0;i<bitcount;i++){
                int lastbit=num&1;
                rev=(rev<<1)|lastbit;
                num=num>>1;
        }
        printf("Reversed number:%u\n",rev);
}
```
## 21.Position of rightmost bit of a given number.
```c
#include<stdio.h>
int main(){ 
        int num,pos=-1,i=0;
        printf("Enter the number:");
        scanf("%d",&num);
        while(num>0){
                if((num&1)==1){
                        pos=i;
                        break;
                }
                i++;
                num=num>>1;
        }
        if(pos!=-1)
               printf("Position of rightmost set bit:%d\n",pos);
        else
                printf("rightmost set bit is not found\n");
}
```
## 22.Given two numbers, write a function to insert a number y in number x. The number y should occupy n bits in x starting at position p. Assume that number y can fit in these n bits.Suppose p=13, n=6, x=0x23173b4, y=0x2F
```c
#include<stdio.h>
unsigned displaybits(int x);
unsigned fun(unsigned x,unsigned y,int p,int n);
int main(){
     unsigned x=0x23173b4,y=0x2f,num;
     int p=13,n=6;
     num=fun(x,y,p,n);
     displaybits(num);
}
unsigned fun(unsigned x,unsigned y,int p,int n){
        int mask,num;
        mask=~(~0<<n)<<(p-n+1);
        num=(x&~mask)|(y<<(p-n+1));
        return num;
}
unsigned displaybits(int x){
        int mask;
        for(int i=31;i>=0;i--){
               mask=1<<i;
               putchar(x&mask?'1':'0');
        }
}
```
## 23.Write a program ro manipulate bits from position i to j in a number x. If i=2 and j=7 then the bits to be manipulated are 2nd, 3rd, 4h, 5th, 6th, 7th.
```c
#include<stdio.h>
unsigned displaybits(int x);
int main(){
        int num,mask;
        int i=2,j=7;
        printf("Enter the number:");
        scanf("%d",&num);
        mask=~(~0<<(j-i+1))<<i;
        num=num|mask;
        displaybits(num);
}
unsigned displaybits(int x){
        int mask;
        for(int i=31;i>=0;i--){
                mask=1<<i;
                putchar(x&mask ? '1' :'0');
        }
        printf("\n");
}
```
## 24.Write a C program that takes a 32-bit hexadecimal number, splits it into 4 bytes, performs nibble swap on the MSB, resets even bits on the 2nd MSB, swaps adjacent bits on the 2nd LSB, inverts all bits on the LSB, then reconstructs and prints the final 32-bit number in both hexadecimal and binary format.
```c
#include<stdio.h>
unsigned char binarybits(unsigned char x){
        int mask;
        for(int i=7;i>=0;i--){
                mask=1<<i;
                putchar(x&mask?'1':'0');
        }
        printf("\n");
}
unsigned char swap(unsigned char x){
        return (x&0x0f)<<4 | (x&0xf0)>>4;
}
unsigned char resetevenbits(unsigned char x){
        return x&0xAA;
}
unsigned char swapadjbits(unsigned char x){
        unsigned char even = (x&0xAA)>>1;
        unsigned char odd = (x&0x55)<<1;
        return even|odd;
}
unsigned char invertallbits(unsigned char x){
        return ~x;
}
int main(){
        unsigned int i=0x3ABC29A4;
        unsigned char b1=i>>24 & 0xff;
        unsigned char b2=i>>16 & 0xff;
        unsigned char b3=i>>8 & 0xff;
        unsigned char b4=i & 0xff;
        printf("MSB (0x%x) before:",b1);
        binarybits(b1);
        b1=swap(b1);
        printf("MSB after swapping:");
        binarybits(b1);
        printf("\n");
        printf("2nd MSB (0x%x) before:",b2);
        binarybits(b2);
        b2=resetevenbits(b2);
        printf("2nd MSB after resetting of evenbits:");
        binarybits(b2);
        printf("\n");
        printf("2nd LSB (0x%x) before:",b3);
        binarybits(b3);
        b3=swapadjbits(b3);
        printf("2nd LSB after swapping of adjacentbits:");
        binarybits(b3);
        printf("\n");
        printf("LSB (0x%x) before:",b4);
        binarybits(b4);
        b4=invertallbits(b4);
        printf("LSB after inverting all bits:");
        binarybits(b4);
        printf("\n");
}
```
## 25.Write a function that reverses the bits in an integer.
```c
#include<stdio.h>
void binarybits(int x){
        int mask;
        for(int i=31;i>=0;i--){
                mask=1<<i;
                putchar(x & mask ? '1' : '0');
        }
        printf("\n");
}
unsigned int reverse(unsigned int num){
        int rev=0;
        for(int i=0;i<32;i++){
                if(num & (1<<i)){
                        rev=rev|(1<<(31-i));
                }
        }
        return rev;
}
int main(){
        unsigned int num;
        printf("Enter the number:");
        scanf("%u",&num);
        binarybits(num);
        binarybits(reverse(num));
}
```
## 26.Write a program that inputs a binary pattern less than or equal to 32 bits and converts it to an integer.
```c
#include<stdio.h>
int main(){
        char bit;
        int num=0;
        printf("Enter the any bit pattern lessthan 32:");
        for(int i=0;i<32;i++){
                bit=getchar();
                if(bit=='0')
                        num=num<<1;
                else if(bit=='1')
                        num=(num<<1)+1;
                else
                        break;
        }
        printf("Number in Hexadecimal:%x\n",num);
        printf("Number in decimal:%d\n",num);
}
```
## 27.Swap two bits at a given position in an integer
```c
#include<stdio.h>
int binarybits(int n){
        int mask;
        for(int i=31;i>=0;i--){
                mask=1<<i;
                putchar(n&mask ? '1' : '0');
        }
        printf("\n");
}
int main(){
        int num,bit1,bit2,i,j;
        printf("Enter the number:");
        scanf("%d",&num);
        binarybits(num);
        printf("Enter the position1:");
        scanf("%d",&i);
        printf("Enter the position2:");
        scanf("%d",&j);
        bit1=num<<i;
        bit2=num<<j;
        if(bit1!=bit2){
                num=num^(1<<i);
                num=num^(1<<j);
        }
        printf("After swapping the number in binary format:");
        binarybits(num);
}
```
## 28.Swap all even and odd bits.
```c
#include<stdio.h>
int binarybits(int n){
        int mask;
        for(int i=7;i>=0;i--){
                mask=1<<i;
                putchar(n&mask ? '1' : '0');
        }
        printf("\n");
}
int main(){
        int num;
        printf("Enter the number:");
        scanf("%d",&num);
        printf("Number in Binary format:");
        binarybits(num);
        int oddbits=num&0x55;
        int evenbits=num&0xAA;
        oddbits=oddbits<<1;
        evenbits=evenbits>>1;
        num=oddbits|evenbits;
        printf("Number after swapping even and odd bits:%d\n",num);
        printf("Number after swapping in binary format");
        binarybits(num);
}
```
## 29.Write a C program that uses the bitwise operators to check if a given positive integer is divisible by both 6 and 9.
```c
#include<stdio.h>
int subtract(int a,int b){
        while(b!=0){
                int borrow = (~a) & b;
                a = a ^ b;
                b = borrow<<1;
        }
        return a;
}
int isdivisibleby9(int n){
        while(n>0){
                n=subtract(n,9);
        }
        return (n==0);
}
int main(){
        int num;
        printf("Enter the number:");
        scanf("%d",&num);
        if(((num&1)==0) && isdivisibleby9(num))
                printf("%d is divisible by 6 and 9",num);
        else
                printf("%d is not divisible by 6 and 9",num);
}
```
## 30.Implement a program that checks if a number is less than 50 without using the less than operator.
```c
#include<stdio.h>
int main(){
        int num;
        printf("Enter the number:");
        scanf("%d",&num);
        int diff;
        diff=num-50;
        if((diff>>31)&1)
                printf("%d is less than 50\n",num);
        else
                printf("%d is not less than 50\n",num);
}
```
## 31.Implement a C program to check if the given number is a palindrome in binary representation using bitwise operators.
```c
#include<stdio.h>
int main(){
        int num,flag=1;
        printf("Enter the number:");
        scanf("%d",&num);
        int msb=31;
        while(msb > 0 && ((num>>msb) & 1) == 0){
                msb--;
        }
        for(int i=0,j=msb;j>i;i++,j--){
                int rightbit=num>>i&1;
                int leftbit=num>>j&1;
                if(rightbit!=leftbit){
                        flag=0;
                        break;
                }
        }
        if(flag)
                printf("%d is palindrome",num);
        else
                printf("%d is not a Palindrome",num);
}
```
## 32.Implement a C program to reverse the bits of a given number using bitwise operators.
```c
#include<stdio.h>
int binarybits(int n){
        int mask;
        for(int i=31;i>=0;i--){
                mask=1<<i;
                putchar(n&mask ? '1' : '0');
        }
}
int reverse(int n){
        int rev=0;
        for(int i=31;i>=0;i--){
                if(n&(1<<i))
                        rev=rev|(1<<(31-i));
        }
        return rev;
}
int main(){
        int num;
        printf("Enter the number:");
        scanf("%d",&num);
        printf("%d in binary format:",num);
        binarybits(num);
        int rev=reverse(num);
        printf("\nNumber after reversing the bits:%d\n",rev);
        printf("%d in binary form :",rev);
        binarybits(rev);
        printf("\n");
}
```
## 33.Write a C program to check if the given number has alternate bits set or not using bitwise operators.
```c
#include<stdio.h>
int binarybits(int n){
        int mask;
        for(int i=7;i>=0;i--){
                mask=1<<i;
                putchar(n&mask ? '1' : '0');
        }
}
int main(){
        int num;
        printf("Enter the number:");
        scanf("%d",&num);
        printf("Number in binary form:");
        binarybits(num);
        printf("\n");
        int x=num^(num>>1);
        if(!(x&(x+1)))
                printf("%d have alternative bits set\n",num);
        else
                printf("%d donot have alternative bits set\n",num);
}
```
## 34.Implement a C program to count the number of bits needed to convert integer A to integer B using bitwise operators.
```c
#include<stdio.h>
int binarybits(int n){
        int mask;
        for(int i=7;i>=0;i--){
                mask=1<<i;
                putchar(n&mask ? '1' : '0');
        }
}
int main(){
        int num1,num2;
        int count=0;
        printf("Enter the A:");
        scanf("%d",&num1);
        printf("%d in binaryform:",num1);
        binarybits(num1);
        printf("\nEnter the B:");
        scanf("%d",&num2);
        printf("%d in binaryform:",num2);
        binarybits(num2);
        int num=num1^num2;
        while(num>0){
                if(num&1)
                        count++;
                num=num>>1;
        }
        printf("\nNumber of bits need to convert from %d to %d = %d",num1,num2,count);
}
```
## 35.Write a C program to check if the given number is a perfect square using bitwise operators.
```c
#include<stdio.h>
int perfectornot(int n){
        if(n<0)
                return 0;
        if(n==0 || n==1)
                return 1;
        int low=1,high=n/2;
        while(low <= high){
                int mid=(low+high)>>1;
                long long sq =(long long)mid*mid;
                if(sq==n)
                        return 1;
                else if(sq<n)
                        low=mid+1;
                else
                        high=mid-1;
        }
        return 0;
}
int main(){
        int num;
        printf("Enter the number:");
        scanf("%d",&num);
        if(perfectornot(num))
                printf("%d is a perfect square",num);
        else
                printf("%d is not a perfect square",num);
}
```
## 36. Implement a C program to swap the first and last bits of a given number using bitwise operators.
```c
#include<stdio.h>
int binarybits(int n){
        int mask;
        for(int i=31;i>=0;i--){
                mask=1<<i;
                putchar(n&mask ? '1' : '0');
        }
        printf("\n");
}
int swapmsbandlsb(int n){
        int lsb=n&(1<<0);
        int msb=n&(1<<31);
        if(lsb!=msb){
                n=n^(1<<0);
                n=n^(1<<31);
        }
        return n;
}
int main(){
        int num;
        printf("Enter the number:");
        scanf("%d",&num);
        printf("%d in binary form:",num);
        binarybits(num);
        int n=swapmsbandlsb(num);
        printf("%d after swapping=%d\n",num,n);
        printf("%d in binary form:",n);
        binarybits(n);
}
```
## 37.Write a C program to check if the given number is a power of 8 using bitwise operators.
```c
#include<stdio.h>
int ispowerof8(unsigned int n){
        if(n==0)
                return 0;
        if((n&(n-1))!=0)
                return 0;
        int pos=0;
        while(n>1){
                n=n>>1;
                pos++;
        }
        return (pos%3==0);
}
int main(){
        int num;
        printf("Enter the number:");
        scanf("%d",&num);
        if(ispowerof8(num))
                printf("%d is power of 8\n",num);
        else
                printf("%d is not power of 8\n",num);
}
```
## 38.Implement a C program to set all the bits at odd positions in a given number using bitwise operators.
```c
#include<stdio.h>
void binarybits(int num){
        int mask;
        for(int i=31;i>=0;i--){
                mask=1<<i;
                putchar(num&mask ? '1' : '0');
                if(i%4==0)
                        printf(" ");
        }
        printf("\n");
}
int main(){
        int num;
        printf("Enter the number:");
        scanf("%d",&num);
        printf("\nNumber in binary format:");
        binarybits(num);
        num=num | 0xAAAAAAAA;
        printf("\nNumber after setting all odd positions:");
        binarybits(num);
}
```
## 39.Write a C program to count the number of bits set to 1 in the binary representation of the sum of two numbers using bitwise operators.
```c
#include<stdio.h>
void binarybits(int num){
        int mask;
        for(int i=31;i>=0;i--){
                mask=1<<i;
                putchar(num&mask ? '1' : '0');
                if(i%4==0)
                        printf(" ");
        }
        printf("\n");
}
int main(){
        int num1,num2,sum;
        int count=0;
        printf("Enter the number 1 and number2:");
        scanf("%d %d",&num1,&num2);
        sum=num1+num2;
        printf("Sum=%d",sum);
        printf("sum in binary format:");
        binarybits(sum);
        while(sum>0){
                if(sum&1)
                        count++;
                sum=sum>>1;
        }
        printf("Number of set bits:%d",count);
}
```
## 40.Implement a C program to check if the given number is a power of 16 using bitwise operators.
```c
#include<stdio.h>
int ispowerof16(unsigned int n){
        if(n==0)
                return 0;
        if((n&(n-1))!=0)
                return 0;
        int pos=0;
        while(n>1){
                n=n>>1;
                pos++;
        }
        return (pos%4==0);
}
int main(){
        int num;
        printf("Enter the number:");
        scanf("%d",&num);
        if(ispowerof16(num))
                printf("%d is power of 16\n",num);
        else
                printf("%d is not power of 16\n",num);
}
```
## 41.Implement a C program to toggle the bits at odd positions in the binary representation of a given number using bitwise operators.
```c
#include<stdio.h>
void binarybits(int num){
        int mask;
        for(int i=31;i>=0;i--){
                mask=1<<i;
                putchar(num&mask ? '1' : '0');
                if(i%4==0)
                        printf(" ");
        }
        printf("\n");
}
int main(){
        int num;
        printf("Enter the number:");
        scanf("%d",&num);
        printf("Orinal Number in Binaryformat:");
        binarybits(num);
        num = num ^ 0xAAAAAAAA;
        printf("Number after toggling of odd positions:");
        binarybits(num);
}
```
