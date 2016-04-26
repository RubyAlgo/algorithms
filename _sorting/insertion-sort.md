---
title:  "Insertion Sort Algorithm"
permalink: /sorting/insertion-sort/
date:   2016-04-16 14:14:36 +0000
tags: test

---
 

This is a test Post

# Inserion Sort implementation (stable)
> Time Complexity: O(n^2),In-place,stable
Very useful for sorting nearly sorted array, very fast and effective for small size arrays
 Worst case: Array is reverse sorted, Best case: Array is already sorted (O(n) time)

## Sub-Heading
{% highlight ruby %}

def insertion_sort(a)
    for i in 1...(a.length)
        j=i
        while j>0
            if a[j-1]>a[j]
                temp=a[j]
                a[j]=a[j-1]
                a[j-1]=temp
            else
              break
            end
            j=j-1
        end
    end
    return a
end
{% endhighlight %}

