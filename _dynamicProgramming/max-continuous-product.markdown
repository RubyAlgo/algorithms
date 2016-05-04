---
layout: single
title:  "Largest product continuos subarray"
permalink: /dynamicProgramming/max-continuos-product/
date:   2016-04-16 14:14:36 +0000
---

## Given a zero index array find the product of contiguos subarray which has the largest product.
Time-complexity: O(n)<br/>
Auxiliary space: O(1)

### Implementation
**Note:  It doesn’t work for arrays like {0, 0, -20, 0}, {0, 0, 0}.. etc**

{% highlight ruby %}

def max_product(a)
   len=a.length
   max_ending_here=min_ending_here=max_so_far=1
   for i in 0...len
        # If this element is +ve, update max_ending_here. 
        # Update minEndingHere only if minEndingHere is negative
        if a[i]>0
            max_ending_here=max_ending_here*a[i]
            min_ending_here = [min_ending_here*a[i],1].min
            
        # If this element is 0, then the maximum product 
        # cannot end here, make both maxEndingHere and minEndingHere 0
        # Assumption: Output is alway greater than or equal to 1.
        elsif a[i]==0
            max_ending_here=min_ending_here=1
            
         # If this element is -ve,min_ending here is previous max_ending_here*current
         #max_ending_here is min of previous min_ending_here*current and 1
        else
            temp=max_ending_here
            max_ending_here=[min_ending_here*a[i],1].max
            min_ending_here=temp*a[i]
        end
        
        max_so_far=max_ending_here if max_so_far<max_ending_here
   end
        return max_so_far
end

max_product([-2, -3, 0, -2, -40]) # => 80

{% endhighlight %}

