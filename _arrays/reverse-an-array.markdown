---
layout: single
title:  "Reverse an array"
permalink: /arrays/reverse-an-array/
date:   2016-04-16 14:14:36 +0000
---


# Given a zero index array reverse the order of elements

## Implementation
```ruby
#Given an array reverse it without using extra-space
#Time-complexity: O(n), Auxiliary-space: O(1)

# Iterative
def reverse_array(a)
    right=a.length-1
    left=0
    while(left<right)
     #swap the elements
        temp=a[left]        #Swapping can be like done like this a[left],a[right]=a[right],a[left]
        a[left]=a[right]
        a[right]=temp
        
        left+=1
        right-=1
    end
    print a
end

reverse_array([1,2,3,4,5]) # => [5,4,3,2,1]

# Recursive

        #driver program
def driver_program(a)
    right=a.length-1
    left=0 
    reverse_array(a,left,right)
    print a
end
def reverse_array(a,left,right)
    
    return  if left>=right 
     #swap the elements
        temp=a[left]        
        a[left]=a[right]
        a[right]=temp
        reverse_array(a,left+1,right-1)
end

driver_program([1,2,3,4,5]) # => [5,4,3,2,1]

```

