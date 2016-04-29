---
layout: single
title:  "Swapping two elements"
permalink: /arrays/swapping-two-elements/
date:   2016-04-16 14:14:36 +0000
---


**Method 1 (using temporary variable)**

```ruby
def swap(a,b)
    temp = a
    a = b
    b = temp
    return a,b
end
```

**Method 2 (Ruby magic)**

```ruby
def swap(a,b)
    a,b=b,a
    return a,b
end
```

**Method 3 (Using sum and difference, no temporary variable required)**
Caveat: Can lead to integer overflow if a and b are really large integers

```ruby
def swap(a,b)
    a = a+b
    b = a-b
    a = a-b
    return a,b
end
```

**Method 4 (Using bitwise XOR ,no temporary variable required)**

```ruby
def swap(a,b)
    a = a^b
    b = a^b
    a = a^b
    return a,b
end
```