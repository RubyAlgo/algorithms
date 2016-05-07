---
layout: single
title:  "Replace every element by product of previous and next"
permalink: /arrays/replace-by-prev&next/
date:   2016-04-16 14:14:36 +0000
---


## Given an array replace every element by product of previous and next
Note: first element is replaced by product of first and second and last element by product of last and second last<br/>
A[0] + A[1] + A[2] = A[4] + A[5] + A[6]<br/>
**Time-complexity: O(n)**<br/>
**Auxiliary-space: O(1)**<br/>

**Implementation**

```ruby
def modify(a)
    len=a.length
    if len<=0
        return -1
    end
    #update first element
    prev=a[0]
    a[0]*=a[1]
    for i in 1...len-1
        current=a[i]        #Keep track of current element
        a[i]=prev*a[i+1]
        prev=current        #Store current element for next iteration
    end
     #update last element
    a[len-1]*=prev
    return a
end
modify([3,6,1,7,8,2]) # => [18, 3, 42, 8, 14, 16]

```

