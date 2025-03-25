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
```
[
    {file: 15127c}, 
    {
        file: 15127b
        zoomin: {
            file: 15127,
                quad: [
                    [0.7540417909622192, 0.5871764421463013],
                    [0.8121265769004822, 0.9136618971824646],
                    [4.0037689208984375, 3.538557529449463],
                    [1.5594348907470703, 0.09003715217113495]
                ]
        }
    }, 
    {
        file: 15127a,
        zoomin: {
            file: 15127,
                quad: [
                    [0.7540417909622192, 0.5871764421463013],
                    [0.8121265769004822, 0.9136618971824646],
                    [4.0037689208984375, 3.538557529449463],
                    [1.5594348907470703, 0.09003715217113495]
                ]
        }
    }
]

TODO:
- describe overlap between adjacent panos
