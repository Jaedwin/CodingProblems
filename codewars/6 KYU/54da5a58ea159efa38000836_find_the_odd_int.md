# Problem

## Kyu Rating

6

## Link

https://www.codewars.com/kata/54da5a58ea159efa38000836

## Description

Given an array of integers, find the one that appears an odd number of times.

There will always be only one integer that appears an odd number of times.

# Solution (in Ruby)

```ruby
def find_it(seq)
  result = Hash.new(0)
  seq.each { |num| result[num] += 1 }
  result.select { |k,v| k if v.odd? }.keys.first
end
```
