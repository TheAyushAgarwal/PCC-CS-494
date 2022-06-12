```python
def activity_selection(A):
    A.sort(key=lambda x:x[1])
    n=len(A)
    j=0
    res=[0]
    for i in range(1,n):
        if A[i][0]>A[j][1]:
            res.append(i)
            j=1
    print("Activities = ",res)
activities=[[1,2],[3,4],[0,6],[5,7],[8,9],[5,9]]
activity_selection(activities)

```
 
