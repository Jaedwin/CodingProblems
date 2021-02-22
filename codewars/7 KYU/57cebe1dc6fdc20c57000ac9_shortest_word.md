# Problem

## Kyu Rating

7

## Link

https://www.codewars.com/kata/57cebe1dc6fdc20c57000ac9

## Description

Simple, given a string of words, return the length of the shortest word(s).

String will never be empty and you do not need to account for different data types.

# Solutions

## Ruby
```ruby
def find_short(s)
  s.split.map { |word| word.length }.min
end
```
