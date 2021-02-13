# Problem

## Kyu Rating

6

## Link

https://www.codewars.com/kata/517abf86da9663f1d2000003

## Description

Complete the method/function so that it converts dash/underscore delimited words into camel casing. The first word within the output should be capitalized only if the original word was capitalized (known as Upper Camel Case, also often referred to as Pascal case).

```ruby
to_camel_case("the-stealth-warrior") # returns "theStealthWarrior"

to_camel_case("The_Stealth_Warrior") # returns "TheStealthWarrior"
```

# Solutions

## Ruby
```ruby
def to_camel_case(str)
  str.empty? ? '' : str.split(/[-_]/).each_with_index.map { |e,i| i.zero? ? e : e.capitalize }.join
end
```
