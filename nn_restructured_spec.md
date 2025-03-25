# Restructured Photo Set Spec

handwritten JSON-ish

## Simple Reordering
(this covers so few cases it isn't useful)

```
order: [231, 231b, 231c, 231a]
```

However, need to be clear whether wraps or not:

```
{
    order: [231, 231b, 231c, 231a],
    wraps: True
}
```


## Order + Zoom-Ins

Ordering is implicity left-to-right, clockwise as viewed from above.

Simplest:
```
[
    {file: 15127c}, 
    {file: 15127b}, 
    {
        file: 15127a,
        zoomin: 15127
    }
]
```

Multiple views connect to 15127:
This is more correct, but optional
```
[
    {file: 15127c}, 
    {
        file: 15127b
        zoomin: 15127
    }, 
    {
        file: 15127a,
        zoomin: 15127
    }
]
```

# Defining zoom-in:
- 2d location
- Quad (4 x 2d points)

TODO:
- overlaps between panos
