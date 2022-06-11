```c
# include<stdio.h>
int main()
{
        int a[10], key, n, i;
        printf("\n Implementing Binary Search using Array :- ");
        printf("\n =======================================");
        printf("\n Enter the total no. of elements to enter :- ");
        scanf("%d", &n);
        printf("\n Enter the elements :- \n");
        for(i=0; i<n; i++)
                scanf("%d", &a[i]);
        printf("\n You entered :- ");
        for(i=0; i<n; i++)
                printf("%d ", a[i]);
        printf("\n Enter the element to search :- ");
        scanf("%d", &key);
        int pos = binsearch(a, key, n);
        if(pos == -1)
        {
                printf("\n Element not found!!!! ");
                return 0;
        }
        printf("\n Element found at position = %d", pos);
        return 0;
}

int binsearch(int a[], int key, int len)
{
        int low = 0, high = len-1, mid;
        while(low <= high)
        {
                mid = low + ((high - low) / 2);
                if(a[mid] == key)
                        return mid;
                if(key < a[mid])
                        high = mid - 1;
                else
                        low = mid + 1;
        }
        return -1;
}
```
 
