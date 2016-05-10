---
layout: single
title:  "Array rotation-II (Juggling Algorithm)"
permalink: /arrays/rotation-juggling-algorithm/
date:   2016-04-16 14:14:36 +0000
---


## Given an zero indexed array and positive integer d,rotate the array by d-steps to the left.

## Juggling Algorithm

**Time-complexity:O(n)**<br/>
**Auxiliary-space:O(1)**<br/>

**Implementation**

```ruby
def left_rotate_array(a, d) #Input array "a" and rotation by "d" elemets
    n=a.length
    if n>0 
        if d>n              # if d>n ,we take modulo n 
            d%=n
        end
        
        for i in 0...gcd(d,n)
            temp=a[i]
            j=i
            while(true)
             k=j+d
             if k>=n
                 k=k-n
             end
             if k==i
                 break
             end
             a[j]=a[k]
             j=k
            end
            a[j]=temp
        end
            
    end
  return a    
end


def gcd(x,y)
    if y==0
        return x
    else
      return gcd(y,x%y)
    end
end

```

