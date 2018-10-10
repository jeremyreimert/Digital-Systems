# Digital-Systems
Warehouse sorting project

This system was designed to act as a routing system to be used in a warehouse shipping environment. 
Each package has a barcode with information about where it is being shipped. 
The system uses this information to send each package to the appropriate truck for shipping. 
Once the truck has been filled, all packages that go to that truck must be rerouted back to the 
warehouse to await the arrival of an empty truck to be loaded. 

In this design example a 3-bit binary number is read by a scanner. 
In this case a random number generator simulates the codes that would be found on the packages. 
The “scanner” (RNG) sends the number through a 3:8 demux to the correct output. 
A counter is attached to each output to track the number of packages. Once the counter reaches its limit, 
a signal is sent via the Carry Out to a switch made of AND gates that routes the package for that output 
to the overflow output. Over flow is indicated by a blue LED. A set of LEDs indicate the level of the 
truck’s available capacity; green, yellow, orange. A flashing red LED indicates when full. 
The flashing is done using a T Flip Flop receiving a High from the Clock and the Carry Out of the counter. 
A reset button will reset any counter that has reached its maximum count. 
This is done by sending the Carry Out signal and the Button signal through an AND gate to the counter’s Clear Pin. 
The system also has an ON/OFF button that uses T Flip Flops to toggle the clock pulse. 
When the output of the flip flop is Low, the clock pulse is not sent through the system. 
Using these flip flops does reduce the frequency of the effective clock pulse by half. 

This system could be used for any sorting application. Other than package routing, 
this system could be applied to guide parts to work areas within a manufacturing setting. 
This system could be altered and applied to a vending machine that receives a product code 
and counts done until the item is gone. It could be expanded to include more outputs. 
If the scanner read more bits the demux could have more outputs and therefore more destinations. 
Instead of having only one output for overflow, there could be overflows or specific overflows for individual outputs. 
