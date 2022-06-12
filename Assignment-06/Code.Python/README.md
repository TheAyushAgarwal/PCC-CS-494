```python
class knapsack:
    def fractional_knapsack(self,weight,values,capacity):
        res=0
        for pair in sorted(zip(weight,values),key=lambda x: -x[1]/x[0]):
            if not bool(capacity):
                break
            if(pair[0]>capacity):
                res=res+int(pair[1]/(pair[0]/capacity))
                capacity=0
            elif (pair[0]<=capacity):
                res=res+pair[1]
                capacity=capacity-pair[0]
        return int(res)

k=knapsack()
weight=[10,20,40,30]
values=[60,40,100,120]
capacity=50
print("\nWeights are:",weight)
print("\nProfit values are:",values)
print("\nSize of knapsack is:",capacity)
profit=k.fractional_knapsack(weight,values,capacity)
print("\nMaximum profit in knapsack is:",profit)
```
 
