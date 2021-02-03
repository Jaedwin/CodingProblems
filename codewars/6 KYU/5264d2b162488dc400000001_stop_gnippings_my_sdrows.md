# Problem

## Kyu Rating

6

## Link

https://www.codewars.com/kata/5264d2b162488dc400000001

## Description

Write a function that takes in a string of one or more words, and returns the same string, but with all five or more letter words reversed (Just like the name of this Kata). Strings passed in will consist of only letters and spaces. Spaces will be included only when more than one word is present.

Examples: spinWords( "Hey fellow warriors" ) => returns "Hey wollef sroirraw" spinWords( "This is a test") => returns "This is a test" spinWords( "This is another test" )=> returns "This is rehtona test"

# Solution (in Ruby)

```ruby
def spin_words(string)
  string.split(' ').map { |word| word.length >= 5 ? word.reverse : word }.join(' ')
end
```