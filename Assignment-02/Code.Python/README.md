```python
def partition(arr,low,high):
    if(low<high):
        mid=(low+high)//2
        partition(arr,low,mid)
        partition(arr,mid+1,high)
        merge_sort(arr,low,mid,high)
def merge_sort(arr,low,mid,high):
    n1=mid-low+1
    n2=high-mid
    L=[0]*(n1)
    R=[0]*(n2)
    for i in range(0,n1):
        L[i]=arr[low+i]
    for j in range(0,n2):
        R[j]=arr[mid+1+j]
    i=j=0
    k=low
    while(i<n1 and j<n2):
        if(L[i]<=R[j]):
            arr[k]=L[i]
            i=i+1
        else:
            arr[k]=R[j]
            j=j+1
        k=k+1
    while(i<n1):
        arr[k]=L[i]
        i=i+1
        k=k+1
    while(j<n2):
        arr[k]=R[j]
        j=j+1
        k=k+1
arr=[]
n=int(input("\nHow many elements you want to enter: "))
for i in range(0,n):
    ele=int(input("\nEnter a number: "))
    arr.append(ele)
l=len(arr)
low=arr[0]
high=arr[l-1]
print("\nArray elements are:",arr)
partition(arr,0,l-1)
print("\nAfter sorting array elements are:",arr)
```
 
