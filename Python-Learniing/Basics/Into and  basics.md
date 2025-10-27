## Variables

A variable is just a name that points to some data in memory.
``
```
x=10
```
here, 
`x` is  the name (label)
`10` is the value , we wan to store
The value is stored somewhere in the memory 
`x` is just a label that says i can show u the way of value `10` , `10` is actually stores somewhere in a memory not in x . 

so when you do ,
```
y=x
```
now both x and y can tell the way to reach `10`.

Checking it,

```
x = 10
y = x
print(id(x))
print(id(y))

```

Both `id`s will be the same — meaning they are **pointing to the same object**.


```
[10]   <-- object in memory
  ^ \
  |  \
  x   y   <-- two labels pointing to the same object

```

 But,
 if you do,
 ```
 y += 5
 ```

what will happen ?
y = 15 but x still remains 10 , because integers are immutable.
So , it creates a new object `15` in am memory .
`y` now points to `15` but x still points to `10`.

```
[10]   <-- x
[15]   <-- y

```

## Mutable vs Immutable Objects

Mutable objects  = can be changed (like dict ,lists,sets)
Immutable objects = cannot be changed(like  numbers , strings , tuples)

```
a = [1, 2, 3]
b = a
b.append(4)
print(a)

```

`a` also becomes `[1, 2, 3, 4]`  
Because both names point to the **same list object** in memory!

### `for` Loop

- Use hota hai **iterables** (list, tuple, string, dict) par repeat karne ke liye

