# Problem

## Kyu Rating

7

## Link

https://www.codewars.com/kata/55fd2d567d94ac3bc9000064

## Description

Given the triangle of consecutive odd numbers:

```ruby
             1
          3     5
       7     9    11
   13    15    17    19
21    23    25    27    29
```

Calculate the row sums of this triangle from the row index (starting at index 1)

# Solutions

## Ruby
```ruby
def dont_give_me_five(start_,end_)
  sorted = [start_,end_].sort
  sorted.last.downto(sorted.first).to_a.reject{ |n| n.to_s.include? '5'}.count
end
```
