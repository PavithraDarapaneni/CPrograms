
## 1. Write a program in C to count the total number of alphabets, digits and special characters in a String.
```c
#include<stdio.h>
#include<string.h>
void counting(char s[]){
        int alph=0,digits=0,symb=0;
        for(int i=0;s[i]!='\0';i++){
                if((s[i]>='a' && s[i]<='z')||(s[i]>='A' && s[i]<='Z'))
                        alph++;
                else if(s[i]>='0' && s[i]<='9')
                        digits++;
                else
                        symb++;
        }
        printf("No of Alphabets=%d\n",alph);
        printf("No of Digits=%d\n",digits);
        printf("No of Symbols=%d\n",symb);
}
int main(){
        char str[100];
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        void (*ptr)(char [])=&counting;
        ptr(str);
}
```
 ## 2. Write a C program to check the String is Pangram or not.
```c
#include<stdio.h>
#include<string.h>
void pangram(int ptr){
        if(ptr)
                printf("string is pangram");
        else
                printf("String is not pangram");

}
int main(){
        char str[100];
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
             str[strlen(str)-1]='\0';
        for(int i=0;str[i]!='\0';i++){
                if(str[i]>='A' && str[i]<='Z')
                        str[i]=str[i]+32;
        }
        void (*ptr)(int)=&pangram;
        for(char ch='a';ch<='z';ch++){
                int found=0;
                for(int i=0;str[i]!='\0';i++){
                        if(str[i]==ch){
                                found=1;
                                break;
                        }
                }
                if(!found){
                        ptr(0);
                        return 0;
                }
        }
        ptr(1);
        return 0;
}
```
## 3. Write a C program to sort a string array in ascending order.
```c
#include<stdio.h>
#include<string.h>
void sorting(char s[]){
        int k=0;
        for(int i=0;s[i]!='\0';i++){
                if(s[i]!=' ')
                        s[k++]=s[i];
        }
        s[k]='\0';
        printf("%s\n",s);
}
int main(){
        char str[100];
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        void (*ptr)(char [])=&sorting;
        for(int i=0;str[i]!='\0';i++){
                for(int j=i+1;str[j]!='\0';j++){
                        if(str[i] > str[j]){
                                int temp=str[i];
                                str[i]=str[j];
                                str[j]=temp;
                        }
                }
        }
        printf("Sorted string:\n");
        ptr(str);
}
```
## 4. Write a program in C to find the frequency of characters.
```c
##include<stdio.h>
#include<string.h>
#include<ctype.h>
void count(char s1[],int freq[]){
                for(int i=0;s1[i]!='\0';i++){
                        if(freq[i]!=0)
                              printf("%c repeates %d times\n",s1[i],freq[i]);
        }
}
int main(){
        char str[100];
        int c;
        void (*ptr)(char [],int [])=&count;
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        for(int i=0;str[i]!='\0';i++){
                str[i]=tolower(str[i]);
        }
        int f[strlen(str)];
        for(int i=0;i<strlen(str);i++){
                f[i]=-1;
        }
        for(int i=0;str[i]!='\0';i++){
                c=1;
                if(f[i]==-1){
                for(int j=i+1;str[j]!='\0';j++){
                        if(str[i]==str[j]){
                                c++;
                                f[j]=0;
                        }
                }
                f[i]=c;
                }
        }
        ptr(str,f);
}
```
## 5.Write a program in C to extract a substring from a given string.
```c
#include<stdio.h>
#include<string.h>
void extractstring(char string[],int str,int len,int mlen){
         char word[100];
         int k=0;
         if(str>0 && str<=mlen){
                for(int i=str-1;i<str-1+len;i++){
                        word[k++]=string[i];
                }
                word[k]='\0';
                printf("%s",word);
         }
         else
                 printf("Invalid");

}
int main(){
        char s1[100];
        int start,sublength;
        fgets(s1,sizeof(s1),stdin);
        if(s1[strlen(s1)-1]=='\n')
                s1[strlen(s1)-1]='\0';
        int length=strlen(s1);
        printf("\nEnter the starting position:");
        scanf("%d",&start);
        printf("\nEnter length of the substring:");
        scanf("%d",&sublength);
        void (*ptr)(char[],int ,int,int)=&extractstring;
        ptr(s1,start,sublength,length);
}
```
## 6. Write a program in C to find the number of times a given word 'the' appears in the given String.
```c
#include<stdio.h>
#include<string.h>
void count(char str[],char aword[],char word[]){
        int count=0,k=0;
        for(int i=0; ;i++){
                if(str[i]!=' ' && str[i]!=',' && str[i]!='\0'){
                        word[k++]=str[i];
                }
                else{
                word[k]='\0';
                if(strcmp(aword,word)==0){
                        count++;
                }
                k=0;
                }
                if(str[i]=='\0')
                        break;
        }
        printf("count=%d",count);
}
int main(){
        char s1[100],aword[100],word[100];
        fgets(s1,sizeof(s1),stdin);
        if(s1[strlen(s1)-1]=='\n')
                s1[strlen(s1)-1]='\0';
        fgets(aword,sizeof(aword),stdin);
        if(aword[strlen(aword)-1]=='\n')
                aword[strlen(aword)-1]='\0';
        void (*ptr)(char [],char [],char [])=&count;
        ptr(s1,aword,word);
}
```
