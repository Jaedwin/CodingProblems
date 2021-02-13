# Problem

## Kyu Rating

7

## Link

https://www.codewars.com/kata/554b4ac871d6813a03000035

## Description

In this little assignment you are given a string of space separated numbers, and have to return the highest and lowest number.
```ruby
high_and_low("1 2 3 4 5")  # return "5 1"
high_and_low("1 2 -3 4 5") # return "5 -3"
high_and_low("1 9 3 4 -5") # return "9 -5"
```

# Solutions

## Ruby
```ruby
def high_and_low(numbers)
  numbers = numbers.split.map(&:to_i)
  "#{numbers.max} #{numbers.min}"
end
```
