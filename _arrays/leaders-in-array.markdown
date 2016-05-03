---
layout: single
title:  "Leaders in an array"
permalink: /arrays/leaders-in-array/
date:   2016-04-16 14:14:36 +0000
---


## Given an zero indexed unsorted array find(if exist) the leaders in an array.
An element is leader if it is greater than all the elements to its right side,the rightmost element is always a leader. <br/>
Time-complexity: O(n)<br/>
Auxiliary-space: O(1)<br/>

**Implementation**

```ruby
def find_leaders(a)
    n = a.length
    max_from_right = a[n-1]
    print "#{max_from_right}"+" "
    
    for i in (n-2).downto(0)
        if a[i]>max_from_right
            max_from_right=a[i]
            print "#{max_from_right}"+" "
        end
    end
end

find_leaders([16, 17, 4, 3, 5, 2]) # => 2 5 17

```

