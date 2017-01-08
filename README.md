Airport Challenge
=================
First solo weekend challenge for Makers Academy.

A small programme designed to simulate the take off and landing of aircraft from airports.

User stories
---------
```
As an air traffic controller 
So I can get passengers to a destination 
I want to instruct a plane to land at an airport and confirm that it has landed 

As an air traffic controller 
So I can get passengers on the way to their destination 
I want to instruct a plane to take off from an airport and confirm that it is no longer in the airport

As an air traffic controller 
To ensure safety 
I want to prevent takeoff when weather is stormy 

As an air traffic controller 
To ensure safety 
I want to prevent landing when weather is stormy 

As an air traffic controller 
To ensure safety 
I want to prevent landing when the airport is full 

As the system designer
So that the software can be used for many different airports
I would like a default airport capacity that can be overridden as appropriate
```
Solution
---------
My solution includes two classes - Airport and Plane - in order to adhere to the single responsibility principle.  I have also included a Weather module in order to simulate different weather conditions - weather may occaisionally be stormy, in which case planes will be unable to take off or land.  

The code guards against edge cases including airborne planes taking off, planes taking off from airports where they are not located, and grounded planes landing.

Usage
---------
```
2.2.3 :001 > require './lib/airport'
 => true 
2.2.3 :002 > airport = Airport.new
 => #<Airport:0x0000000148a0c0 @grounded=[], @capacity=10> 
2.2.3 :003 > plane = Plane.new
 => #<Plane:0x00000001467ca0 @airborne=true> 
2.2.3 :004 > airport.receive_plane(plane)
 => [#<Plane:0x00000001467ca0 @airborne=false>] 
2.2.3 :005 > airport.release_plane(plane)
 => #<Plane:0x00000001467ca0 @airborne=true> 
```

