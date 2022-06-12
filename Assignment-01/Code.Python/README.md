```python
a=[]
def sorting_array():
    for i in range(0,n-1):
        for j in range(0,n-i-1):
            if(a[j]>a[j+1]):
                temp=a[j]
                a[j]=a[j+1]
                a[j+1]=temp
def binary_search(low,high):
    flag=0
    key=int(input("\nEnter key element to be searched: "))
    while(low<=high):
        mid=(low+high)//2
        if(a[mid]==key):
            flag=1
            break
        elif(key<a[mid]):
            high=mid-1
        else:
            low=mid+1
    if(flag==1):
        print("\nElement found")
    else:
        print("\nElement not found")
n=int(input("\nHow many elements you want to enter: "))
for i in range(0,n):
    ele=int(input("\nEnter element: "))
    a.append(ele)
print("\nElements of array are:",a)
sorting_array()
print("\nSorted array is:",a)
low=0
high=n-1 
binary_search(low,high)
``` 
