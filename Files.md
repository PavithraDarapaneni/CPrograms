## Open file in read mode.
```c
#include<stdio.h>
void main(){
        char a[10];
        int val;
        FILE *fp;
        fp=fopen("file.txt","r");
        if(NULL==fp){
                printf("Failed to open the file");
                return;
        }
        fscanf(fp,"%s %d",a,&val);
        printf("%s %d\n",a,val);
        fclose(fp);
        return;
}
```
## Open the file in write mode.
```c
#include<stdio.h>
void main(){
        FILE *fp;
        fp=fopen("file.txt","w");
        if(fp==NULL){
                printf("failed to open the file");
                return;
        }
        char a[100]="world";
        fprintf(fp,"%s",a);
        fclose(fp);
        return;
}
```
## 1.Write a C program to read content from one file and write it to another file.
```c
#include<stdio.h>
#include<string.h>
#include<stdlib.h>
int main(){
        FILE *fp1,*fp2;
        char str[100];
        char ch;
        fp1=fopen("abc.txt","r");
        if(fp1==NULL){
                printf("Error in opening file");
                return 0;
        }
        fp2=fopen("cde.txt","w");
        if(fp2==NULL){
                printf("Error in opening file");
                return 0;
        }
        while(fgets(str,sizeof(str),fp1)!=NULL){
        fprintf(fp2,"%s",str);
        }
        fclose(fp1);
        fclose(fp2);
}

```
## 2.Create a program that reads integers from a file and calculates their sum, then writes the sum to another file.
```c
#include<stdio.h>
#include<stdlib.h>
int main(){
        FILE *fp1,*fp2;
        int num,sum=0;
        fp1=fopen("int.txt","r");
        if(fp1==NULL){
                printf("Error in opening file");
                exit(1);
        }
        while(fscanf(fp1,"%d",&num)==1){
                sum=sum+num;
        }
        fclose(fp1);
        fp2=fopen("sum.txt","w");
        if(fp2==NULL){
                printf("Error in opening file");
                exit(1);
        }
        fprintf(fp2,"%d",sum);
        fclose(fp2);
}
```
## 3. Develop a program to read a text file and count the number of words in it.
```c
#include<stdio.h>
#include<stdlib.h>
int main(){
        FILE *fp;
        char ch;
        int inword=0,count=0;
        fp=fopen("abc.txt","r");
        if(fp==NULL){
                printf("Error in opening a file");
                exit(1);
        }
        while((ch=getc(fp))!=EOF){
                if(ch==' '||ch=='\t'||ch=='\n'){
                        inword=0;
                }
                else if(inword==0){
                        inword=1;
                        count++;
                }

        }
        fclose(fp);
        printf("Total Words in file:%d\n",count);
}
```
## 4.Write a C program using file handling to compress a string by replacing consecutive repeating characters with the character followed by their count.
```c
#include<stdio.h>
#include<stdlib.h>
#include<string.h>
int main(){
        FILE *fpin,*fpout;
        char str[100],res[100];
        fpin=fopen("a.txt","w");
        if(fpin==NULL){
                printf("Error");
                exit(1);
        }
        printf("Enter the string:");
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        fprintf(fpin,"%s",str);
        int len=strlen(str);
        int count=1,k=0;
        for(int i=0;str[i]!='\0';i++){
                if(str[i]==str[i+1])
                        count++;
                else{
                        res[k++]=str[i];
                        if(count>1){
                                res[k++]=count+'0';
                        }
                        count=1;
                }
        }
        res[k]='\0';
        fpout=fopen("res.txt","w");
         if(fpout==NULL){
                printf("Error");
                exit(1);
        }
        fprintf(fpout,"%s",res);
        fclose(fpin);
        fclose(fpout);
}
```
## 5.Implement a file management system that allows users to create, read, update, and delete files using C functions.
```c
#include<stdio.h>
#include<string.h>
#include<stdlib.h>
void createfile(){
        char filename[100],str[100];
        FILE *fp;
        printf("Enter the filename:");
        scanf("%s",filename);
        fp=fopen(filename,"w");
        if(fp==NULL){
                printf("Error");
                return;
        }
        printf("File %s created successfully",filename);
        printf("\nEnter the string:");
        getchar();
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        fprintf(fp,"%s",str);
        fclose(fp);
}
void readfile(){
        char filename[100],ch;
        FILE *fp;
        printf("\nEnter the filename:");
        scanf("%s",filename);
        fp=fopen(filename,"r");
        if(fp==NULL){
                printf("Error");
                return;
        }
        printf("Contents of file:");
        while((ch=fgetc(fp))!=EOF){
                putchar(ch);
        }
        fclose(fp);
}
void appendfile(){
        char filename[100],data[100];
        FILE *fp;
        printf("\nEnter the filename:");
        scanf("%s",filename);
        fp=fopen(filename,"a");
        if(fp==NULL){
                printf("Error");
                return;
        }
        int i=0;
        printf("append the string that ends with !:");
        while((data[i]=getchar())!='!'){
                i++;
        }
        data[i]='\0';
        fprintf(fp,"%s",data);
        fclose(fp);
}
void deletefile(){
        char filename[100];
        printf("Enter the file name:");
        scanf("%s",filename);
        if(remove(filename)==0)
                printf("File removed successfully");
        else
                printf("Error in removing file");
}

int main(){
        int choice;
        printf("----File Management System------\n");
        printf("1.Create file\n");
        printf("2.Read file\n");
        printf("3.Append file\n");
        printf("4.Delete file\n");
        printf("Enter the choice:");
        scanf("%d",&choice);
        switch(choice){
                case 1 :
                        createfile();
                        break;
                case 2 :
                        readfile();
                        break;
                case 3 :
                        appendfile();
                        break;
                case 4 :
                        deletefile();
                        break;
                default :
                        printf("Invalid");
        }
}
```
## 6.Write a program that checks whether a file exists or not.
```c
#include<stdio.h>
#include<stdlib.h>
int main(){
        char filename[100];
        printf("Enter the filename:");
        scanf("%s",filename);
        FILE *fp;
        fp=fopen(filename,"r");
        if(fp==NULL){
                printf("Error in opening file");
                exit(1);
        }
        else{
                printf("File Opened successfully");
                fclose(fp);
        }
}
```
## 7.Create a C program to rename a file.
```c
#include<stdio.h>
#include<stdlib.h>
int main(){
        char newname[100];
        printf("Enter the newname of file:");
        scanf("%s",newname);
        if(rename("cde.txt",newname)==0)
                printf("File name changed successfully");
        else
                printf("Error");
}
```
## 8. Develop a C program that handles errors while opening files and prints appropriate error messages.
```c
#include<stdio.h>
#include<errno.h>
#include<string.h>
int main(){
        FILE *fp;
        fp=fopen("Cde.txt","r");
        if(fp==NULL){
                perror("File doesnot open\n");
                printf("Error:%s\n",strerror(errno));
                return 1;
        }
        printf("File opened successfully");
}
```
## 9. Write a program that reads a file line by line and prints each line along with its line number.
```c
#include<string.h>
#include<stdio.h>
#include<stdlib.h>
int main(){
        FILE *fpin,*fpout;
        char line[256];
        fpin=fopen("read.txt","r");
        if(fpin==NULL){
                printf("Error");
                exit(1);
        }
        fpout=fopen("Newfile.txt","w");
        if(fpout==NULL){
                printf("Error");
                exit(1);
        }
        int count=0;
        while((fgets(line,sizeof(line),fpin))!=NULL){
                count++;
                line[strcspn(line,"\n")]='\0';
                fprintf(fpout,"%d %s\n",count,line);
        }
        fclose(fpin);
        fclose(fpout);
}
```
## 10. Create a program to delete a specific line from a text file.
```c
#include<stdio.h>
#include<unistd.h>
#include<stdlib.h>
#include<string.h>
int main(){
        FILE *fpin,*fpout;
        int n;
        char line[100];
        printf("Enter the line number:");
        scanf("%d",&n);
        fpin=fopen("read.txt","r");
        if(fpin==NULL){
                printf("Error");
                exit(1);
        }
        fpout=fopen("ss.txt","w");
        if(fpout==NULL){
                printf("Error");
                exit(1);
        }
        int count=0;
        while(fgets(line,sizeof(line),fpin)!=NULL){
                count++;
                if(count!=n)
                        fprintf(fpout,"%s",line);
        }
        fclose(fpin);
        fclose(fpout);
}
```
## 11.Write a C program to store and retrieve student records using binary file handling.
```c
#include<stdio.h>
#include<stdlib.h>
struct student{
        char name[20];
        int id;
        float marks;
};
void addRecord(){
        struct student s;
        FILE *fp;
        fp=fopen("student.txt","ab");
        if(fp==NULL){
                printf("Error");
                exit(1);
        }
        printf("Enter the student ID:");
        scanf("%d",&s.id);
        printf("Enter the student name:");
        scanf("%s",s.name);
        printf("Enter the marks:");
        scanf("%f",&s.marks);
        fwrite(&s,sizeof(s),1,fp);
        fclose(fp);
        printf("Record added successfully");
}
void displayRecord(){
        struct student s;
        FILE *fp;
        fp=fopen("student.txt","rb");
        if(fp==NULL){
                printf("No data found");
                exit(1);
        }
        while(fread(&s,sizeof(s),1,fp)==1){
                printf("Roll No:%d\tName:%s\tMarks:%f\n",s.id,s.name,s.marks);
        }
        fclose(fp);
}
int main(){
        int choice;
        printf("1.Add Record\n");
        printf("2.Display Record\n");
        printf("3.exit\n");
        printf("Enter the choice:");
        scanf("%d",&choice);
        switch(choice){
                case 1:
                        addRecord();
                        break;
                case 2:
                        displayRecord();
                        break;
                case 3:
                        exit(1);
                        break;
                default:
                        printf("Invalid");
        }
}
```
## 12.Implement a program that copies the contents of one binary file to another.
```c
#include<stdio.h>
#include<stdlib.h>
int main(){
        FILE *fpin,*fpout;
        char ch;
        fpin=fopen("read.txt","rb");
        if(fpin==NULL){
                printf("Error");
                exit(1);
        }
        fpout=fopen("sr.txt","wb");
        if(fpout==NULL){
                printf("Error");
                exit(1);
        }
        while((ch=fgetc(fpin))!=EOF){
                fputc(ch,fpout);
        }
        fclose(fpin);
        fclose(fpout);
}
```
## 13.Develop a program that reads a binary file containing integer data and finds the maximum and minimum values.
```c
#include<stdio.h>
#include<stdlib.h>
#include<limits.h>
int main(){
        FILE *fp;
        int num,min=INT_MAX,max=INT_MIN;
        fp=fopen("read.txt","r");
        if(fp==NULL){
                printf("Error");
                exit(1);
        }
        while(fread(&num,sizeof(num),1,fp)==1){
                if(num>max)
                        max=num;
                if(num<min)
                        min=num;
        }
        fclose(fp);
        if(min==INT_MAX && max==INT_MIN)
                printf("File is empty or not contain integers");
        else{
                printf("Maximum element: %d\n",max);
                printf("Minimum element: %d\n",min);
        }
}
```
## 14.Create a program to open a file and move the file pointer to the end of the file and determine the file size.
```c
#include<stdio.h>
#include<stdlib.h>
int main(){
        FILE *fp;
        int size;
        fp=fopen("read.txt","r");
        if(fp==NULL){
                printf("error");
                exit(1);
        }
        fseek(fp,0,SEEK_END);
        size=ftell(fp);
        printf("Size of file:%d\n",size);
        fclose(fp);
}
```
## 15.Write a C program to read the last n lines of a text file.
```c
#include<stdio.h>
#include<stdlib.h>
int main(){
        FILE *fp;
        int pos,n,count=0;
        char ch;
        fp=fopen("read.txt","r");
        if(fp==NULL){
                printf("error");
                exit(1);
        }
        fseek(fp,0,SEEK_END);
        pos=ftell(fp);
        printf("Enter number of lines:");
        scanf("%d",&n);
        while(pos>0 && count<=n){
                fseek(fp,--pos,SEEK_SET);
                ch=fgetc(fp);
                if(ch=='\n')
                        count++;
        }
        while((ch=fgetc(fp))!=EOF){
                putchar(ch);
        }
        fclose(fp);
}
```
## 16.Implement a program to search for a specific string in a text file and print its line number.
```c
#include<stdlib.h>
#include<string.h>
int main(){
        FILE *fp;
        char str[256],word[100];
        int count=0,found=0;
        printf("Enter the specifice word :");
        fgets(word,sizeof(word),stdin);
        if(word[strlen(word)-1]=='\n')
                word[strlen(word)-1]='\0';
        fp=fopen("read.txt","r");
        if(fp==NULL){
                printf("error");
                exit(1);
        }
        while(fgets(str,sizeof(str),fp)!=NULL){
                count++;
                if((strstr(str,word)!=NULL)){
                        printf("%s found at %d line\n",word,count);
                        found=1;
                }
        }
        if(!found)
                printf("String not present");
        fclose(fp);
}
```
## 17.Develop a C program that appends data to an existing text file.
```c
#include<stdio.h>
#include<stdlib.h>
#include<string.h>
int main(){
        FILE *fp;
        fp=fopen("read.txt","a");
        if(fp==NULL){
                printf("Error");
                exit(1);
        }
        char str[100];
        printf("Enter the string to append:");
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        fprintf(fp,"\n%s",str);
        fclose(fp);
}
```
## 18.Write a program that appends the current date and time to a log file each time it is run.
```c
#include<stdio.h>
#include<stdlib.h>
#include<time.h>
int main(){
        FILE *fp;
        time_t currenttime;
        char timestr[100];
        fp=fopen("log.txt","a");
        if(fp==NULL){
                printf("error");
                exit(1);
        }
        currenttime=time(NULL);
        struct tm *local=localtime(&currenttime);
        strftime(timestr,sizeof(timestr),"%y-%m-%d %H %M %S",local);
        fprintf(fp,"Program run at %s\n",timestr);
        fclose(fp);
}
```
## 19.Create a program that allows users to input text and appends it to a file until they enter "exit".
```c
#include<stdio.h>
#include<string.h>
#include<stdlib.h>
int main(){
        FILE *fp;
        char str[100];
        fp=fopen("read.txt","a");
        if(fp==NULL){
                printf("error");
                exit(1);
        }
        while(1){
        printf("Enter the string(type exit you want to exit):");
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        if(strcmp(str,"exit")==0){
                break;
        }
        fprintf(fp,"%s\n",str);
        }
        fclose(fp);
        printf("All input has been saved to read.txt\n");
}
```
## 20.Write a C program to merge the words alternately from both files.
```c
#include<stdio.h>
#include<stdlib.h>
int main(){
        FILE *fp,*fp1,*fp2;
        char str1[100],str2[100];
        fp1=fopen("file1.txt","r");
        if(fp==NULL){
                printf("Error");
                exit(1);
        }
        fp2=fopen("file2.txt","r");
        if(fp2==NULL){
                printf("Error");
                exit(1);
        }
        fp=fopen("file.txt","w");
        while(fscanf(fp1,"%s",str1)==1 && fscanf(fp2,"%s",str2)==1){
                fprintf(fp,"%s %s ",str1,str2);
        }
        fclose(fp1);
        fclose(fp2);
        fclose(fp);
}
```
## 21. Develop a program that compresses a text file using simple compression techniques (e.g.,run-length encoding) and saves the compressed data to another file.
```c
#include<stdio.h>
#include<string.h>
int main(){
        FILE *fp1,*fp2;
        char str[100];
        int count=1;
        fp1=fopen("file.txt","r");
        fp2=fopen("Compress.txt","w");
        if(fp1==NULL || fp2==NULL){
                printf("Error in opening file");
                return 1;
        }
        fscanf(fp1,"%s",str);
        fclose(fp1);
        for(int i=0;str[i]!='\0';i++){
                if(str[i]==str[i+1]){
                        count++;
                }
                else{
                        fprintf(fp2,"%c",str[i]);
                        if(count>=1)
                              fprintf(fp2,"%d",count);
                        count=1;
                }
        }
        fclose(fp2);
}
```
## 22.Write a program that decompresses a compressed file and restores the original text.
```c
#include<stdio.h>
#include<string.h>
#include<ctype.h>
int main(){
        FILE *fp1,*fp2;
        char str[100],res[1000];
        int k=0;
        char prevchar;
        fp1=fopen("Compress.txt","r");
        fp2=fopen("original.txt","w");
        if(fp1==NULL || fp2==NULL){
                printf("Error in opening file");
                return 1;
        }
        fgets(str,100,fp1);
        for(int i=0;str[i]!='\0';i++){
                if(isalpha(str[i])){
                                prevchar=str[i];
                                res[k++]=str[i];
                }
                else if(isdigit(str[i])){
                      int num=0;
                      while(isdigit(str[i])){
                        num = num*10 + (str[i]-'0');
                        i++;
                      }
                      i--;
                      for(int j=0;j<num;j++){
                        res[k++]=prevchar;
                      }
                }
        }
        res[k]='\0';
        fprintf(fp2,"%s",res);
        printf("%s",res);
        fclose(fp1);
        fclose(fp2);
}
```

## 23.Implement a C program that reads data from a CSV (comma-separated values) file, parses it,and performs specific operations (e.g., calculate average, find maximum/minimum).
```c
#include<stdio.h>
#include<limits.h>
int main(){
        FILE *fp;
        int i;
        fp=fopen("csv.txt","r");
        if(fp==NULL){
                printf("Error");
                return 1;
        }
        float sum=0;
        int count=0;
        int min=INT_MAX;
        int max=INT_MIN;
        while(fscanf(fp,"%d,",&i)==1){
                if(i>max){
                        max=i;
                }
                if(i<min){
                        min=i;
                }
                sum=sum+i;
                count++;
        }
        printf("Average=%.2f\n",sum/count);
        printf("maximum=%d\n",max);
        printf("Minimum=%d\n",min);
}
```

## 24.Write a program in C to create and store information in a text file.
```c
#include<stdio.h>
#include<string.h>
int main(){
        char str[100];
        int id;
        float Marks;
        FILE *fp;
        fp=fopen("textfile.txt","w");
        if(fp==NULL){
                printf("Error");
                return 1;
        }
        printf("Enter the Name:");
        fgets(str,sizeof(str),stdin);
        str[strcspn(str,"\n")]='\0';
        fprintf(fp,"Name : %s\n",str);
        printf("Enter the Number:");
        scanf("%d",&id);
        fprintf(fp,"Id : %d\n",id);
        printf("Enter the marks:");
        scanf("%f",&Marks);
        fprintf(fp,"Marks : %f\n",Marks);

}
```

## 25. Write a program in C to read an existing file.
```c
#include<stdio.h>
#include<string.h>
int main(){
        char str[100];
        FILE *fp;
        fp=fopen("textfile.txt","r");
        if(fp==NULL){
                printf("Error");
                return 1;
        }
        /*while((ch=fgetc(fp))!=EOF){
                printf("%c",ch);
        }*/
        while(fgets(str,sizeof(str),fp)!=NULL){
                printf("%s",str);
        }
        fclose(fp);
}
```

## 26.rite a program in C to write multiple lines to a text file.
```c
#include<stdio.h>
#include<string.h>
int main(){
        char str[100];
        int n;
        FILE *fp;
        fp=fopen("textfile.txt","w");
        if(fp==NULL){
                printf("Error");
                return 1;
        }
        printf("Enter the number of lines:");
        scanf("%d",&n);
        getchar();
        for(int i=0;i<n;i++){
                fgets(str,sizeof(str),stdin);
                str[strcspn(str,"\n")]='\0';
                fprintf(fp,"%s\n",str);
        }
        fclose(fp);
        printf("Data written Successfully\n");
}
```

## 27..Write a program in C to read the file and store the lines in an array.
```c
#include<stdio.h>
#include<string.h>
int main(){
        char arr[100][200];
        int count=0;
        FILE *fp;
        fp=fopen("textfile.txt","r");
        if(fp==NULL){
                printf("Error");
                return 1;
        }
        while(fgets(arr[count],sizeof(arr[count]),fp) != NULL){
                arr[count][strcspn(arr[count],"\n")]='\0';
                count++;
        }
        fclose(fp);
        printf("File has %d lines :\n",count);
        for(int i=0;i<count;i++){
                printf("%s\n",arr[i]);
        }
}
```

## 28.Write a program in C to find the number of lines in a text file.
```c
#include<stdio.h>
int main(){
        FILE *fp;
        char str[100];
        int count=0;
        fp=fopen("textfile.txt","r");
        if(fp==NULL){
                printf("Error");
                return 1;
        }
        while(fgets(str,sizeof(str),fp)!=NULL){
                count++;
        }
        fclose(fp);
        printf("Number of lines in text file :%d\n",count);
}
```

## 29.Write a program in C to count the number of words and characters in a file.
```c
#include<stdio.h>
int main(){
        FILE *fp;
        char str[100];
        char ch;
        fp=fopen("textfile.txt","r");
        if(fp==NULL){
                printf("Error");
                return 1;
        }
        int wordc=0,charc=0;
        while(fscanf(fp,"%s",str)==1){
                wordc++;
        }
        rewind(fp);
        while((ch=getc(fp))!=EOF){
                charc++;
        }
        fclose(fp);
        printf("Number of words:%d\n",wordc);
        printf("Number of characters:%d\n",charc);
}
```

## 30. Write a program in C to delete a specific line from a file.
```c
#include<stdio.h>
int main(){
        FILE *fp1,*fp2;
        char c;
        int line,count=1;
        fp1=fopen("textfile.txt","r");
        if(fp1==NULL){
                printf("Error");
                return 1;
        }
        fp2=fopen("filee.txt","w");
        if(fp2==NULL){
                printf("Error");
                return 1;
        }
        printf("Enter the line number to delete:");
        scanf("%d",&line);
        c=getc(fp1);
        while(c!=EOF){
                if(c=='\n')
                        count++;
                if(count != line)
                        putc(c,fp2);
                c=getc(fp1);
        }
        fclose(fp1);
        fclose(fp2);
        printf("Line %d deleted successfully.\n",line);
}
```

## 31.Write a program in C to replace a specific line with another text in a file.
```c
#include<stdio.h>
int main(){
        FILE *fp1,*fp2;
        char str[]="The sun rises in the east";
        char c;
        int line,count=1;
        fp1=fopen("textfile.txt","r");
        if(fp1==NULL){
                printf("Error");
                return 1;
        }
        fp2=fopen("filee.txt","w");
        if(fp2==NULL){
                printf("Error");
                return 1;
        }
        printf("Enter the line number to replace:");
        scanf("%d",&line);
        c=getc(fp1);
        while(c!=EOF){
                if(count==line){
                        fprintf(fp2,"%s\n",str);
                        while(c != '\n' && c != EOF)
                                c=getc(fp1);
                        if(c != EOF)
                                c=getc(fp1);
                        count++;
                }
                if(c!=EOF){
                     putc(c,fp2);
                     if(c=='\n')
                             count++;
                     c=getc(fp1);
               }
        }
        fclose(fp1);
        fclose(fp2);
}
```
