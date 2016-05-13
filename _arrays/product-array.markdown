---
layout: single
title:  "Create a product array from a given array"
permalink: /arrays/create-product-array/
date:   2016-04-16 14:14:36 +0000
---


## Given an array 'a',create a product array where product[i]==product of all elements except a[i]
**Time-complexity: O(n)**<br/>
**Space-complexity: O(n){for product array}**<br/>
**Auxiliary-space: O(1)**<br/>

**Implementation**

```ruby

def product_array(a)
    len=a.length
    product=Array.new(len,1) # Initilaize product array elements to 1
    temp=1
    
    #Loop to store product of left elements
    for i in 0...len
        product[i]=temp
        temp*=a[i]
    end
    
    temp=1 #reset temp variable to 1
  
    #Loop to multiply stored left products with right products
    for i in (len-1).downto(0)
        product[i]*=temp
        temp*=a[i]
    end
    
    return product
end

product_array([1,2,3,4,5,6])  # => [720, 360, 240, 180, 144, 120]

```

