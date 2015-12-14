# QUICK
def partition(D,lo,hi):
    i=lo
    x=D[i]
    for j in range(lo+1,hi+1):
        if D[j]<=x:
            i=i+1
            swap=D[j]
            D[j]=D[i]
            D[i]=swap
    newswap=D[lo]
    D[lo]=D[i]
    D[i]=newswap
    return i
def quicksort(D,lo,hi):
    if lo<hi:
        p=partition(D,lo,hi)
        quicksort(D,lo,p-1)
        quicksort(D,p+1,hi)
    return D
output=''
print 'Enter input (after 100 will be cut out)'
data=raw_input()
data=map(int,(data.split()))
if len(data)>100:
   data=data[:100]
lenght=len(data)
quicksort(data,0,lenght-1)
sort=quicksort(data,0,(lenght-1))
print(' '.join(map(str, sort)))

