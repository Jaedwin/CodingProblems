# Problem

## Kyu Rating

7

## Link

https://www.codewars.com/kata/544aed4c4a30184e960010f4

## Description

Create a function named divisors/Divisors that takes an integer n > 1 and returns an array with all of the integer's divisors(except for 1 and the number itself), from smallest to largest. If the number is prime return the string '(integer) is prime' (null in C#) (use Either String a in Haskell and Result<Vec<u32>, String> in Rust).

## Ruby
```ruby
require 'prime'

def divisors(n)
  Prime.prime?(n) ? "#{n} is prime" : [*2..n/2].select{ |e| e if (n % e).zero? }
end
```
