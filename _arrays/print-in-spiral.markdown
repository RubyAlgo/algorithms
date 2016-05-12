---
layout: single
title:  "Print 2D-array in spiral order"
permalink: /arrays/print-array-in-apiral-order/
date:   2016-04-16 14:14:36 +0000
---


## Given a matrix(2D array),print all of its elements in spiral order.
e.g. [[1,2,3].[4,,5,6],[7,8,9]] => 1 2 3 6 9 8 7 4 5<br/>

**Implementation**

```ruby
def spiralOrder(a)
    n=a.length
    m=a[0].length
    t=0
    b=m-1
    r=n-1
    l=0
    dir=0
    while t<=b && l<=r
        if dir==0
            for i in l..r
                print "#{a[t][i]} "
            end
            t+=1
            dir=1
        elsif dir==1
            for i in t..b
                print "#{a[i][r]} "
            end
            r-=1
            dir=2
        elsif dir==2
            for i in r.downto(l)
                print "#{a[b][i]} "
            end
            b-=1
            dir=3
        else
            for i in b.downto(t)
                print "#{a[i][l]} "
            end
            l+=1
            dir=0
        end
    end
end

```

