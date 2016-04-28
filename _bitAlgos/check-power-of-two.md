---
layout: single
title:  "Check if a given number is power of two"
permalink: /bitAlgos/check-power-of-two/
date:   2016-04-16 14:14:36 +0000
---


# Given a number,check if it is power of 2 or not without using division or modulo operator.

**Algorithm:**
For any power of 2,say x, the bitwise and of x and x-1 is always 0.
e.g. 64 = 1000000, 63= 0111111 now 1000000&0111111==0000000<br/>

## Implementation

```ruby
def check_power(x)
    if x&(x-1)==0
        print "#{x} is power of two"
    else
        print "#{x} is not power of two"
    end
end
check_power(126) # => 126 is not power of two 
check_power(1024) # => 1024 is power of two 
```

