```python
def quick_sort(arr,low,high):
    if(low<high):
        p=partition(arr,low,high)
        quick_sort(arr,low,p-1)
        quick_sort(arr,p+1,high)
def partition(arr,low,high):
    i=low-1
    pivot=arr[high]
    for j in range(low,high):
        if(arr[j]<=pivot):
            i=i+1
            arr[i],arr[j]=arr[j],arr[i]
    arr[i+1],arr[high]=arr[high],arr[i+1]
    return i+1
arr=[]
n=int(input("\nHow many elements you want to enter: "))
for i in range(0,n):
    ele=int(input("\nEnter a number: "))
    arr.append(ele)
n=len(arr)
print("\nArray elements are:",arr)
quick_sort(arr,0,n-1)
print("\nAfter sorting array elements are:",arr)