---
title:  "3 way Quick Sort Algorithm"
permalink: /sorting/3way-quick-sort/
date:   2016-04-16 14:14:36 +0000

---
 
Quick sort implementation which can handle duplicates well.
 
**Algorithm**

    In 3 Way QuickSort, an array arr[l..r] is divided in 3 parts:
    * arr[l..i] elements less than pivot.
    * arr[i+1..j-1] elements equal to pivot.
    * arr[j..r] elements greater than pivot


## Implementation
{% highlight ruby %}

def quick_sort(a,lo,hi)
    if lo<hi
        temp=partition(a,lo,hi)
        l=temp[0]
        r=temp[1]
        quick_sort(a,lo,l-1)
        quick_sort(a,r+1,hi)
    end
end

def partition(a,lo,hi)
    pivot=a[lo]
    i=lo+1
    lt=lo
    gt=hi
    
    while(i<=gt)
        if a[i]< pivot
            temp=a[lt]
            a[lt]=a[i]
            a[i]=temp
            lt+=1
            i+=1
        elsif a[i]>pivot
            temp=a[i]
            a[i]=a[gt]
            a[gt]=temp
            gt-=1
        else
            i+=1
        end
    end
    return lt,gt
end
{% endhighlight %}