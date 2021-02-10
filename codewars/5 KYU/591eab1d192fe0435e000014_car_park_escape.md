# Problem

## Kyu Rating

5

## Link

https://www.codewars.com/kata/591eab1d192fe0435e000014

## Description

Your task is to escape from the carpark using only the staircases provided to reach the exit. You may not jump over the edge of the levels (you’re not Superman!) and the exit is always on the far right of the ground floor.

Rules:

```ruby
1. You are passed the carpark data as an argument into the function.

2. Free carparking spaces are represented by a 0

3. Staircases are represented by a 1

4. Your parking place (start position) is represented by a 2

5. The exit is always the far right element of the ground floor.

6. You must use the staircases to go down a level.

7. You will never start on a staircase.

8. The start level may be any level of the car park.

9. Each floor will have only one staircase apart from the ground floor which will not have any staircases.
```

Returns:

```ruby
Return an array of the quickest route out of the carpark

R1 = Move Right one parking space.

L1 = Move Left one parking space.

D1 = Move Down one level.
```

Example:

Initialise: 

```ruby
carpark = [[1, 0, 0, 0, 2],
           [0, 0, 0, 0, 0]]
```

Working Out:

```ruby
- You start in the most far right position on level 1
- You have to move Left 4 places to reach the staircase => "L4"
- You then go down one flight of stairs => "D1"
- To escape you have to move Right 4 places => "R4"
```

```ruby
result = ["L4", "D1", "R4"]
```

Result:

# Solution (in Ruby)

```ruby
def escape(carpark)
  # Tracking
  output = []
  beginPos = nil
  stairPos = nil
  
  # Get # of floors
  numOfFloors = carpark.length
  numOfSpots = carpark.first.length
  
  return [] if numOfFloors == 1
  
  # Traverse down through floors
  carpark.each_with_index do |floor, index|  
  
    floor.each_with_index do |spot, index|
      beginPos = index if spot == 2
      stairPos = index if spot == 1
    end
    
    # Skip floors until on the starting floor
    next if beginPos.nil?
    
    # If on the first floor (last element in the array)
    if (numOfFloors-1 - index).zero?
      puts "#{numOfSpots}, #{beginPos+1}"
      distanceToExit = numOfSpots - (beginPos+1)
      output << 'R' + distanceToExit.abs.to_s unless distanceToExit == 0
      break
    end
    
    distanceToMove = beginPos - stairPos
    beginPos = stairPos
      
    if distanceToMove.positive?
      output += ['L' + distanceToMove.abs.to_s, 'D1']
    elsif distanceToMove.negative?
      output += ['R' + distanceToMove.abs.to_s, 'D1']
    else
      output << "D#{output.pop.split('D').last.to_i + 1}"
    end 
  end
  output
end
```
