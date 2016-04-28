---
layout: single
title:  "Unset the least significant bit"
permalink: /bitAlgos/unset-lsb/
date:   2016-04-16 14:14:36 +0000
---

## Given a binary number unset the rightmost set bit. ##
**Algorithm:**
The biwise "&" of any number n with n-1 unsets the rightmost set bit
e.g. 5=101 ,5-1=4=100 ,5&4=(101)&(100)=100(result with rightmost bit unset)<br/>


## Implementation

```ruby
def unset_rightmost(n)
    n&=(n-1)
end
```