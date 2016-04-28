---
layout: single
title:  "Shuffling an array"
permalink: /arrays/shuffling-an-array/
date:   2016-04-16 14:14:36 +0000
tags: test
---

This is a test Post

## Knuth Shuffling Algorithm ##
**Choose random number between i and n-i and swap**

**Time-complexity: O(n)**

## Implementation ##
```ruby
def shuffle(arr)
  len = arr.length
  for i in 0...len
    r = Random.rand(len-i)+i
    swap(arr,i,r)
  end
  return arr
end


def swap(arr,i,j)
  temp = arr[i]
  arr[i] = arr[j]
  arr[j] = temp
end


shuffle([1,2,3,4,5,6])
```

## Fitcher-Yates shuffling algorithm ##

**Start from last element,swap with random element from the array,decrement array size by one and repeat until array size is 1**

**Time-complexity: O(n)**

## Implementation
```ruby
def shuffle(arr)
   n=arr.length
   for i in (n-1).downto(1)
    j=Random.rand(i+1)
    swap(arr,i,j)
   end
   print arr
end

def swap(arr,i,j)
  temp = arr[i]
  arr[i] = arr[j]
  arr[j] = temp
end

shuffle([1,2,3,4,5,6])
```
