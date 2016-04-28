---
layout: single
title:  "Finding Square root (Babylonian Method)"
permalink: /mathematics/babylonian-sqrt/
date:   2016-04-16 14:14:36 +0000
tags: test
---

This is a test Post

## Babylonian method for finding square root( based on Newton–Raphson method) ##


## Implementation ##

```ruby
def sqrt_babylonian(num)
    x=num
    y=1.0
    e=0.000001              #Desired approximation or accuracy level
    while x-y>e
        x=(x+y)/2
        y=num/x
    end
    return x
end

sqrt_babylonian(26) # => 5.099019513684702 
```

