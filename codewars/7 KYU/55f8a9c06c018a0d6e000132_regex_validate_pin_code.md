# Problem

## Kyu Rating

7

## Link

https://www.codewars.com/kata/558fc85d8fd1938afb000014

## Description

ATM machines allow 4 or 6 digit PIN codes and PIN codes cannot contain anything but exactly 4 digits or exactly 6 digits.

If the function is passed a valid PIN string, return true, else return false.

# Solutions

## Ruby
```ruby
def validate_pin(pin)
  !!(pin.delete("\n") =~ /^\d{4}$|^\d{6}$/)
end
```
