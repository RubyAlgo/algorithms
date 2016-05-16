---
layout: single
title:  "Segregate 0s on left side and 1s on right side in given array"
permalink: /arrays/segregate-zeros-and-ones-1/
date:   2016-04-16 14:14:36 +0000
---


## Given an array of 0s and 1s in random order.Segregate 0s on left side and 1s on right side of the array.
**Brute-force: Count 0s and rewrite array first with counted zeros then by 1**

> Algorithm: Dutch National Flag Algorithm

**Time-complexity:O(n)**<br/>
**Auxiliary-space: O(1)**<br/>

**Implementation**

```ruby

def segregate(a)
   left=0
   right=a.length-1
   while left<right
        #Increment left index while we see 0 at left
        while a[left]== 0
            left+=1
        end
        #Decrement right index while we see 1 at right
        while a[right]==1
            right-=1
        end
        #Exchange arr[left] and arr[right]
        if left<right
            a[left],a[right]=a[right],a[left]
            left+=1
            right-=1
        end
   end
    return a
end
segregate([1,0,1,1,0,0]) # => [0, 0, 0, 1, 1, 1]
```

