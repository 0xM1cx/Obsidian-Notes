## We can use the following operations to create mutations to a set:

####  `.update()` or `|=`
It updates the set by adding elements from an iterable or another set.
```Python
H = set("Hacker")
R = set("Rank")
H.update(R)
print H

set(['a', 'c', 'e', 'H', 'k', 'n', 'r', 'R'])

```