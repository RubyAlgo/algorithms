---
layout: single
title:  "Check if a given number is even or odd"
permalink: /bitAlgos/check-even-odd/
date:   2016-04-16 14:14:36 +0000
---


## Given a number,check if it is even or odd using bit operations. ##
**Algorithm:** 
 let num be x 
 find x&1 ,if result is 0 then even else odd. 
 The Least significant bit of odd number is always 1 and even is always 0, 
 hence x&1 will be 0 if even else odd. <br>


## Implementation
```ruby

    def check_evenOdd(x)
        if x&1==0
            print "#{x} is even"
        else
            print "#{x} is odd"
        end
    end
```

