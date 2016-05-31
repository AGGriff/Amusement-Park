# Amusement-Park Code

while true do
 
if redstone.getAnalogInput("right") > 0 then    --Basically detects if there is a redstone signal then sets off the track ten seconds later
  sleep(10)
  turtle.place()
 
elseif redstone.getAnalogInput("right") == 0 then    --No longer sets off that signal
  sleep(3)
 
  turtle.dig()
 
end
end


while true do
 
 
if redstone.getAnalogInput("back") > 0 then    -- When redstone signal is received place redstone torch to open gates above
  turtle.place()
 
elseif redstone.getAnalogInput("back") == 0 then
  sleep(2)                                          --When redstone signal is no longer active mine the redstone torch closing the gates
  turtle.dig()
end
 
end



while true do
 
if redstone.getAnalogInput("top") == 0 then    --Once redstone signal is received from trapped chest above take the gold or iron
  turtle.suckUp(1)
 
  if turtle.compareTo(16) then    --Compare the item sucked to slot 16 if it is the same move to the chests, place the gold in the acceptance chest and remove the necessary items from the other chests and bring them to the removing chest
    for n = 1, 3 do
      turtle.down()
    end
    for n = 1, 6 do
        turtle.forward()
    end
    turtle.up()
    turtle.drop()
    turtle.down()
    turtle.suck(1)
    turtle.turnLeft()
    turtle.forward()
    turtle.forward()
    turtle.turnRight()
    turtle.suck(64)
    turtle.turnLeft()
    turtle.forward()
    turtle.forward()
    turtle.turnLeft()
    for n = 1, 6 do
      turtle.forward()
    end
    for n = 1, 3 do
        turtle.up()
    end
     
    turtle.dropUp()
    turtle.select(2)
    turtle.dropUp()
    turtle.select(1)
    turtle.turnLeft()
    turtle.turnLeft()
    turtle.down()  
    turtle.down()
    turtle.down()
    turtle.forward()
    turtle.forward()
    turtle.turnRight()    
    turtle.forward()
    turtle.forward()
    turtle.forward()
    turtle.forward()
    turtle.turnRight()
    turtle.forward()
    turtle.forward()
    turtle.up()
    turtle.up()
    turtle.up()
    turtle.turnLeft()
    turtle.turnLeft()
     
 
  elseif turtle.compareTo(15) then    --Compare the sucked item to slot 15 and perfprm the same actions as above except for which chests are accessed
 
    for n = 1, 3 do
      turtle.down()
    end
    for n = 1, 6 do
      turtle.forward()
    end
    turtle.up()
    turtle.drop()
    turtle.down()
    turtle.turnLeft()
    for n = 1, 4 do
      turtle.forward()
    end
    turtle.turnRight()
    turtle.suck(1)
    turtle.turnRight()
    turtle.turnRight()
    for n =  1, 6 do
      turtle.forward()
    end
    for n = 1,3 do
      turtle.up()
    end
    turtle.dropUp()
    for n = 1, 3 do
      turtle.down()
    end
    turtle.turnRight()
    turtle.turnRight()
    for n = 1, 2 do
      turtle.forward()
    end
    turtle.turnRight()
    for n = 1, 4 do
      turtle.forward()
    end
    turtle.turnRight()
    for n = 1, 2 do
      turtle.forward()
    end
    for n = 1, 3 do
      turtle.up()
    end
    for n = 1, 2 do
      turtle.turnLeft()
    end
 
end
       
end
   
end


while true do
 
sleep(0.1)
 
if redstone.getAnalogInput("top") > 0 then    --if trapped chest is activated remove the item
  sleep(1)
  turtle.suckUp()
 
  if turtle.compareTo(16) then    --compare item to slot 16
    redstone.setAnalogOutput("front", 15)  --if it is the same activate redstone signal
    turtle.dropUp()    --place the item back in the chest
    sleep(2)    --sleep to avoid constant running of program
   
  end
  turtle.dropUp()    --Finally place any item that is not right back
 
else redstone.setAnalogOutput("front", 0)  --Do not output anymore redstone signal if trapped chest is not active
 
end
 
 
end


while true do
 
sleep(0.1)
 
if redstone.getAnalogInput("top") > 0 then    --if trapped chest is activated remove the item
  sleep(1)
  turtle.suckUp()
 
  if turtle.compareTo(16) then    --compare item to slot 16
    redstone.setAnalogOutput("front", 15)  --if it is the same activate redstone signal
    turtle.dropUp()    --place the item back in the chest
    sleep(2)    --sleep to avoid constant running of program
   
  end
  turtle.dropUp()    --Finally place any item that is not right back
 
else redstone.setAnalogOutput("front", 0)  --Do not output anymore redstone signal if trapped chest is not active
 
end
 
 
end


while true do
 
if redstone.getAnalogInput("back") > 0 then
  turtle.place()
 
elseif redstone.getAnalogInput("back") == 0 then
  sleep(1)
  turtle.dig()
 
end
 
end


local side = "right"
local password = "sosa"
local opentime = 7
while true do
  term.clear()
  term.setCursorPos(1, 1)
  print("Please Enter Password:")
  input = read("*")
  if input == password then
  print("Password Correct!")
  redstone.setOutput("right", true)
  sleep(2)
  redstone.setOutput("right", false)
  else
  print("Password Incorrect!")
  sleep(2)
  end
end


while true do
 
if redstone.getAnalogInput("front") == 0 then    -- Keeps the redstone signal on while not receiving one in the front
  redstone.setAnalogOutput("back", 15)
  sleep(0.1)
 
elseif redstone.getAnalogInput("front") > 0 then  -- Now that the tripwire sends out a redstone signal the computer no longer outputs a signal closing the piston
  redstone.setAnalogOutput("back", 0)
  sleep(1)
 
end
 
end


while true do
 
if redstone.getAnalogInput("back") > 0 then  --When the current is higher than 0 place a restone torch to deactivate the piston
  turtle.place()
 
elseif redstone.getAnalogInput("back") == 0 then  --When there is no longer a redstone signal deactivate the piston to deceive the user also turning the lights at the beginning on to notify the next participants
  sleep(0.2)
  turtle.dig()
 
end
 
end


if redstone.getAnalogInput("back") > 0 then
turtle.place()

elseif redstone.getAnalogInput("back") == 0 then
turtle.dig()
end

while true do

if redstone.getAnalogInput("back") > 0 then --Place redstone torch if redstone signal is active to open door
turtle.place()
sleep(2)

else turtle.dig() --Break redstone torch if no redstone signal

end
end

while true do

if redstone.getAnalogInput("back") > 0 then -- When the tripwire is activated the turtle will place a redstone torch to create a redstone loop
turtle.place()

elseif redstone.getAnalogInput("back") == 0 then -- As long as there is no redstone signal the turtle removes the torch stopping the loop
sleep(1)
turtle.dig()

end

end
