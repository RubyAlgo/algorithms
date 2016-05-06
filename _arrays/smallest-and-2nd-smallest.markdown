---
layout: single
title:  "Smallest and second smallest in an array"
permalink: /arrays/smallest-and-2nd-smallest/
date:   2016-04-16 14:14:36 +0000
---


## Given an array of elements,Find the smallest and second smallest element.

**Time-complexity: O(n)**<br/>
**Auxiliary-space: O(1)**<br/>

**Implementation**

```ruby
def find_smallest2(a)
    len=a.length
    min= second= 1.0/0.0
    
    for i in 0...len
        if a[i]<min
          	second=min
            min=a[i]
        elsif a[i]<second 
            second=a[i]
        end
    end
        
        
    return min,second
    
end

find_smallest2([1,2,3,-1,4,5,0]) # => [-1, 0]

```

