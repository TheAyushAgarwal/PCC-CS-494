```c
#include<stdio.h>
int max, min, a[100];
int main()
{
        int i, num;
        printf("\n Implementing MAX and MIN using Array :- ");
        printf("\n ======================================");
        printf("\n Enter the total no.of elements :- ");
        scanf("%d", &num);
        printf("\n Enter the elements :- ");
        for(i=1; i<=num; i++)
                scanf("%d", &a[i]);
        max = a[0];
        min = a[0];
        maxmin(1, num);
        printf("\n The Maximum element in the array is :- %d", max);
        printf("\n The Minimum element in the array is :- %d", min);
        return 0;
}

int maxmin(int i, int j)
{
        int max1, min1, mid;
        if(i == j)
                max = min = a[i];
        else if(i == j-1)
        {
                if(a[i] < a[j])
                {
                        max = a[j];
                        min = a[i];
                }
                else
                {
                        max = a[i];
                        min = a[j];
                }
        }
        else
        {
                mid = (i + j)/2;
                maxmin(i, mid);
                max1 = max;
                min1 = min;
                maxmin(mid+1, j);
                if(max < max1)
                        max = max1;
                if(min > min1)
                        min = min1;
        }
}
```
