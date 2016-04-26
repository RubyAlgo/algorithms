---
title:  "Bubble Sort Algorithm"
permalink: /sorting/bubble-sort/
date:   2016-04-16 14:14:36 +0000
tags: test

---
 

This is a test Post

# Bubble Sort Implementation (works by repeatedly swapping the adjacent elements if they are in wrong order.)
# Time-complexity : O(n^2), In-place, Can be made stable
# Takes O(n^2) even when array already sorted (hence can be optimized by stopping the algorithm if inner loop didn’t cause any swap.)

## Sub-Heading
{% highlight ruby %}

def bubble_sort(a)
   n=a.length
   for i in 0...n-1
    for j in 0...n-i-1
        if a[j]>a[j+1]
            temp=a[j]
            a[j]=a[j+1]
            a[j+1]=temp
        end
    end
   end
   return a
end
{% endhighlight %}

# Bubble Sort optimized
# Best case: Array already sorted (O(n))


{% highlight ruby %}

def bubble_sort(a)
   n=a.length
   for i in 0...n-1
    swapped = false
    for j in 0...n-i-1
        if a[j]>a[j+1]
            temp=a[j]
            a[j]=a[j+1]
            a[j+1]=temp
            swapped = true
        end
    end   
    if swapped == false
        break
    end
   end
   return a
end
{% endhighlight %}