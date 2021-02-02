# Problem

## Kyu Rating

7

## Link

https://www.codewars.com/kata/5b71af678adeae41df00008c

## Description

A bug lives in a world which is a cuboid and has to walk from one corner of the cuboid to the opposite corner (see the picture below).

Define a function which takes 3 arguments: the length a , width b, and height c of the bug's "world", and finds the shortest distance needed to walk from start to finish. The dimensions will be positive numbers.

Note: The bug cannot fly and has to maintain contact with a surface at all times but can walk up walls.

Example
```
a=1, b=2, c=3: distance=4.242640687119285
```

# Solution (in Ruby)

Assuming strict input:
```ruby
def shortest_distance(a, b, c)
  [Math.sqrt((a+b)**2 + c**2), Math.sqrt((a+c)**2 + b**2), Math.sqrt((c+b)**2 + a**2)].min
end
```

Assuming non-strict input:
```ruby
def shortest_distance(a, b, c)
  input = [a,b,c].sort
  a = input.shift
  b = input.shift
  c = input.shift
  Math.sqrt((a+b)**2 + c**2)
end

```
