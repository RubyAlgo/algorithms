---
layout: single
title:  "Maximum sum with no two adjacent elements"
permalink: /arrays/maxsum-no-two-adjacent-element/
date:   2016-04-16 14:14:36 +0000
---


## Given an array of positive numbers,find the maximum possible sum such that no two chosen numbers are adjacent

Time-complexity:O(n)<br/>
Auxiliary-space: O(1)<br/>

**Implementation**

```ruby

def max_sum(a)
   len=a.length
   incl=a[0]
   excl=0
   for i in 1...len
       temp=[excl,incl].max
       incl=excl+a[i]
       excl=temp
   end
   return [incl,excl].max
end

max_sum([1,2,3,-1,4,5,0]) # => 9 

```

