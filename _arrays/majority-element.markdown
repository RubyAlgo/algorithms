---
layout: single
title:  "Majority Element in an Array"
permalink: /arrays/majority-element/
date:   2016-04-16 14:14:36 +0000
---


## Find majority element(if exists) in a given array.

**Majority element in unsorted array(Moore`s voting algorithm)**
Time-complexity: O(n)

```ruby
#Moore's Voting algorithm
def majority_element(a)
   len=a.length
   maj_index=0
   count=1
   for i in 1...len
       if a[i]==a[maj_index]
           count+=1
       else
           count-=1
       end
       if count==0
           a[maj_index]=a[i]
           count=1
       end
   end
    candidate=a[maj_index]
    count=0
   for i in 0...len
    if a[i]==candidate
        count+=1
    end
   end
 
   if count > (len/2)
     return candidate
   else
       return -1
   end
end
majority_element([2, 2, 3, 5, 2, 3])

```

**Majority element in sorted array(Using Binary search algorithm)**
Time-complexity: O(logn)

```ruby

def majority_element(a)
  	len=a.length
   	lo=0
  	hi=len-1
   	candidate=a[lo+(hi-lo)/2]
   while hi-lo>1
        mid=lo+(hi-lo)/2
        if a[mid]>=candidate
            hi=mid
        else
            lo=mid
        end
   end
  
   if a[hi]==candidate
       	left_index=hi
     	right_index=left_index+(len/2)
  		if a[right_index]==candidate
          return candidate
   		else
       		return -1
   		end
   end
  
    
end
majority_element([1,2, 2, 3, 3, 3, 3]) # => 3

```