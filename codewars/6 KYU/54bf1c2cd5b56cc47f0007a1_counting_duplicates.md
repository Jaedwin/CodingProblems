# Problem

## Kyu Rating

6

## Link

https://www.codewars.com/kata/53da3dbb4a5168369a0000fe

## Description

Write a function that will return the count of distinct case-insensitive alphabetic characters and numeric digits that occur more than once in the input string. The input string can be assumed to contain only alphabets (both uppercase and lowercase) and numeric digits.

Example:

```ruby
"abcde" -> 0 # no characters repeats more than once
"aabbcde" -> 2 # 'a' and 'b'
"aabBcde" -> 2 # 'a' occurs twice and 'b' twice (`b` and `B`)
"indivisibility" -> 1 # 'i' occurs six times
"Indivisibilities" -> 2 # 'i' occurs seven times and 's' occurs twice
"aA11" -> 2 # 'a' and '1'
"ABBA" -> 2 # 'A' and 'B' each occur twice
```

# Solutions

## Ruby
```ruby
def duplicate_count(text)
    text.downcase.chars.uniq.count { |char| text.downcase.count(char) > 1 }
end
```
