---
title:  "Counting Sort Algorithm"
permalink: /sorting/counting-sort/
date:   2016-04-16 14:14:36 +0000
tags: test

---
 

Counting sort is a non comparison-based linear sorting algorithm which can be used if the range of elements is known.

> Time-complexity: O(n+k), Auxiliary-space:O(n+k), Not In-place, Not stable

**Algorithm**

    1. Take a count array to store the frequency of each value in given range
    2. change count[i] to count[i]+count[i-1],i.e each element now stores the prefix sum of counts.
    3. take each value from the array and put it at the correct index in output array using count, decrement value of count! (correct index of a[i] will be count[a[i]-1])
    4. Finally copy the values of output array to array.
    

## Implementation
{% highlight ruby %}

def counting_sort(a=[9,8,7,6],min=0,max=10)
    if min>max
      return "invalid range"
    end
    
  	n=max-min+1
	count=Array.new(n,0)
	len=a.length
	output=Array.new(len)
  
  	for i in 0...len
		count[a[i]-min]+=1
	end
	
  	for i in 1...n
		count[i]+=count[i-1]
	end
		
	
	for i in 0...len
		output[count[a[i]-min]-1]=a[i]
		count[a[i]-min]-=1
	end
	
	for i in 0...len
		a[i]=output[i]
	end
	
	return a
	
end
{% endhighlight %}

