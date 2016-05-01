---
layout: single
title:  "Union And Intersection of two arrays"
permalink: /arrays/union-and-intersection-of-two-arrays/
date:   2016-04-16 14:14:36 +0000
---


## Given two sorted arrays ,Print the elements in the union and intersection of these arrays
**Time-complexity:O(n+m)(n=length of array1 and m=length of array2)**<br/>
**Auxiliary-space: O(1)**


** Method for finding Union**

```ruby
def union(a,b)
    len1=a.length
    len2=b.length
    ctr1=0
    ctr2=0
    puts "Union of the gives arrays:"
    while (ctr1<len1 && ctr2<len2)
        if a[ctr1]==b[ctr2]
            print "#{a[ctr1]} "
            ctr1+=1
            ctr2+=1
        elsif a[ctr1]<b[ctr2]
            print "#{a[ctr1]} "
            ctr1+=1
        else
            print "#{b[ctr2]} "
            ctr2+=1
        end
    end
    
    #Printing remaining elements(if any)
    while ctr1<len1
        print "#{a[ctr1]} "
        ctr1+=1
    end
    while ctr2<len2
        print "#{b[ctr2]} "
        ctr2+=1
    end
        
end
```

**Method for finding Intersection**

```ruby
def intersection(a,b)
    len1=a.length
    len2=b.length
    ctr1=0
    ctr2=0
    puts "Intersection of the gives arrays:"
    while (ctr1<len1 && ctr2<len2)
        if a[ctr1]==b[ctr2]
            print "#{a[ctr1]} "
            ctr1+=1
            ctr2+=1
        elsif a[ctr1]<b[ctr2]
            ctr1+=1
        else
            ctr2+=1
        end
    end
end

```

**Ruby magic: One line solutions**

```ruby
def union(a,b)
    print a | b   # union([1,2,3],[2,3,4]) => [1, 2, 3, 4] 
end

def intersection(a,b)
    print a & b     # intersection([1,2,3],[2,3,4]) => [2, 3]
end
```