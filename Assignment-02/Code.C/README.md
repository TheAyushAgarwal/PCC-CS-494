```c
#include<stdio.h>
#include<conio.h>
# define max 50
void merge(int[], int, int, int);
void mergesort(int[], int, int);
int main()
{
        int arr[max], n, i;
        printf("\n Implementing MergeSort using Array :- ");
        printf("\n ==================================");
        printf("\n Enter the no. of elements to enter :- ");
        scanf("%d", &n);
        printf("\n Enter the array elements :- ");
        for(i=0; i<n; i++)
                scanf("%d", &arr[i]);
        mergesort(arr, 0, n-1);
        printf("\n The Sorted Array is :- ");
        for(i=0; i<n; i++)
                printf("%d ", arr[i]);
        getch();
        return 0;
}

void merge(int arr[], int beg, int mid, int end)
{
        int i, j, k, index, temp[max];
        i = beg;
        j = mid+1;
        index = beg;
        while(i<=mid && j<=end)
        {
                if(arr[i]<arr[j])
                {
                        temp[index] = arr[i];
                        i++;
                }
                else
                {
                        temp[index] = arr[j];
                        j++;
                }
                index++;
        }
        if(i>mid)
        {
                while(j<=end)
                {
                        temp[index] = arr[j];
                        j++;
                        index++;
                }
        }
        else
        {
                while(i<=mid)
                {
                        temp[index] = arr[j];
                        i++;
                        index++;
                }
        }
        for(k=beg; k<index; k++)
                arr[k] = temp[k];
}

void mergesort(int arr[], int beg, int end)
{
        int mid;
        if(beg<end)
        {
                mid = (beg+end)/2;
                printf("\n b = %d ; m = %d ; e = %d ", beg, mid, end);
                getch();
                mergesort(arr, beg, mid);
                mergesort(arr, mid+1, end);
                printf("\n Merge call \n b = %d ; m = %d ; e = %d ", beg, mid, end);
                getch();
                merge(arr, beg, mid, end);
        }
}
```
 
