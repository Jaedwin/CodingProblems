# Problem

## Kyu Rating

5

## Link

https://www.codewars.com/kata/513e08acc600c94f01000001

## Description

The rgb function is incomplete. Complete it so that passing in RGB decimal values will result in a hexadecimal representation being returned. Valid decimal values for RGB are 0 - 255. Any values that fall out of that range must be rounded to the closest valid value.

Note: Your answer should always be 6 characters long, the shorthand with 3 will not work here.

The following are examples of expected output values:
```ruby
rgb(255, 255, 255) # returns FFFFFF
rgb(255, 255, 300) # returns FFFFFF
rgb(0,0,0) # returns 000000
rgb(148, 0, 211) # returns 9400D3
```

# Solutions

## Ruby
```ruby
def rgb(r, g, b)
  "#{convertToHex(r)}#{convertToHex(g)}#{convertToHex(b)}"
end

def convertToHex(val)
  val = (val > 255 ? 255 : val < 0 ? 0 : val).to_f
  intVal = ((val/16).to_i).to_s(16).upcase
  remVal = ((val/16 % 1)*16).to_i.to_s(16).upcase
  intVal + remVal
end
```
