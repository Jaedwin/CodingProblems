# Problem

## Kyu Rating

7

## Link

https://www.codewars.com/kata/5412509bd436bd33920011bc

## Description

Usually when you buy something, you're asked whether your credit card number, phone number or answer to your most secret question is still correct. However, since someone could look over your shoulder, you don't want that shown on your screen. Instead, we mask it.

Your task is to write a function maskify, which changes all but the last four characters into '#'.
# Solutions

## Ruby
```ruby
def maskify(cc)
  cc.size < 4 ? cc : '#' * (cc.size - 4) + cc.chars[-4..-1].join
end
```
