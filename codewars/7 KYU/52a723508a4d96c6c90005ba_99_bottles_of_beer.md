# Problem

## Kyu Rating

7

## Link

https://www.codewars.com/kata/52a723508a4d96c6c90005ba

## Description

Complete the function that returns the lyrics for the song 99 Bottles of Beer as an array of strings: each line should be a separate element - see the example at the bottom.

Note: in order to avoid hardcoded solutions, the size of your code is limited to 1000 characters

# Solutions

## Ruby
```ruby
def sing
  result = []
  
  [*0..99].reverse.each do |n| 
    result << "#{n} bottles of beer on the wall, #{n} bottles of beer."
    result << "Take one down and pass it around, #{n-1} bottles of beer on the wall." unless n.eql? 0
  end
  result << "Go to the store and buy some more, 99 bottles of beer on the wall."
  
  result
end
```
