```c
#include<stdio.h>
int start[50], end[50], n1, n, i, j;
int main()
{
        printf("\n Implementing Activity Selection using Arrays :- ");
        printf("\n =============================================");
        printf("\n Enter the total events :- ");
        scanf("%d", &n1);
        printf("\n Enter the starting times :- \n");
        for(i=0; i<n1; i++)
                scanf("%d", &start[i]);
        printf("\n Enter the ending times :- \n");
        for(j=0; j<n1; j++)
                scanf("%d", &end[j]);
        n = n1/start[0];
        activitysel(start, end, n);
        return 0;
}

void activitysel(int a[], int b[], int m)
{
        printf("\n The Selected Activities are :- ");
        i=1;
        printf("A - %d || ", i);
        for(j=1; j<n; j++)
        {
                if(a[j] >= b[i])
                {
                        printf("A - %d || ", j+1);
                        i = j;
                }
        }
}
 
