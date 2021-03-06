# Problem

## Kyu Rating

7

## Link

https://www.codewars.com/kata/57f36495c0bb25ecf50000e7

## Description

Your task is to write function findSum.

Upto and including n, this function will return the sum of all multiples of 3 and 5.

For example:

findSum(5) should return 8 (3 + 5)

findSum(10) should return 33 (3 + 5 + 6 + 9 + 10)

# Solutions

## Ruby
```ruby
def find(n)
  [*3..n].select{ |n| n if (n % 3 == 0 || n % 5 == 0) }.reduce(:+)
end
```
