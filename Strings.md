## 1. Write a program in C to input a string and print it.
```c
#include<stdio.h>
int main()
{
char str[100];
fgets(str,sizeof(str),stdin);
printf("%s",ste);
}
```
## 2. Write a program in C to find the length of a string without using library functions.
```c
#include<stdio.h>
int main()
{
char str[100];int count = 0;
fgets(str,sizeof(str),stdin);
for(int i =0; str[i] != '\0';i++)
{
count ++;
}
printf("Length of the string : %d",count);
}
```
## OR
```c
#include<string.h>
int length(char*ptr)
{
int count = 0;
while( ptr != '\0')
{
count++;
ptr++;
}
return count;
}
int main()
{
char str[100];
fgets(str,sizeof(sr),stdin);
length(str);
}
```
## OR
```c
#include<stdio.h>
int length(char ptr[])
{
while(ptr[i] != '\0')
{
i++;
}
return i;
}
int main()
{
char str[100];
fgets(str,sizeof(str),stdin);
length(str);
}
