---
layout: single
title:  "Count number of set bits in binary notation"
permalink: /bitAlgos/count-set-bits/
date:   2016-04-16 14:14:36 +0000
---


## Given a number "n",count the number of set bits in it. ##
**Algorithm(Brian Kernighan's method):**
1. set count=0 
2. while n>0 
    set n:=n&(n-1)
    increment count
3.return count

Time-complexity:O(logn)

## Implementation
```ruby
def count_set_bits(num)
  count=0
  while num>0
    num&=(num-1)
    count+=1
  end
  return count
end
```