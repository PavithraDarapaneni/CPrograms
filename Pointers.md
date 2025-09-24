
## 1. Write a program in C to input a string and print it.
```c
#include<stdio.h>
int main(){

      char str[100];
      fgets(str,sizeof(str),stdin);
      printf("%s",str);
}
```
## 2. Write a program in C to find the length of a string without using library functions.
```c
#include<stdio.h>
int main(){
        char s1[30];
        scanf("%s",s1);
        printf("string=%d",s1);
        int i=0;
        while(i!='\0'){
                count++;
                i++;
        }
        printf("length of the string:%d",count);
}
```
## 3. Write a program in C to separate individual characters from a string.
```c
#include<stdio.h>
#include<string.h>
int main(){
        char s1[100];
        fgets(s1,sizeof(s1),stdin);
        if(s1[strlen(s1)-1]=='\n')
                s1[strlen(s1)-1]='\0';
        printf("Input string:%s\n",s1);
        printf("Individual characters in the string are:\n");
        for(int i=0;s1[i]!='\0';i++){
                printf("%c\n",s1[i]);
        }
}
```
## 4. Write a program in C to print individual characters of a string in reverse order.
```c
#include<stdio.h>
#include<string.h>
int main(){
        char name[30];
        int len,temp;
        fgets(name,sizeof(name),stdin);
        if(name[strlen(name)-1]=='\n')
                name[strlen(name)-1]='\0';
        printf("string before reversing :%s\n",name);
        len=strlen(name);
        printf("string after reversing:\n");
        for(int i=len-1;i>=0;i--){
                printf("%c\n",name[i]);
        }
}
```
## 5. Write a program in C to count the total number of words in a string.
```c
#include<stdio.h>
#include<string.h>
int main(){ 
    char str[1000];
    int count=0;
    fgets(str,sizeof(str),stdin);
    if(str[strlen(str)-1]=='\n')
    str[strlen(str)-1]='\0';
    for(int i=0;str[i]!='\0';i++){
        if((i==0 && str[i]!=' ' && str[i]!=','&& str[i]!='\t')||((str[i]==' '||str[i]=='.'||
    str[i]=='\t'||str[i]==',')&&((str[i+1]!=' '&&str[i+1]!=','&&str[i+1]!='\t'&&str[i+1]!='.')))){
            count++;
        }
    }
    printf("count=%d",count);
}
```
## 6. Remove the newline character added by fgets() using strcspn().
```c
#include<stdio.h>
#include<string.h>
int main(){
        char str[100];
        fgets(str,sizeof(str),stdin);
        str[strcspn(str,"\n")]='\0';
        printf("%s",str);
}
```
## 7.Write a C Program to check if a two strings are Anagram or not.
```c
#include<stdio.h>
#include<string.h>
#include<ctype.h>
void sort(char str[]){
        for(int i=0;str[i]!='\0';i++){
                for(int j=i+1;str[j]!='\0';j++){
                        if(str[i]>str[j]){
                        char temp=str[i];
                        str[i]=str[j];
                        str[j]=temp;
                }
                }
        }
}
int main(){
        char str1[100],str2[100];
        int count=0;
        fgets(str1,sizeof(str1),stdin);
        if(str1[strlen(str1)-1]=='\n')
                str1[strlen(str1)-1]='\0';
        fgets(str2,sizeof(str2),stdin);
        if(str2[strlen(str2)-1]=='\n')
                str2[strlen(str2)-1]='\0';

        if(strlen(str1)!=strlen(str2)){
                printf("string is not a anagram");
                return 0;
        }
        for(int i=0;str1[i]!='\0';i++){
                str1[i]=tolower(str1[i]);
        }
        for(int i=0;str2[i]!='\0';i++){
                str2[i]=tolower(str2[i]);
        }
        sort(str1);
        sort(str2);
        if(strcmp(str1,str2)==0)
                printf("String is a anagram");
        else
                printf("string is not a anagram");

}
```
## 8.Write a C program to check if string is pangram or not.
```c
#include<stdio.h>
#include<string.h>
#include<ctype.h>
void pangram(char str[]){
        for(char ch='a';ch<='z';ch++){
                int found=0;
                for(int i=0;str[i]!='\0';i++){
                        if(ch==str[i]){
                              found=1;
                              break;
                        }
                }
                if(found==0){
                        printf("Not a Pangram");
                        return ;
                }
        }
        printf("Pangram");
}
int main(){
        char s1[1000];
        fgets(s1,sizeof(s1),stdin);
        if(s1[strlen(s1)-1]=='\n')
                s1[strlen(s1)-1]='\0';
        for(int i=0;s1[i]!='\0';i++){
                s1[i]=tolower(s1[i]);
        }
        pangram(s1);
}
```
## 9. Write a program to reverse a string using recursion.
```c
#include<stdio.h>
#include<string.h>
void reverse(char str[],int start,int end){
        if(start>=end)
                return;
        char temp;
        temp=str[start];
        str[start]=str[end];
        str[end]=temp;
        reverse(str,start+1,end-1);
}
int main(){
        char str[100];
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        int length=strlen(str);
        reverse(str,0,length-1);
        printf("\n%s",str);
}
```
## 10.Write a C program to print sum of numbers in a string.
```c
#include<stdio.h>
int main(){
        char str[]="Hello123bg43";
        int sum=0;
        for(int i=0;str[i]!='\0';i++){
                if(str[i]>='0'&&str[i]<='9'){
                        sum=sum+str[i]-'0';
                }
        }
        printf("Sum of the digits=%d",sum);
}
```
## 11.Write a C program to count number of vowels in a string.
```c
#include<stdio.h>
int main(){
        char str[100];
        int count=0;
        fgets(str,sizeof(str),stdin);
        for(int i=0;str[i]!='\0';i++){
                if(str[i]=='a' || str[i]=='e' || str[i]=='i' || str[i]=='o' || str[i]=='u'){
                        count++;
                }
        }
        printf("Number of vowels in a string=%d",count);
}
```
## 12.Write a C program to find substring in a given string.
```c
#include<stdio.h>
#include<string.h>
int main(){
    char str[1000],Aword[100];
    int found=0;
    fgets(str,sizeof(str),stdin);
    if(str[strlen(str)-1]=='\n')
       str[strlen(str)-1]='\0';
    fgets(Aword,sizeof(Aword),stdin);
    if(Aword[strlen(Aword)-1]=='\n')
       Aword[strlen(Aword)-1]='\0';
    int len1=strlen(str);
    int len2=strlen(Aword);
    for(int i=0;i<=len1-len2;i++){
        int j;
        for(j=0;j<len2;j++){
            if(str[i+j]!=Aword[j])
                break;
        }
        if(j==len2){
                found=1;
                break;
        }
    }
    if(found)
        printf("substring is found");
    else
        printf("substring is not found");
    
}
```
## 13.Write a function to reverse a string.
```c
#include<stdio.h>
#include<string.h>
char* reverse(char str1[]){
    int len=strlen(str1);
    for(int i=0,j=len;i<j;i++,j--){
        int temp=str1[i];
        str1[i]=str1[j];
        str1[j]=temp;
    }
    return str1;
}
int main(){
    char str[100];
    fgets(str,sizeof(str),stdin);
    if(str[strlen(str)-1]=='\n')
       str[strlen(str)-1]='\0';
    reverse(str);
    printf("%s",str);
}
```
## 14. Write a program in C to find the maximum number of characters in a string.
```c
#include<stdio.h>
#include<string.h>
int main(){
    char str[100];
    int count=0;
    int len,freq;
    char maxcharacter;
    fgets(str,sizeof(str),stdin);
    if(str[strlen(str)-1]=='\n')
        str[strlen(str)-1]='\0';
    len=strlen(str);
    int fre[len];
    for(int i=0;i<len;i++){
        fre[i]=-1;
    }
    for(int i=0;i<len;i++){
        if(fre[i]==-1){
            count=0;
            for(int j=0;j<len;j++){
                if(str[i]==str[j]){
                    fre[j]=0;
                    count++;
                }
            }
            fre[i]=count;
        }
    }
    freq=fre[0];
    maxcharacter=str[0];
    for(int i=0;i<len;i++){
        if(fre[i]>freq){
            freq=fre[i];
            maxcharacter=str[i];
        }
    }
    printf("character %c repeates %d times",maxcharacter,freq);
}
```
## 15.Write a program in C to extract a substring from a given string.
```c
#include<stdio.h>
#include<string.h>
int main(){
    char str1[1000],word[100];
    int k=0,a,len;
    fgets(str1,sizeof(str1),stdin);
    if(str1[strlen(str1)-1]=='\n')
        str1[strlen(str1)-1]='\0';
    printf("Enter the position the starting position(1-based index):");
    scanf("%d",&a);
    printf("Enter the length of the string:");
    scanf("%d",&len);
    for(int i=a-1;i<a-1+len&&str1[i]!='\0';i++){
        word[k++]=str1[i];
    }
    word[k]='\0';
    printf("%s",word);
}
```
## 16.Write a program in C to find the number of times a given word 'the' appears in the given string.
```c
#include<stdio.h>
#include<string.h>
#include<ctype.h>
int main(){
    char str[1000],word[100];
    int count=0,k=0;
    fgets(str,sizeof(str),stdin);
    if(str[strlen(str)-1]=='\n')
        str[strlen(str)-1]='\0';
    for(int i=0;str[i]!='\0';i++){
        str[i]=tolower(str[i]);
    }
    for(int i=0; ;i++){
        if(str[i]!=' '&&str[i]!='\0')
           word[k++]=str[i];
        else{
        word[k]='\0';
        if(strcmp(word,"the")==0)
            count++;
        k=0;
        }
        if(str[i]=='\0')
          break;
    }
    printf("the repeats %d times",count);
}
```
## 17.Write a program in C to read a sentence and replace lowercase characters with uppercase and vice versa.
```c
#include<stdio.h>
#include<string.h>
int main(){
    char str[1000];
    fgets(str,sizeof(str),stdin);
    if(str[strlen(str)-1]=='\n')
        str[strlen(str)-1]='\0';
    for(int i=0;str[i]!='\0';i++){
        if(str[i]>='a'&&str[i]<='z')
            str[i]=str[i]-32;
        else if(str[i]>='A'&&str[i]<='Z')
            str[i]=str[i]+32;
    }
    printf("%s",str);
    
}
```
## 18.Write a program in C to remove characters from a string except alphabets.
```c
#include<stdio.h>
#include<string.h>
int main(){
    char str[1000],word[100];
    int k=0;
    fgets(str,sizeof(str),stdin);
    if(str[strlen(str)-1]=='\n')
        str[strlen(str)-1]='\0';
    for(int i=0;str[i]!='\0';i++){
        if((str[i]>='a'&&str[i]<='z')||(str[i]>='A'&&str[i]<='Z'))
             word[k++]=str[i];
    }
    word[k]='\0';
    printf("%s",word);
}
```
## 19.Write a program in C to find the largest and smallest words in a string.
```c
#include<stdio.h>
#include<string.h>
int main(){
    char str[1000],word[100],largest[100],smallest[100];
    int k=0,maxlen=0,minlen=1000;
    fgets(str,sizeof(str),stdin);
    if(str[strlen(str)-1]=='\n')
        str[strlen(str)-1]='\0';
    for(int i=0; ;i++){
        if((str[i]!=' '&&str[i]!='\0'))
             word[k++]=str[i];
        else{     
           word[k]='\0';
           if(strlen(word)>maxlen){
              maxlen=strlen(word);
              strcpy(largest,word);
           }
           if(strlen(word)<minlen&&strlen(word)>0){
               minlen=strlen(word);
               strcpy(smallest,word);
           }
           k=0;
        }
        if(str[i]=='\0')
              break;
    }
    printf("Largest string=%s\n",largest);
    printf("Smallest string=%s\n",smallest);
}
```
## 20.Write a program in C to combine two strings manually.
```c
#include<stdio.h>
#include<string.h>
int main(){
    char str1[1000],str2[1000];
    int len1,len2,k=0;
    printf("Enter the 1st string:");
    fgets(str1,sizeof(str1),stdin);
    if(str1[strlen(str1)-1]=='\n')
        str1[strlen(str1)-1]='\0';
    printf("\n");
    printf("Enter the 2nd string:");
    fgets(str2,sizeof(str2),stdin);
    if(str2[strlen(str2)-1]=='\n')
        str2[strlen(str2)-1]='\0';
    len1=strlen(str1);
    len2=strlen(str2);
    char string[len1+len2];
    for(int i=0;str1[i]!='\0';i++){
        string[k++]=str1[i];
    }
    for(int i=0;str2[i]!='\0';i++){
        string[k++]=str2[i];
    }
    string[k]='\0';
    printf("%s",string);
  
}
```
## 21.Write a C program to reverse each word in a sentence while keeping spaces, commas, and full stop in their original positions.
```c
#include<stdio.h>
#include<string.h>
int main(){
        char str[1000],word[100];
        printf("Enter the string:");
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        int len1=strlen(str);
        int k=0,len2;
        for(int i=0; ;i++){
                if(str[i]!=' '&&str[i]!=','&&str[i]!='.'&&str[i]!='\0')
                        word[k++]=str[i];
                else{
                    word[k]='\0';
                    for(int i=0,j=k-1;i<j;i++,j--){
                        int temp=word[i];
                        word[i]=word[j];
                        word[j]=temp;
                    }
                    printf("%s",word);
                    if(str[i]!='\0')
                            printf("%c",str[i]);
                    k=0;
                   }
                if(str[i]=='\0')
                        break;
        }
}
```
## 22. Write a C program to read a sentence and split it into words using spaces. Do not use strtok. Use pointer manipulation.
```c
#include<stdio.h>
#include<string.h>
int main(){
        char str[100],word[100];
        int k=0;
        char *ptr;
        printf("Enter the string:");
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        for(ptr=str; ;ptr++){
                if(*ptr!=' ' && *ptr!='.' && *ptr!=',' && *ptr!='\0')
                        word[k++]=*ptr;
                else{
                    word[k]='\0';
                    if(k>0)
                         printf("%s\n",word);
                    k=0;
                }
                if(*ptr=='\0')
                        break;
        }
}
```
## 25.Replace vowels with nxt character in a string.
```c
#include<stdio.h>
#include<string.h>
int main(){
        char str[100];
        printf("Enter the string:");
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        for(int i=0;str[i]!='\0';i++){
                if(str[i]=='a'||str[i]=='e'||str[i]=='i'||str[i]=='o'||str[i]=='u'||str[i]=='A'||str[i]=='I'||str[i]=='O'||str[i]=='U'||str[i]=='E')
                        str[i]=str[i]+1;
        }
        printf("%s",str);
}
```
## 26.Find the length of the last word.
```c
#include<stdio.h>
#include<string.h>
int main(){
        char str[1000],word[100];
        int k=0;
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        int len=strlen(str),i;
        for(i=len-1;i>=0&&str[i]==' ';i--);
        for(;i>=0&&str[i]!=' ';i--){
                        word[k++]=str[i];
        }
        word[k]='\0';
        printf("%d",strlen(word));
}
```
## 27.Write a C program to read an integer target, an array of n integers, and print all indices where the array element equals target.
```c
#include<stdio.h>
int main(){
        int arr[]={1,3,4,6,5,67,9};
        int num,len;
        len=sizeof(arr)/sizeof(arr[0]);
        printf("Enter the number:");
        scanf("%d",&num);
        for(int i=0;i<len;i++){
                if(arr[i]==num){
                        printf("Index value=%d",i);
                }
        }
}
```
## 28.Write a C program to find and print all adjacent pairs in an array whose sum is equal to a given number k.
```c
#include<stdio.h>
int main(){
        int arr[]={1,2,3,4,5};
        int sum=0,k=3;
        for(int i=0;i<4;i++){
                sum=arr[i]+arr[i+1];
                if(sum==3){
                        printf("%d %d",arr[i],arr[i+1]);
                }
        }
}
```
## 29.Write a C program to check whether a given number is a Happy Number or not.
```c
#include<stdio.h>
int main(){
        int num,rem;
        printf("Enter the number:");
        scanf("%d",&num);
        while(num>9){
                int sum=0;
                while(num>0){
                        rem=num%10;
                        sum=sum+rem*rem;
                        num=num/10;
                }
                num=sum;
        }
        if(num==1)
                printf("Happy");
        else
                printf("Not Happy");
}
```
## 30.Write a C program to check whether the parentheses in a given expression are balanced or not.
```c
#include<stdio.h>
#include<string.h>
int main(){
        char exps[100];
        int top=-1;
        printf("Enter the expression:");
        fgets(exps,sizeof(exps),stdin);
        if(exps[strlen(exps)-1]=='\n')
                exps[strlen(exps)-1]='\0';
        for(int i=0;exps[i]!='\0';i++){
                if(exps[i]=='('){
                        top++;
                }
                else if(exps[i]==')'){
                        if(top==-1){
                                printf("Not Balanced");
                                return 0;
                        }
                        else
                                top--;
                }
        }
        if(top==-1)
                printf("Balanced");
        else
                printf("Not balanced");
}
```
## 31.Write a program in C to compare two strings without using string library functions.
```c
#include<stdio.h>
#include<string.h>
int comp(char *ptr1,char *ptr2){
        while(*ptr1!='\0'&&*ptr2!='\0'&&*ptr1==*ptr2){
                ptr1++;
                ptr2++;
        }
        if(*ptr1==*ptr2)
                return 0;
        else
                return(*ptr1-*ptr2);
}
int main(){
        char str1[100],str2[100];
        int c;
        printf("Enter the string1:");
        fgets(str1,sizeof(str1),stdin);
        if(str1[strlen(str1)-1]=='\n')
                str1[strlen(str1)-1]='\0';
        printf("Enter the string2:");
        fgets(str2,sizeof(str2),stdin);
        if(str2[strlen(str2)-1]=='\n')
                str2[strlen(str2)-1]='\0';
        c=comp(str1,str2);
        if(!c)
                printf("Two strings are equal");
        else
                printf("Two strings are not equal");
}
```
## 32.Write a program in C to check whether a character is a Hexadecimal Digit or not.
```c
#include<stdio.h>
#include<string.h>
int main(){
        char ch;
        scanf("%c",&ch);
        if((ch>='0'&&ch<='9')||(ch>='a'&&ch<='f')||(ch>='A'&&ch<='F'))
                printf("character is hexadecimal");
        else
                printf("Character is not hexadecimal");
}
```
## 33.Write a program in C to replace the spaces in a string with a specific character.
```c
#include<stdio.h>
#include<string.h>
int main(){
        char str[100];
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        for(int i=0;str[i]!='\0';i++){
              if(str[i]==' ')
                   str[i]='!';
         }
        printf("%s",str);
}
```
## 34.Write a program in C to check whether a letter is uppercase or not.
```c
#include<stdio.h>
int main(){
        char ch;
        scanf("%c",&ch);
        if(ch>='A'&&ch<='Z')
                printf("upper case");
        else
                printf("Not a upper case");
}
```
## 35. Write a program in C to count the number of punctuation characters present in a string.
```c
#include<stdio.h>
#include<string.h>
int main(){
        char str[100];
        int count=0;
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        for(int i=0;str[i]!='\0';i++){
                if(str[i] == '.' || str[i] == ',' || str[i] == ';' || str[i] == ':' ||
            str[i] == '!' || str[i] == '?' || str[i] == '\'' || str[i] == '\"' ||
            str[i] == '-' || str[i] == '(' || str[i] == ')' || str[i] == '[' ||
            str[i] == ']' || str[i] == '{' || str[i] == '}' || str[i] == '/' ||
            str[i] == '@' || str[i] == '#' || str[i] == '&') {
                        count++;
                }
        }
        printf("No of punctuaction marks=%d",count);
}
```
## 35. Write a C program to find the repeated character in a string.
```c
#include<stdio.h>
#include<string.h>
int main(){
        char str[100];
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        int len=strlen(str);
        int freq[len];
        for(int i=0;i<len;i++){
                freq[i]=-1;
        }
        for(int i=0;str[i]!='\0';i++){
                if(freq[i]==-1){
                        int count=1;
                        for(int j=i+1;str[j]!='\0';j++){
                                if(str[i]==str[j]){
                                        count++;
                                        freq[j]=0;
                                }
                        }
                        freq[i]=count;
                }
        }
        printf("Repeated characters are:");
        for(int i=0;i<len;i++){
                if(freq[i]>1&&freq[i]!='\0'){
                        printf("%c ",str[i]);
                }
        }
}
```
## 36.Write a C program to find the length of the longest substring of a given string without repeating characters.
```c
#include<stdio.h>
#include<string.h>
#include<limits.h>
int main(){
    char str[100],longest[100];
    int maxlen=INT_MIN;
    printf("Enter the string:");
    fgets(str,sizeof(str),stdin);
    if(str[strlen(str)-1]=='\n')
    str[strlen(str)-1]='\0';
    int n=strlen(str);
    for(int i=0;i<n;i++){
        int count=0;
        char current[100]="";
        int visited[256]={0};
        for(int j=i;j<n;j++){
            if(visited[(unsigned char)str[j]]){
                break;
            }
            visited[(unsigned char)str[j]]=1;
            current[count++]=str[j];
        }
        current[count]='\0';
        if(count>maxlen){
            maxlen=count;
            strcpy(longest,current);
        }
    }
    printf("String=%s \t length=%d",longest,maxlen);
}
```
## 36.Write a program in C to read a file and remove the spaces between two words of its content.
```c
#include<stdio.h>
int main(){
        FILE *fp=fopen("file.txt","r");
        if(fp==NULL){
                printf("File is not found");
                return 1;
        }
        char c;
        while((c=fgetc(fp))!=EOF){
                if(c!=' ')
                        putchar(c);
        }
        fclose(fp);
}
```
## 37.A given string contains the bracket characters '(', ')', '{', '}', '<', ‘>', '[' and ']', Write a Cprogram to check if the string is valid or not. The input string will be valid when open brackets and closed brackets are the same type of brackets.
```c
#include<stdio.h>
#include<string.h>
int main(){
        char str[100];
        char stack[100];
        int top=-1;
        int valid=1;
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        for(int i=0;str[i]!='\0';i++){
                char c=str[i];
                if(c=='('||c=='{'||c=='['||c=='<')
                        stack[++top]=c;
                else if(c==')'||c=='}'||c==']'||c=='>'){
                        if(top==-1){
                                valid=0;
                                break;
                        }
                        char open=stack[top--];
                        if((c==')'&&open!='(')||
                           (c=='}'&&open!='{')||
                           (c==']'&&open!='[')||
                           (c=='>'&&open!='<')){
                                valid=0;
                                break;
                        }
                }
        }
        if(top!=-1)
                valid=0;
        printf(valid?"Valid\n":"Invalid\n");
}
```
## 38.Write a function for performing case insensitive string comparison.
```c
#include<stdio.h>
#include<string.h>
#include<ctype.h>
int strcasecmp(const char *s1,const char *s2){
        while(*s1&&*s2){
                char c1=tolower((unsigned char)*s1);
                char c2=tolower((unsigned char)*s2);
                if(c1!=c2){
                        return c1-c2;
                }
                *s1++;
                *s2++;
        }
        return (unsigned char)*s1-(unsigned char)*s2;
}
int main(){
        char s1[100],s2[100];
        printf("Enter the string1:");
        fgets(s1,sizeof(s1),stdin);
        if(s1[strlen(s1)-1]=='\n')
                s1[strlen(s1)-1]='\0';
        printf("Enter the string2:");
        fgets(s2,sizeof(s2),stdin);
        if(s2[strlen(s2)-1]=='\n')
                s2[strlen(s2)-1]='\0';
        int result=strcasecmp(s1,s2);
        if(result==0)
                printf("Strings are same");
        else
                printf("Strings are not same");
}
```
## 39.Write a program to accept a line of text and display the number of consonants and spaces in that line of text.
```c
#include<stdio.h>
#include<string.h>
int main(){
        char str[100];
        int spaces=0,consonants=0;
        printf("Enter the string:");
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        for(int i=0;str[i]!='\0';i++){
                char c=str[i];
                if(c==' '){
                        spaces++;
                }
                else if(c!='a'&&c!='e'&&c!='i'&&c!='o'&&c!='u'&&c!='A'&&c!='E'&&c!='I'&&c!='O'&&c!='U'){
                        consonants++;
                }
        }
        printf("Consonants=%d\nSpaces=%d",consonants,spaces);
}
```
## 40.Write a C program to check whether a string is palindrome or not.
```c
#include<stdio.h>
#include<string.h>
int main(){
        char str1[100],str2[100];
        printf("Enter the string:");
        fgets(str1,sizeof(str1),stdin);
        if(str1[strlen(str1)-1]=='\n')
                str1[strlen(str1)-1]='\0';
        int len=strlen(str1);
        for(int i=0;str1[i]!='\0';i++){
                if(str1[i]>='A'&&str1[i]<='Z'){
                        str1[i]=str1[i]+32;
                }
        }
        strcpy(str2,str1);
        for(int i=0,j=len-1;i<j;i++,j--){
                char temp=str1[i];
                str1[i]=str1[j];
                str1[j]=temp;
        }
        if(strcmp(str1,str2)==0)
                        printf("Palindrome");
        else
                printf("Not a palindrome");
}
```
## 41.Write a C program to reverse order of words in a given string.
```c
include<stdio.h>
#include<string.h>
#include<ctype.h>
int main(){
    char str[100],word[100][100];
    int k=0,j=0;
    printf("Enter the string1:");
    fgets(str,sizeof(str),stdin);
    if(str[strlen(str)-1]=='\n')
    str[strlen(str)-1]='\0';
    int len=strlen(str);
    for(int i=0;i<len;i++){
        if(str[i]!=' '){
            word[k][j++]=str[i];
        }
        else{
            word[k][j]='\0';
            k++;
            j=0;
        }
    }
    word[k][j]='\0';
    k++;
    for(int i=k-1;i>=0;i--){
        printf("%s",word[i]);
        if(i>0){
            printf(" ");
        }
    }
}
```
## 42.Write a C program to find the first occurrence of a character in a given string.
```c
#include<stdio.h>
#include<string.h>
int main(){
        char str[100],ch;
        printf("Enter the string:");
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        printf("Enter the character:");
        scanf("%c",&ch);
        int pos=1,found=0;
        for(int i=0;str[i]!='\0';i++){
                if(ch==str[i]){
                        found=1;
                        break;
                }
                pos++;
        }
        if(found)
                printf("First occurrence of %c at position %d",ch,pos);
        else
                printf("character is not found");

}
```
## 43. Write a C program to find the last occurrence of a character in a given string.
```c
#include<stdio.h>
#include<string.h>
int main(){
        char str[100],ch;
        int lastpos=-1;
        printf("Enter the string:");
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        printf("Enter the character:");
        scanf("%c",&ch);
        for(int i=0;str[i]!='\0';i++){
                if(str[i]==ch){
                        lastpos=i+1;
                }
        }
        if(lastpos!=-1)
                printf("Last occurrence of %c is at position %d",ch,lastpos);
        else
                printf("Character is not found");
}
```
## 44.Write a C program to search all occurrences of a character in a given string.
```c
#include<stdio.h>
#include<string.h>
int main(){
        char str[100],ch;
        int found=0;
        printf("Enter the string:");
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        printf("Enter the character:");
        scanf("%c",&ch);
        for(int i=0;str[i]!='\0';i++){
                if(str[i]==ch){
                        printf("%c occurs at %d position\n",ch,i+1);
                        found=1;
                }
        }
        if(!found)
                printf("character is not found");
}
```
## 45.Write a C program to count occurrences of a character in a given string.
```c
#include<stdio.h>
#include<string.h>
int main(){
        char str[100],ch;
        int count=0,found=0;
        printf("Enter the string:");
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        printf("Enter the character:");
        scanf("%c",&ch);
        for(int i=0;str[i]!='\0';i++){
                if(str[i]==ch){
                        count++;
                }
        }
        if(count>0)
                printf("Number of occurrences=%d",count);
        else
                printf("charcter is not found");
}
```
## 46.Write a C program to find the highest frequency character in a string.
```c
#include<stdio.h>
#include<string.h>
int main(){
        char str[100];
        int count=1;
        printf("Enter the string:");
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        int len=strlen(str);
        int freq[len];
        for(int i=0;i<len;i++){
                freq[i]=-1;
        }
        for(int i=0;str[i]!='\0';i++){
                if(freq[i]==-1){
                        count=1;
                        for(int j=i+1;str[j]!='\0';j++){
                                if(str[i]==str[j]){
                                        count++;
                                        freq[j]=0;
                                }
                        }
                        freq[i]=count;
                }
        }
        int max=0;
        char maxchar=str[0];
        for(int i=0;i<len;i++){
                if(freq[i]>max){
                        max=freq[i];
                        maxchar=str[i];
                }
        }
        printf("Highest freq character=%c",maxchar);
}
```
## 47.Write a C program to find the lowest frequency character in a string.
```c
#include<stdio.h>
#include<string.h>
int main(){
        char str[100];
        int count=1;
        printf("Enter the string:");
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        int len=strlen(str);
        int freq[len];
        for(int i=0;i<len;i++){
                freq[i]=-1;
        }
        for(int i=0;str[i]!='\0';i++){
                if(freq[i]==-1){
                        count=1;
                        for(int j=i+1;str[j]!='\0';j++){
                                if(str[i]==str[j]){
                                        count++;
                                        freq[j]=0;
                                }
                        }
                        freq[i]=count;
                }
        }
        int min=999;
        char minchar;
        for(int i=0;i<len;i++){
                if(freq[i]!=0&&freq[i]<min){
                        min=freq[i];
                        minchar=str[i];
                }
        }
        printf("Lowest freq character=%c",minchar);
}
```
## 48.Write a C program to count the frequency of each character in a string.
```c
#include<stdio.h>
#include<string.h>
int main(){
        char str[100];
        int count=1;
        printf("Enter the string:");
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        int len=strlen(str);
        int freq[len];
        for(int i=0;i<len;i++){
                freq[i]=-1;
        }
        for(int i=0;str[i]!='\0';i++){
                if(freq[i]==-1){
                        count=1;
                        for(int j=i+1;str[j]!='\0';j++){
                                if(str[i]==str[j]){
                                        count++;
                                        freq[j]=0;
                                }
                        }
                        freq[i]=count;
                }
        }
        for(int i=0;i<len;i++){
                if(freq[i]>0){
                        printf("%c repeates %d times\n",str[i],freq[i]);
                }
        }
}
```
## 49.Write a C program to remove the first occurrence of a character from a string.
```c
#include<stdio.h>
#include<string.h>
int main(){
        char str[100],ch;
        int found=0;
        printf("Enter the string:");
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        printf("Enter the character:");
        scanf("%c",&ch);
        int len=strlen(str);
        for(int i=0;str[i]!='\0';i++){
                if(str[i]==ch && !found){
                        found=1;
                }
                if(found && i<len-1){
                        str[i]=str[i+1];
                }
        }
        if(found){
                str[len-1]='\0';
                printf("string after removal=%s",str);
        }
        else
                printf("character is not found");
}
```
## 50.Write a C program to remove the last occurrence of a character from a string.
```c
#include<stdio.h>
#include<string.h>
int main(){
        char str[100],ch;
        int found=0,lastpos;
        printf("Enter the string:");
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        printf("Enter the character:");
        scanf("%c",&ch);
        int len=strlen(str);
        for(int i=0;str[i]!='\0';i++){
                if(str[i]==ch ){
                        lastpos=i;
                        found=1;
                }
        }
        for(int i=lastpos;str[i]!='\0';i++){
                str[i]=str[i+1];
        }
        if(found){
                str[len-1]='\0';
                printf("string after removal=%s",str);
        }
        else
                printf("character not found");
}
```
## 51.Write a C program to remove all occurrences of a character from a string.
```c
#include<stdio.h>
#include<string.h>
int main(){
        char str[100],ch,str2[100];
        int j=0;
        printf("Enter the string:");
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        printf("Enter the character:");
        scanf("%c",&ch);
        for(int i=0;str[i]!='\0';i++){
                if(str[i]!=ch){
                        str2[j++]=str[i];
                }
        }
        str2[j]='\0';
        printf("%s",str2);
}
```
## 52.Write a C program to remove all repeated characters from a given string.
```c
#include<stdio.h>
#include<string.h>
int main(){
        char str[100],result[100];
        int k=0,found=0;
        printf("Enter the string:");
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        for(int i=0;str[i]!='\0';i++){
                found=0;
                for(int j=0;j<k;j++){
                        if(str[i]==result[j]){
                                found=1;
                                break;
                        }
                }
                if(!found){
                        result[k++]=str[i];
                }
        }
        result[k]='\0';
        printf("string after removing repeated character=%s\n",result);
}
```
## 53.Write a C program to replace the first occurrence of a character with another in a string.
```c
#include<stdio.h>
#include<string.h>
int main(){
        char str[100],ch,rep;
        int found=0;
        printf("Enter the string:");
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        printf("Enter the character:");
        scanf("%c",&ch);
        printf("Enter replacement character:");
        scanf(" %c",&rep);
        for(int i=0;str[i]!='\0';i++){
                if(str[i]==ch){
                        str[i]=rep;
                        found=1;
                        break;
                }
        }
        if(found)
                printf("%s\n",str);
        else
                printf("character is not found");
}
```
## 54.Write a C program to replace the last occurrence of a character with another in a string.
```c
#include<stdio.h>
#include<string.h>
int main(){
        char str[100],ch,rep;
        int lastpos,found=0;
        printf("Enter the string:");
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        printf("Enter the character:");
        scanf("%c",&ch);
        printf("Enter replacement character:");
        scanf(" %c",&rep);
        for(int i=0;str[i]!='\0';i++){
                if(str[i]==ch){
                        lastpos=i;
                        found=1;
                }
        }
        if(found){
                str[lastpos]=rep;
                printf("%s\n",str);
        }
        else
                printf("character is not found");
}
```
## 55.Write a C program to replace all occurrences of a character with another in a string.
```c
#include<stdio.h>
#include<string.h>
int main(){
        char str[100],ch,rep;
        int found=0;
        printf("Enter the string:");
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        printf("Enter the character:");
        scanf("%c",&ch);
        printf("Enter replacement character:");
        scanf(" %c",&rep);
        for(int i=0;str[i]!='\0';i++){
                if(str[i]==ch){
                        str[i]=rep;
                        found=1;
                }
        }
        if(found)
                printf("%s\n",str);
        else
                printf("character is not found");
}
```
## 56.Write a C program to trim leading white space characters from a given string.
```c
#include<stdio.h>
#include<string.h>
#include<ctype.h>
int main(){
        char str[100];
        int i=0,j=0;
        printf("Enter the string:");
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        while(isspace(str[i])){
                i++;
        }
        while(str[i]!='\0'){
                str[j++]=str[i++];
        }
        printf("%s",str);
}
```
## 57.Write a C program to trim trailing white space characters from a given string.
```c
#include<stdio.h>
#include<string.h>
int main(){
        char str[100];
        printf("Enter the string:");
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        for(int i=strlen(str)-1;i>=0;i--){
                if(str[i]==' '||str[i]=='\t'){
                        str[i]='\0';
                }
                else{
                        break;
                }
        }
        printf("%s",str);
}
```
## 58.Write a C program to trim both leading and trailing white space characters from given string.
```c
#include<stdio.h>
#include<string.h>
#include<ctype.h>
int main(){
        char str[100];
        int i=0,j=0;
        printf("Enter the string:");
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        while(isspace(str[i])){
                i++;
        }
        while(str[i]!='\0'){
                str[j++]=str[i++];
        }
        str[j]='\0';
        for(int i=strlen(str)-1;i>=0;i--){
                if(str[i]==' '||str[i]=='\t')
                        str[i]='\0';
                else
                        break;
        }
        printf("%s",str);
}
```
## 59.Write a C program to remove all extra blank spaces from given string.
```c
#include<stdio.h>
#include<string.h>
#include<ctype.h>
int main(){
        char str[100],result[100];
        printf("Enter the string:");
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        int i=0;
        int j=0;
        while(isspace(str[i])){
                i++;
        }
        int spacebar=0;
        while(str[i]!='\0'){
                if(isspace(str[i])){
                        if(!spacebar){
                                result[j++]=' ';
                                spacebar=1;
                        }
                }
                else{
                        result[j++]=str[i];
                        spacebar=0;
                }
                i++;
        }
        if(j>0 && result[j-1]==' ')
                j--;
        result[j]='\0';
        printf("String after removing of trailing spaces:%s",result);
}
```
## 60.Write a recursive function to reverse a string using bitwise operator’s.
```c
#include<stdio.h>
#include<string.h>
void reverse(char str[],int left,int right){
        if(left>=right)
                return;
        str[left]=str[left]^str[right];
        str[right]=str[left]^str[right];
        str[left]=str[left]^str[right];

        return reverse(str,left+1,right-1);
}
int main(){
        char str[100];
        printf("Enter the string:");
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        reverse(str,0,strlen(str)-1);
        printf("string after reversing:%s\n",str);
}
```
## 61.Unlike gets (), the function fgets() doesn't delete the newline character entered at the end but retains it. What should we do if we don't want the newline character in the string.
```c
#include<stdio.h>
#include<string.h>
int main(){
        char str[100];
        printf("Enter the string:");
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        printf("String after removal of new line at end:%s\n",str);
}
```
## 62.Write a function to remove all leading and trailing blanks from a string.
```c
#include<stdio.h>
#include<string.h>
#include<ctype.h>
char removespaces(char str[],char result[100]){
        int i=0,j=0;
        while(isspace(str[i])){
                i++;
        }
        int spaceflag=0;
        while(str[i]!='\0'){
                if(isspace(str[i])){
                        if(!spaceflag){
                                result[j++]=' ';
                                spaceflag=1;
                        }
                }
                else{
                        result[j++]=str[i];
                }
                i++;
        }
        if(j>0 && result[j-1]==' '){
                j--;
        }
        result[j]='\0';
}
int main(){
        char str[100],result[100];
        printf("Enter the string:");
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        removespaces(str,result);
        printf("String after removing of trailing spaces:%s",result);
}
```
## 63.Input a string and change it so that the characters are placed in alphabetical order. For example the string "Devanshi"should be changed to "aDehinsv".
```c
#include<stdio.h>
#include<string.h>
#include<ctype.h>
int main(){
        char str[100];
        printf("Enter the string:");
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        for(int i=0;str[i]!='\0';i++){
                for(int j=i+1;str[j]!='\0';j++){
                        if(tolower(str[i])>tolower(str[j])){
                                char temp=str[i];
                                str[i]=str[j];
                                str[j]=temp;
                        }
                }
        }
        printf("%s\n",str);
}
```
## 64.Write a program to abbreviate input text. For example if the input is "World Health Organization", then the output should be WHO.
```c
#include<stdio.h>
#include<string.h>
int main(){
        char str[100],result[100];
        int j=0;
        printf("enter the string:");
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        if((str[0]>='A'&&str[0]<='Z')||(str[0]>='a'&&str[0]<='z')){
                if(str[0]>='a'&&str[0]<='z')
                        result[j++]=str[0]-32;
                else
                        result[j++]=str[0];
        }
        for(int i=0;str[i]!='\0';i++){
                if(str[i-1]==' ' &&((str[i]>='a'&&str[i]<='z')||(str[i]>='A'&&str[i]<='Z'))){
                                if(str[i]>='a'&&str[i]<='z')
                                      result[j++]=str[i]-32;
                                else
                                      result[j++]=str[i];
                }
        }
        result[j]='\0';
        printf("%s\n",result);
}
```
## 65. Write a function to replace adjacent multiple spaces in a string by a single space. 
```c
#include<stdio.h>
#include<string.h>
#include<ctype.h>
int main(){
        char str[100],result[100];
        int i=0,j=0;
        printf("Enter the string:");
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        int spaceflag;
        while(isspace(str[i])){
                i++;
        }
        spaceflag=0;
        while(str[i]!='\0'){
                if(isspace(str[i])){
                        if(!spaceflag){
                                result[j++]=' ';
                                spaceflag=1;
                        }
                }
                else{
                        result[j++]=str[i];
                        spaceflag=0;
                }
                i++;
        }
        if(j>0 && result[j-1]==' ')
                j--;
        result[j]='\0';
        printf("String after removing the extra spaces:%s",result);
}
```
## 66.Write a program to find the number of occurrences of a particular word in a string.
```c
#include<stdio.h>
#include<string.h>
#include<ctype.h>
int main(){
        char str[100],word[20],pword[20];
        int count=0,k=0;
        printf("Enter the string:");
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        printf("Enter the word:");
        fgets(pword,sizeof(pword),stdin);
        if(pword[strlen(pword)-1]=='\n')
                pword[strlen(pword)-1]='\0';
        for(int i=0;str[i]!='\0';i++){
                str[i]=tolower(str[i]);
        }
        for(int i=0;pword[i]!='\0';i++){
                pword[i]=tolower(pword[i]);
        }
        for(int i=0; ;i++){
                if(str[i]!=' '&&str[i]!='\0')
                        word[k++]=str[i];
                else{
                        word[k]='\0';
                        if(strcmp(word,pword)==0)
                               count++;
                        k=0;
                }
                if(str[i]=='\0')
                        break;
        }
        printf("Total occurences of given word:%d",count);
}
```
## 67.Write a program to replace all occurrences of the word "Bangalore" by "Bengaluru" in a string.
```c
#include<stdio.h>
#include<string.h>
int main(){
        char str[100],word[20],result[100];
        int k=0;
        printf("Enter the string:");
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        for(int i=0; ;i++){
                if(str[i]!=' '&&str[i]!='\0')
                        word[k++]=str[i];
                else{
                        word[k]='\0';
                        if(strcmp(word,"Bangalore")==0)
                              strcat(result,"Bengaluru");
                        else
                                strcat(result,word);
                        k=0;
                }
                if(str[i]==' ')
                        strcat(result," ");
                if(str[i]=='\0')
                        break;
        }

        printf("%s",result);
}
```
## 67.Write your own pointer versions of the library functions strncpy() , strncmp (), strncat ().
## strncpy():
```c
#include<stdio.h>
#include<string.h>
char* mystrcpy(char *src,char *dest,int n){
        char *temp=dest;
        while(n>0 && *src!='\0'){
                *dest++=*src++;
                n--;
        }
        while(n>0){
                *dest++='\0';
                n--;
        }
        return temp;
}
int main(){
        char str1[100],str2[100];
        printf("Enter the string1:");
        fgets(str1,sizeof(str1),stdin);
        if(str1[strlen(str1)-1]=='\n')
                str1[strlen(str1)-1]='\0';
        mystrcpy(str1,str2,5);
        printf("String after copy:%s",str2);
}
```
## strncmp():
```c
int mystrcmp(char *s1,char *s2,int n){
        while(n>0 && *s1 && (*s1==*s2)){
                s1++;
                s2++;
                n--;
        }
        if(n==0)
                return 0;
        return (unsigned char)*s1 - (unsigned char)*s2;
}
int main(){
        char str1[100],str2[100],str[100];
        printf("Enter the string1:");
        fgets(str1,sizeof(str1),stdin);
        if(str1[strlen(str1)-1]=='\n')
                str1[strlen(str1)-1]='\0';
        printf("Enter the string2:");
        fgets(str2,sizeof(str2),stdin);
        if(str2[strlen(str2)-1]=='\n')
                str2[strlen(str2)-1]='\0';
        if(!mystrcmp(str1,str2,3))
                printf("strings are equal");
        else
                printf("strings are not equal");
}
```
## strncat():
```c
char* mystrcat(char *s1,char *s2,int n){
        char *temp=s1;
        while(*s1!='\0')
                s1++;
        while(n-- > 0 && *s2!='\0')
                *s1++=*s2++;
        *s1='\0';
        return temp;
}
int main(){
        char str1[100],str2[100];
        printf("Enter the string1:");
        fgets(str1,sizeof(str1),stdin);
        if(str1[strlen(str1)-1]=='\n')
                str1[strlen(str1)-1]='\0';
        printf("Enter the string2:");
        fgets(str2,sizeof(str2),stdin);
        if(str2[strlen(str2)-1]=='\n')
                str2[strlen(str2)-1]='\0';
        mystrcat(str1,str2,5);
        printf("String after concatination:%s",str1);
}
```
## 68.Write a function find_indexF () which takes two strings as arguments and returns the index of the first occurrence of the second string in the first string. Write a similar function find_indexF() that returns the index of the last occurrence of the second string in the first string.
```c
#include<stdio.h>
#include<string.h>
int str_start(char *s,char *subs,int n){
        return(strncmp(s,subs,n)==0);
}
int str_end(char *s,char *subs){
        int len1=strlen(s);
        int len2=strlen(subs);
        return(strncmp(s+len1-len2,subs,len2)==0);
}
int main(){
        char str[100],substr[100];
        printf("Enter the string:");
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        printf("Enter the sunstring:");
        fgets(substr,sizeof(substr),stdin);
        if(substr[strlen(substr)-1]=='\n')
                substr[strlen(substr)-1]='\0';
        int len=strlen(substr);
        /*if(str_start(str,substr,len-1))
                printf("Present\n");
        else
                printf("Not present\n");*/
        if(str_end(str,substr))
                printf("present\n");
        else
                printf("Not present\n");

}
```
## 69.Write a recursive function to reverse a string.
```c
#include<stdio.h>
#include<string.h>
int reverse(char *s){
        if(*s=='\0')
                return -1;
        reverse(s+1);
        printf("%c",*s);
}
int main(){
        char str[100];
        printf("Enter the string:");
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        reverse(str);
        printf("\n");
}
```
## 70. Write a recursive function to return the index of the first occurrence of a character in a string.
```c
#include<stdio.h>
#include<string.h>
int focc(char *s,char ch,int i){
        if(*s=='\0')
                return -1;
        if(*s==ch)
                return i;
        focc(s+1,ch,i+1);
}

int main(){
        char str[100],ch;
        printf("Enter the string:");
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        printf("Enter the character:");
        scanf("%c",&ch);
        printf("First Occurrence=%d",focc(str,ch,0));
        printf("\n");
}
```
## 71.Write a recursive function to return the index of the last occurrence of a character in a string.
```c
#include<stdio.h>
#include<string.h>
int locc(char *s,char ch,int i){
        if(*s=='\0')
                return -1;
        if(*s==ch)
                return i;
        locc(s+1,ch,i-1);
}

int main(){
        char str[100],ch;
        int len;
        printf("Enter the string:");
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        len=strlen(str);
        printf("Enter the character:");
        scanf("%c",&ch);
        printf("First Occurrence=%d",locc(str,ch,len-1));
        printf("\n");
}
```
## 72.Write a recursive function to find whether a string is palindrome or not. A palindrome is a string that is read the same way forward and backward for example "radar", "hannah", "madam".
```c
#include<stdio.h>
#include<string.h>
int palindrome(char *s,int f,int l){
        if(l<f)
                return 1;
        if(s[f]==s[l])
                palindrome(s,f+1,l-1);
        else
                return 0;
}

int main(){
        char str[100];
        printf("Enter the string:");
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        int len=strlen(str);
        if(palindrome(str,0,len-1))
                printf("palindrome");
        else
                printf("Not a palindrome");
}
```
## 73.Write a function stratr_r() which takes two strings as arguments and returns a pointer to the beginning of the last occurrence of the second string in the first string.
```c
#include<stdio.h>
#include<string.h>
char* stratr_r(char *s,char *sstr){
        char *lastoccurrence=NULL;
        char *current;
        if(*sstr=='\0')
                return (char*)s;
        current=strstr(s,sstr);
        while(current!=NULL){
                lastoccurrence=current;
                current=strstr(current+1,sstr);
        }
        return lastoccurrence;
}
int main(){
        char str[100],substr[20];
        printf("Enter the string:");
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        printf("Enter the substring:");
        fgets(substr,sizeof(substr),stdin);
        if(substr[strlen(substr)-1]=='\n')
                substr[strlen(substr)-1]='\0';
        char *result=stratr_r(str,substr);
        if(result!=NULL)
                printf("Last Occurrence found at:%s",result);
        else
                printf("Substring not found");
}
```
## 74.Write a function find_indexF () which takes two strings as arguments and returns the index of the first occurrence of the second string in the first string. Write a similar function find_indexF() that returns the index of the last occurrence of the second string in the first string.
```c
#include<stdio.h>
#include<string.h>
int find_index(char *s,char *sstr){
        char *pos=strstr(s,sstr);
        if(pos==NULL)
                return -1;
        return (int)(pos-s);
}
int find_last(char *s,char *sstr){
        char *pos=strstr(s,sstr);
        char *last=NULL;
        while(pos!=NULL){
                last=pos;
                pos=strstr(pos+1,sstr);
        }
        if(last==NULL)
                return -1;
        return (int)(last-s);
}
int main(){
        char str[100],substr[100];
        printf("Enter the string:");
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        printf("Enter the substring:");
        fgets(substr,sizeof(substr),stdin);
        if(substr[strlen(substr)-1]=='\n')
                substr[strlen(substr)-1]='\0';
        int res1=find_index(str,substr);
        int res2=find_last(str,substr);
        printf("First Occurence of substring:%d\n",res1);
        printf("Last occurrence of substring:%d\n",res2);
}
```
## 75.Write a program to input two strings and remove all the common characters from both the strings. Display the resultant strings.
```c
#include<stdio.h>
#include<string.h>
int ispresent(char str[],char ch){
        for(int i=0;str[i]!='\0';i++){
                if(str[i]==ch)
                        return 1;
        }
        return 0;
}
int main(){
        char str1[100],str2[100],res1[100],res2[100];
        printf("Enter the string1:");
        fgets(str1,sizeof(str1),stdin);
        if(str1[strlen(str1)-1]=='\n')
                str1[strlen(str1)-1]='\0';
        printf("Enter the string2:");
        fgets(str2,sizeof(str2),stdin);
        if(str2[strlen(str2)-1]=='\n')
                str2[strlen(str2)-1]='\0';
        int j=0;
        for(int i=0;str2[i]!='\0';i++){
                if(!ispresent(str1,str2[i]))
                        res2[j++]=str2[i];
        }
        res2[j]='\0';
        int k=0;
        for(int i=0;str1[i]!='\0';i++){
                if(!ispresent(str2,str1[i]))
                        res1[k++]=str1[i];
        }
        res1[k]='\0';
        printf("String1 after removal of common characters:%s\n",res1);
        printf("string2 after removal of common characters:%s\n",res2);
}
```
## 76.Write a recursive function to count the number of vowels in a string.
```c
#include<stdio.h>
#include<string.h>
int vowels(char *s,int c){
        if(*s=='\0')
                return c;
        if(*s=='a'||*s=='e'||*s=='i'||*s=='o'||*s=='u'||*s=='A'||*s=='E'||*s=='I'||*s=='O'||*s=='U')
                c++;
        return vowels(s+1,c);
}
int main(){
        char str[100];
        printf("Enter the string:");
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        int count=vowels(str,0);
        printf("No of vowels:%d",count);
}
```
## 75. Write a recursive function to replace each occurrence of a character by another character in a string.
```c
#include<stdio.h>
#include<string.h>
char* replace(char *s,char c){
        if(*s=='\0')
                return s;
        if(*s==c)
                *s='s';
        replace(s+1,c);
        return s;
}

int main(){
        char str[100],ch;
        printf("Enter the string:");
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        printf("Enter the character:");
        scanf("%c",&ch);
        char *res=replace(str,ch);
        printf("%s\n",res);
}
```
## 76.Write a recursive function to convert a string of numbers to an integer.
```c
#include<stdio.h>
#include<string.h>
int strtoint(char str[],int n){
        if(n==1)
                return str[0]-'0';
        int smallans = strtoint(str,n-1);
        int lastdigit = str[n-1]-'0';
        return smallans*10+lastdigit;
}
int main(){
        char str[100],res;
        printf("Enter the string:");
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        int len=strlen(str);
        res=strtoint(str,len);
        printf("Converted integer: %d\n",res);
}
```
## 77.Write a C program to multiply two positive numbers as strings. Return a string representation of the product.
```c
#include<stdio.h>
#include<string.h>
int strtoint(char str[],int n){
        int digit,res=0;
        for(int i=0;i<n;i++){
                digit=str[i]-'0';
                res=res*10+digit;
        }
        return res;
}

int main(){
        char str1[100],str2[100];
        int res1,res2,result;
        printf("Enter the string1:");
        fgets(str1,sizeof(str1),stdin);
        if(str1[strlen(str1)-1]=='\n')
                str1[strlen(str1)-1]='\0';
        printf("Enter the string2:");
        fgets(str2,sizeof(str2),stdin);
        if(str2[strlen(str2)-1]=='\n')
                str2[strlen(str2)-1]='\0';
        int len1=strlen(str1);
        int len2=strlen(str2);
        res1=strtoint(str1,len1);
        res2=strtoint(str2,len2);
        result=res1*res2;
        printf("Result : %d\n",result);
}
```
## 78.Write a C program to compress a string by replacing consecutive repeating characters with the character followed by their count.
```c
#include<stdio.h>
#include<string.h>
int main(){
        char str[100],res[100];
        int count=1,k=0;
        printf("Enter the string:");
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        int len=strlen(str);
        for(int i=0;i<len;i++){
                if(str[i]==str[i+1])
                        count++;
                else{
                        res[k++]=str[i];
                        if(count>1)
                                res[k++]=count+'0';
                        count=1;
                }
        }
        res[k]='\0';
        printf("%s",res);
}
```

## 78.Write a C Program given string consisting of words and spaces return the length of the last word.
```c
#include<stdio.h>
#include<string.h>
int main(){
        char str[100],res[100];
        int k=0;
        printf("Enter the string:");
        fgets(str,sizeof(str),stdin);
        str[strcspn(str,"\n")]='\0';
        int len=strlen(str);
        for(int i=len-1;i>=0;i--){
                if(str[i]==' '||str[i]=='\n')
                        str[i]='\0';
                else
                        break;
        }
        int alen=strlen(str);
        for(int i=alen-1;i>=0;i--){
                if(str[i]!=' '){
                        k++;
                }
                else
                        break;
        }
        printf("Length of the last word:%d",k);
}
```
