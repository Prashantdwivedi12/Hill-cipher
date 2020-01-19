# Hill-cipher
#include <stdio.h>
#include <stdlib.h>

int e[3][1],c[3][3],a[3][3],mes[3][1];
void getkey();
void encrypt();

int main()
{
    char msg[3];
    int i;
    printf("Enter the plain text:");
    scanf("%s",msg);
    for(i=0;i<3;i++)
    {
        mes[i][0]=msg[i]-97;
    }

    getkey();
    encrypt();


    return 0;
}

void getkey()
{
    int i,j;
    printf("Enter the Key:");
    for(i=0;i<3;i++)
    {
    for(j=0;j<3;j++)
    {
        scanf("%d",&c[i][j]);
        a[i][j]=c[i][j];
    }
    }
}

void encrypt()
{
    int i,j,k;
    for(i=0;i<3;i++)
    {
        for(j=0;j<1;j++)
        {
            for(k=0;k<3;k++)
            {
                e[i][j]=e[i][j]+a[i][k]*mes[j][k];            }
        }
    }

printf("Cipher Text :");
for(i=0;i<3;i++)
{
    printf("%c",(char)((e[i][0]%26)+97));
}
}
