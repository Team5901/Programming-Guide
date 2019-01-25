# Overview
This page summarizes the overall steps required to program a robot.
Programming is iterative - you may need to repeat many of these steps as the season continues.


## Design
* Strategy - What is the team strategy for autonomous mode?
* Subsystems 
	* What subsystems will you have on your robot?
	* What does each subsystem need to do?  
	* What sensors should be used, if any?
* Controllers 
	* How many controllers is needed to control this robot?
	* What commands should be mapped to which buttons?

## Programming
* Motor Assignments
	* Motor controller CAN IDs (Work with Electrical Team)
	* Methods that control motors must be created
* Commands need to be created
	* Commands should call methods from subsystems
* Autonomous routines need to be created	
	* Will use CommandGroups of commands

## Testing
**Golden Rule: Your code doesnt work until you've tested it on the robot **

## Example - 2017 Steamworks - Design
* **Strategy** - Our team strategy is to start from three possible locations, meaning we need three different autonomous modes. We will try to place a gear in autonomous mode.
* **Subsystems** 
	* Drivetrain
		* Sensors - Encoder (measure distance), Gyro (measure angle)
		* Functions
			* Drive Straight
			* Turn to an angle
			* Turbo speed
			* Stop
	* Intake
		* Sensors - Encoder (measure how open intake is)
			* Open intake
			* Close intake
* **Commands**
	* Controllers 
		* Controller 1 - Driving
		* Controller 2 - Control intake

## Example - 2017 Steamworks Programming
* Subsystems need to be created
	* Drivetrain motors (4x) - 1,2,3,4
	* Intake motors (1x) - 5
	* Create methods
* Commands created
* Autonomous routines 	
	* Left Position Auto - Drive straight 1m, turn -60 degrees, drive straight 1m, open intake
	* Middle Position Auto - Drive straight 1m, open intake
	* Right Position Auto - Drive straight 1m, turn 60 degrees, drive straight 1m, open intake





