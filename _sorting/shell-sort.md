---
title:  "Shell Sort Algorithm"
permalink: /sorting/shell-sort/
date:   2016-04-16 14:14:36 +0000
tags: test

---
 

This is a test Post

# Shell Sort implementation(Diminishing Increment Sort)
> Time-complexity: O(n^2), In-place
will be using Knuth series :3n+1

## Implementation
{% highlight ruby %}
def shell_sort(a)
    n=a.length
    h=1
    
    while (h<n/3)  #for computing increment factor "h"
        h= (3*h)+1
    end
    
    while h>=1
    # Logic of insertion sort with inrement steps of "h"
        for i in h...n
            j=i
            while j>=h
                if a[j-h]>a[j]
                    temp=a[j]
                    a[j]=a[j-h]
                    a[j-h]=temp
                end
                j-=h
            end
        end
        h/=3
    end
    
    return a
    
end
{% endhighlight %}

