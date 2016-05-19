---
layout: single
title:  "Segregate and put all 0s first, then all 1s and all 2s in last"
permalink: /arrays/segregate-zeros--ones-and-twos/
date:   2016-04-16 14:14:36 +0000
---


## Given an array A[] consisting 0s, 1s and 2s, put all 0s first, then all 1s and all 2s in last.
**Brute-force: Count 0s and 1s (using 2 varibales)and rewrite array first with counted zeros then by counted 1s and then by 2s**

> Algorithm: Dutch National Flag Algorithm

**Time-complexity:O(n)**<br/>
**Auxiliary-space: O(1)**<br/>

**Implementation**

```ruby

def segregate(a)
   right=a.length-1
   left=0
   current=0
    while(current<=right)
        if a[current]==0
           swap(a,left,current)
           left+=1
           current+=1
        elsif a[current]==2
            swap(a,right,current)
            right-=1
        else
             current+=1
        end
    end
   print a
end

def swap(a,i,j)
    a[i],a[j]=a[j],a[i]
end

segregate([0, 1, 1, 0, 1, 2, 1, 2, 0, 0, 0, 1])

```

