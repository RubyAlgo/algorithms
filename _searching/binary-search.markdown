---
title:  "Binary Search Algorithm"
permalink: /searching/binary-search/
date:   2016-04-16 14:14:36 +0000
tags: test

---
 

This is a test Post

**Time Complexity = O(logn)**<br>
**Precondition: List should be sorted**

## Implementation
{% highlight ruby %}

def binary_search (a,n,key)  # a is the array, n is length of array and key is the value to be found
    lo = 0
    hi= n-1
    
    while (lo<=hi)
        mid = lo+((hi-lo)/2)
        
        if a[mid] == key
            return mid
        elsif a[mid] < key
            lo=mid+1
        else
            hi=mid-1
        end
        
    end
    
    return "Value not found in array"
end
{% endhighlight %}

## Heading 2