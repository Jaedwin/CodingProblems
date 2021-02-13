# Problem

## Kyu Rating

6

## Link

https://www.codewars.com/kata/5526fc09a1bbd946250002dc

## Description

You are given an array (which will have a length of at least 3, but could be very large) containing integers. The array is either entirely comprised of odd integers or entirely comprised of even integers except for a single integer N. Write a method that takes the array as an argument and returns this "outlier" N.

Example:

```ruby
[2, 4, 0, 100, 4, 11, 2602, 36]
Should return: 11 (the only odd number)

[160, 3, 1719, 19, 11, 13, -21]
Should return: 160 (the only even number)
```

# Solutions

## Ruby
```ruby
def find_outlier(integers)
  integers.select{ |n| n.odd? }.one? ? integers.select{ |n| n.odd? }.first : integers.select{ |n| n.even? }.first
end
```

## Better Solution (Top Solution)
```ruby
def find_outlier(integers)
  integers.partition(&:odd?).find(&:one?).first
end
```
