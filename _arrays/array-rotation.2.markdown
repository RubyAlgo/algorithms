---
layout: single
title:  "Array rotation-III (Reversal Algorithm)"
permalink: /arrays/rotation-reversal-algorithm/
date:   2016-04-16 14:14:36 +0000
---


## Given an zero indexed array and positive integer d,rotate the array by d-steps to the left.

## Reversal Algorithm

**Time-complexity:O(n)**<br/>
**Auxiliary-space:O(1)**<br/>

**Implementation**

```ruby
def left_rotate_array(a,d)  #Input array "a" and rotation by "d" elemets
    n=a.length
    if n>0
        
        if d>n               # if d>n ,we take modulo n 
            d%=n
        end
        
        reverse(a,0,d-1)
        reverse(a,d,n-1)
        reverse(a,0,n-1)
    end
    return a
end


def reverse(a,first,last)   #Utility function for reversing array
    i=first
    j=last
    
    while i<j
        temp=a[i]
        a[i]=a[j]
        a[j]=temp
        i+=1
        j-=1
    end
    return a
end

```

