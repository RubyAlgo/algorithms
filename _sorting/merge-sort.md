---
title:  "Merge Sort Algorithm"
permalink: /sorting/merge-sort/
date:   2016-04-16 14:14:36 +0000
tags: test

---
 

This is a test Post

## Merge Sort (divides input array in two halves, calls itself for the two halves and then merges the two sorted halves recursively)

> Time-complexity: O(nlogn),Auxiliary Space: O(n),Stable
Algorithmic Paradigm: Divide and Conquer
Uses: Sorting linked lists(implementation details differ), Counting inversions in array

**Algorithm:**

 MergeSort(arr[], l,  r)
 
    * If r > l
    *       1. Find the middle point to divide the array into two halves:  
    *               middle m = (l+r)/2
    *       2. Call mergeSort for first half:   
    *               Call mergeSort(arr, l, m)
    *       3. Call mergeSort for second half:
    *               Call mergeSort(arr, m+1, r)
    *       4. Merge the two halves sorted in step 2 and 3:
    *               Call merge(arr, l, m, r)
    
## Implementation

{% highlight ruby %}

 # Logic to merge two sub arrays
 
 def merge(a,l,m,r)
    n1 = m-l+1
    left = Array.new(n1) # Created temp array for storing left subarray
    n2 = r-m
    right = Array.new(n2) # Created temp array for storing right subarray
    
    for i in 0...n1         #Copy values from left subarray to temp array
        left[i]= a[l+i]
    end
    
    for i in 0...n2          #Copy values from Right subarray to temp array
        right[i]= a[m+1+i]
    end
    
    i=0
    j=0
    
    # Comparing and merging two sub arrays
    for k in l..r
        if i>=n1
            a[k]=right[j]
            j+=1
        elsif j>=n2
            a[k]=left[i]
            i+=1
        elsif left[i]>right[j]
            a[k]=right[j]
            j+=1
        else
            a[k]=left[i]
            i+=1
        end
    end
 end
 
  # Merge Sort 
 def merge_sort(a,l,r)
     if l<r
         m=l+(r-l)/2
         merge_sort(a,l,m)
         merge_sort(a,m+1,r)
         merge(a,l,m,r)
     end
 end
{% endhighlight %}

