# Problem

## Kyu Rating

6

## Link

https://www.codewars.com/kata/546f922b54af40e1e90001da

## Description

Welcome.

In this kata you are required to, given a string, replace every letter with its position in the alphabet.

If anything in the text isn't a letter, ignore it and don't return it.

"a" = 1, "b" = 2, etc.

Example:

```ruby
alphabet_position("The sunset sets at twelve o' clock.") => "20 8 5 19 21 14 19 5 20 19 5 20 19 1 20 20 23 5 12 22 5 15 3 12 15 3 11"
```

# Solutions

## Ruby
```ruby
def alphabet_position(text)
  text.downcase.gsub(/\W|\d|_/, '').chars.map{ |c| ([*'a'..'z'].find_index(c) + 1).to_s }.join(' ')  
end
```
