# Overview
This page summarizes the overall steps required to program a robot.    

## Design Phase
* Strategy - What is the team strategy for autonomous mode?
* Subsystems 
	* What subsystems will you have on your robot?
	* What does each subsystem need to do?  
	* What sensors should be used, if any?
	* How many actuators does each subsystem need?
* Controllers 
	* How many controllers is needed to control this robot?
	* What commands should be mapped to which buttons?

## Programming Phase
* Subsystems
	* Create objects (sensors.actuators, etc.) in Java
	* Program methods to control
* Commands need to be created, calling from subsystem methods
* Autonomous routines need to be created (optional for 2019)


## Testing 
* Test code & fix bugs 
* Look for new ways to do things smarter and more efficiently
* **Golden Rule: Your code doesnt work until you've tested it on the robot **

## Example


Lets say we want to design an arm that will lift a game object.   
The arm will squeeze ball with pistons, and then lift the ball.   
From a programmer standpoint, here is an example of our thought process.   

###### Design Phase
* Our arm will need to lift a game piece to a certain height 
	* This means you need at least one `motor` to lift your arm
	* This means you may need a `sensor`, like an `encoder` so you know the height of your arm
* Our arm will need to squeeze the ball with `pistons`
	* We will need a `solenoid` to activate our pistons
	* We will need an `air compressor` to generate air

###### Programming Phase

* Subsystems
	* Need to create `motor controller`, `encoder` , `solenoid`, and `compressor` in Java
	* Method/Command examples
		* Lift Arm 
		* Lower Arm
		* Stop Arm
		* Squeeze Ball
		* Release Ball
