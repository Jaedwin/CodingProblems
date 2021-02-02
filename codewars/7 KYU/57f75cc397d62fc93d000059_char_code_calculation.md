# Problem

## https://www.codewars.com/kata/57f75cc397d62fc93d000059

## Description

Given a string, turn each character into its ASCII character code and join them together to create a number - let's call this number total1:

```
'ABC' --> 'A' = 65, 'B' = 66, 'C' = 67 --> 656667
```

Then replace any incidence of the number 7 with the number 1, and call this number 'total2':

```
total1 = 656667
              ^
total2 = 656661
              ^
```

Then return the difference between the sum of the digits in total1 and total2:

```
  (6 + 5 + 6 + 6 + 6 + 7)
- (6 + 5 + 6 + 6 + 6 + 1)
-------------------------
                       6
```

# Solution

```ruby
def calc(s)
  converted = convert_to_ascii(s)
  total1 = sum_numbers(converted)
  total2 = sum_numbers(replace_7_with_1(converted))
  total1 - total2
end

def char_value(char)
  char.ord
end

def convert_to_ascii(string)
  string.chars.map { |char| char_value(char) }.join.to_i
end

def replace_7_with_1(num)
  num.to_s.chars.map { |elem| elem == '7' ? '1' : elem }.join.to_i
end

def sum_numbers(nums)
  nums.to_s.chars.map { |num| e.to_i }.inject(:+)
end
```
