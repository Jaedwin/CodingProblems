# Problem

## Kyu Rating

5

## Link

https://www.codewars.com/kata/520b9d2ad5c005041100000f

## Description

Move the first letter of each word to the end of it, then add "ay" to the end of the word. Leave punctuation marks untouched.

Examples:

```ruby
pig_it('Pig latin is cool') # igPay atinlay siay oolcay
pig_it('Hello world !')     # elloHay orldway !
```

# Solution (in Ruby)

```ruby
def pig_it text
  text.split(' ').map { |word| /[!?]/.match(word) ? word : (word.chars.values_at *[1..-1, 0]).join('') + "ay" }.join(' ')
end
```
