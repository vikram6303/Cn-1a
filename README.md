1(a).#include<stdio.h>
#include<string.h>
int main()
{
    int a[20],b[30],i,j,k,count,n;
    printf("Enter frame size (Example: 8):");
    scanf("%d",&n);
    printf("Enter the frame in the form of 0 and 1 :");
    for(i=0; i<n; i++)
        scanf("%d",&a[i]);
    i=0;
    count=1;
    j=0;
    while(i<n)
    {
        if(a[i]==1)
        {
            b[j]=a[i];
            for(k=i+1; a[k]==1 && k<n && count<5; k++)
            {
                j++;
                b[j]=a[k];
                count++;
                if(count==5)
                {
                    j++;
                 
				    b[j]=0;
                }
                i=k;
            }
        }
        else
        {
            b[j]=a[i];
        }
        i++;
        j++;
    }
    printf("After Bit Stuffing :");
    for(i=0; i<j; i++)
        printf("%d",b[i]);
    return 0;
}
1(b)
#include<stdio.h>
 #include<string.h> 
 #include<process.h>
  void main()
{
int i=0,j=0,n,pos; char a[20],b[50],ch;
printf("Enter string\n"); scanf("%s",&a); n=strlen(a);
printf("Enter position\n");
 
scanf("%d",&pos); if(pos>n)
{
printf("invalid position, Enter again :"); scanf("%d",&pos);}
printf("Enter the character\n"); ch=getche();
b[0]='d';
b[1]='l';
b[2]='e';
b[3]='s';
b[4]='t';
b[5]='x'; j=6;
while(i<n)
{
if(i==pos-1)
{
b[j]='d';
b[j+1]='l';
b[j+2]='e';
b[j+3]=ch; b[j+4]='d';
b[j+5]='l';
b[j+6]='e';
 
j=j+7;
}
if(a[i]=='d' && a[i+1]=='l' && a[i+2]=='e')
{
b[j]='d';
b[j+1]='l';
b[j+2]='e';
j=j+3;
}
b[j]=a[i]; i++;
j++;
}
b[j]='d';
b[j+1]='l';
b[j+2]='e';
b[j+3]='e';
b[j+4]='t';
b[j+5]='x';
b[j+6]='\0';
printf("\nframe after stuffing:\n"); printf("%s",b);
}
3.
#include<stdio.h> 
int main()
{
int w,i,f,frames[50]; printf("Enter window size: "); scanf("%d",&w);
printf("\nEnter number of frames to transmit: "); scanf("%d",&f);
printf("\nEnter %d frames: ",f); for(i=1;i<=f;i++)
scanf("%d",&frames[i]);
printf("\nWith sliding window protocol the frames will be sent in the following manner (assuming no corruption of frames)\n\n");
printf("After sending %d frames at each stage sender waits for acknowledgement sent by the receiver\n\n",w);
for(i=1;i<=f;i++)
{
if(i%w==0)
{
 



}
else
 
printf("%d\n",frames[i]);
printf("Acknowledgement of above frames sent is received by sender\n\n");



printf("%d ",frames[i]);
 
}
if(f%w!=0)
printf("\nAcknowledgement of above frames sent is received by sender\n"); return 0;
}
2 .
#include <stdio.h>
#include <string.h>
int main() {
    char data[50], key[50], quotient[50], remainder[50], finaldata[50];
    int datalen, keylen, i, j;
    printf("Enter data: ");      scanf("%s", data);
    printf("Enter key: ");      scanf("%s", key);
   datalen = strlen(data);
    keylen = strlen(key);
char temp[50];
  strncpy(temp, data, keylen);
    temp[keylen] = '\0';
 for (i = 0; i <= datalen - keylen; i++) {
  quotient[i] = temp[0];
   if (temp[0] == '1') {
            for (j = 0; j < keylen; j++) {
                temp[j] = (temp[j] == key[j]) ? '0' : '1';    }       }
for (j = 0; j < keylen - 1; j++)    {
            temp[j] = temp[j + 1]     }
           temp[keylen - 1] = (i + keylen < datalen) ? data[i + keylen] : '0';    }
 quotient[datalen - keylen] = '\0';
    strncpy(remainder, temp, keylen - 1);
    remainder[keylen - 1] = '\0';
  printf("Quotient is: %s\n", quotient);        printf("Remainder is: %s\n", remainder);
strcpy(finaldata, data);
    strcat(finaldata, remainder);
    printf("Final data is: %s\n", finaldata);

    return 1;
}
