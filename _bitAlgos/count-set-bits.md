---
layout: single
title:  "Count number of set bits in binary notation"
permalink: /bitAlgos/count-set-bits/
date:   2016-04-16 14:14:36 +0000
tags: test
---

This is a test Post

## Given a number "n",count the number of set bits in it. ##
> Algorithm: 
 Brian Kernighan's method(set count=0 ,while n>0 set n:=n&(n-1) and increment count, return count)
 Time-complexity:O(logn)

## Sub-Heading

{% highlight ruby %}
def count_set_bits(num)
  count=0
  while num>0
    num&=(num-1)
    count+=1
  end
  return count
end
{% endhighlight %}

## Heading 2