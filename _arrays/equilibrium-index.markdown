---
layout: single
title:  "Equilibrium Index in an array"
permalink: /arrays/equilibrium-index/
date:   2016-04-16 14:14:36 +0000
---


## Given an zero indexed unsorted array find(if exists) the equilibrium index.
Equilibrium index of an array is an index such that the sum of elements at lower indexes is equal to the sum of elements at higher indexes.<br/>
For example, in an arrya A:<br/>
A[]=[-7,1,5,2,-4,3,0]<br/>
3 is an equilibrium index, because:<br/>
A[0] + A[1] + A[2] = A[4] + A[5] + A[6]<br/>
**Time-complexity: O(n)**<br/>
Auxiliary-space: O(1)<br/>

**Implementation**

```ruby
def find_equilibrium(a)
  len = a.length
  leftsum=0
  rightsum=0
  for x in a
    rightsum+=x
  end
  for i in 0...len
    rightsum-=a[i]
    if (leftsum == rightsum)
      return i
    end
    leftsum+=a[i]
  end
  
  return -1
      
end

```

