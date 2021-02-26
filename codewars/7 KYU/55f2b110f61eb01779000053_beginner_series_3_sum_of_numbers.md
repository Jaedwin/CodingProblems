# Problem

## Kyu Rating

7

## Link

https://www.codewars.com/kata/55f2b110f61eb01779000053

## Description

Given two integers a and b, which can be positive or negative, find the sum of all the integers between including them too and return it. If the two numbers are equal return a or b.

Note: a and b are not ordered!

# Solutions

## Ruby
```ruby
def get_sum(a,b)
  a == b ? a : ( a > b ? [*b..a].inject(:+) : [*a..b].inject(:+) )
end
```
