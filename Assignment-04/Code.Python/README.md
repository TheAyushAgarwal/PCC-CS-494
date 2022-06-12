```python
from os import lstat


def Max(lst,index,no):
    maximum=-1
    if(index>=no-2):
        if(lst[index]>lst[index+1]):
            return lst[index]
        else:
            return lst[index+1]
    maximum=Max(lst,index+1,no)
    if lst[index]>maximum:
        return lst[index]
    else:
        return maximum

def Min(lst,index,no):
    minimum=0
    if(index>=no-2):
        if(lst[index]<lst[index+1]):
            return lst[index]
        else:
            return lst[index+1]
    minimum=Min(lst,index+1,no)
    if lst[index]<minimum:
        return lst[index]
    else:
        return minimum
lst=[]
num=int(input("\nHow many elements you want to enter: "))
for i in range(0,num):
    ele=int(input("\nEnter element: "))
    lst.append(ele)
no=len(lst)
i=0
print("\nMinimum:",Min(lst,i,no))
print("\nMaximum:",Max(lst,i,no))
```
 
