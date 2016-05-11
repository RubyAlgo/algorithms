---
layout: single
title:  "Array rotation-IV (Block Swap Algorithm)"
permalink: /arrays/block-swap-algorithm/
date:   2016-04-16 14:14:36 +0000
---


## Given an zero indexed array and positive integer d,rotate the array by d-steps to the left.

## Block Swap Algorithm:

    Block swap algorithm for array rotation
      Initialize A=[0..d-1], B=[d..size-1]
        until size of A is equal to size of B
            a)  If A is shorter
                1. Divide B into Bl and Br such that Br is of same length as A.
                2. Swap A and Br to change ABlBr into BrBlA.
                3. Now A is at its final place, so recur on pieces of B.  
            b)  If A is longer
                1. Divide A into Al and Ar such that Al is of same length as B.
                2. Swap Al and B to change AlArB into BArAl.
                3. Now B is at its final place, so recur on pieces of A.
        Finally when A and B are of equal size, block swap them.


**Time-complexity:O(n)**<br/>
**Auxiliary-space:O(1)**<br/>

**Implementation**

RECURSIVE

```ruby

 #Driver function
def rotate_array(a, d) #Input array "a" and rotation by "d" elemets
  	finish =a.length-1
    block_swap(a,0,finish,d)
end
def block_swap(a,start,finish,d)
    n=finish-start+1
  	if n>0
      if d>n
        d%=n
      end
      
      if d==0
          return a
      end
      
      if d==n-d
          swap(a,start,start+d,d)
          return a
      elsif d<n-d
          swap(a,start,finish-d+1,d)
        block_swap(a,start,finish-d,d)
      else
          swap(a,start,d,n-d)
          block_swap(a,n-d,n-1,(2*d)-n)
      end
      
    end
    
    return a
    
end

    #Utility function for swapping
def swap(a,start1,start2,d)
        for i in 0...d
            temp = a[start1+i]
            a[start1+i] = a[start2+i]
            a[start2+i] = temp
        end
end
rotate_array([1,2,3,4,5,6,7,8,9,10],6)

```
Iterative

```ruby

def block_swap(a,d)
    n=a.length
  if n>0
      if d>=n
        d%=n
      end
    
      if d==0
          return a
      end

      if d==n-d
          swap(a,0,d,d)
      end

      i= d
      j= n-d

      while(i!=j)
        if i<j
            swap(a,d-i,d+j-i,i)
            j-=i
        else
            swap(a,d-i,d,j)
            i-=j
        end
      end
    swap(a,d-i,d,i)
  end
    return a
end
    
def swap(a,start1,start2,d)
    if (start1 != start2)
        for i in 0...d
            temp = a[start1+i]
            a[start1+i] = a[start2+i]
            a[start2+i] = temp
        end
    end
end

block_swap([1,2,3,4,5,6,7,8,9],5)

```
