# Chapter 2 (Pattern Matching)

Most important concept here is that in elixir the use of the equals sign does _not_ mean assignment. It is a check if the left hand side can be matched to the right hand side.

```
a = 1 # passes
1 = a # passes as a is now equal to 1
a = 2 # passes as we can re-assign the left side to 2
3 = a # fails as the value 3 does not match the pattern 2 and it cannot re-assign the right hand side
```

This can be used with more complex patterns:

```
a = 4
[a, b, c] = [1, 2, 3]
a
> 1
b
> 2
c
> 3
```

## Ignoring Values

We can ignore values with underscores and acts like a wildcard. I will accept any values here

```
[1, _, _ ] = [1, 2, 3]
[1, _, _ ] = [1, 4, 7]

```

## Variables bind once

```
[a, b, a ] = [1, 2, 1] # works as a has been bound to 1
[a, b, a ] = [1, 2, 3] # does not work as a cannot be re-bound to 3

```

By default, the value of a variable will always be matched with a new value. An existing value can be reused with caret (`^`). This is called the pin operator

```

a = 1
a = 2
^a = 3 # This fails as we do not set a new value for a

```

```

```
