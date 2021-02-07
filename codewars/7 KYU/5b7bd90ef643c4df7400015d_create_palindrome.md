# Problem

## Kyu Rating

7

## Link

https://www.codewars.com/kata/5b7bd90ef643c4df7400015d

## Description

Consider the string "adfa" and the following rules:

```ruby
a) each character MUST be changed either to the one before or the one after in alphabet. 
b) "a" can only be changed to "b" and "z" to "y". 
```

From our string, we get:

```ruby
"adfa" -> ["begb","beeb","bcgb","bceb"]

Here is another example: 
"bd" -> ["ae","ac","ce","cc"]

--We see that in each example, one of the outcomes is a palindrome. That is, "beeb" and "cc".
```

You will be given a lowercase string and your task is to return True if at least one of the outcomes is a palindrome or False otherwise.

More examples in test cases. Good luck!

# Solution (in Ruby)

```ruby
def solve st
  combos = st.chars.map { |e| combinations(e) }
  length = combos.length

  combos[0..(length/2)-1].each_with_index do |elem, i|
    return false unless intersection?(elem, combos[length-i-1])
  end
  
  return true
end

def intersection?(arr1, arr2)
  !(arr1 & arr2).empty?
end

def combinations(char)
  result = []
  result << prev_char(char) unless prev_char(char) == char
  result << next_char(char) unless next_char(char) == char
  result
end

def next_char(char)
  char.downcase == 'z' ? char : (char.ord + 1).chr
end

def prev_char(char)
  char.downcase == 'a' ? char : (char.ord - 1).chr 
end
```