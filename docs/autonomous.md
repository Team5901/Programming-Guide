# Overview
The first stage of the game usually involves an autonomus phase where Robots must act on their own without human intervention.
The first exception to this rule is in 2019 - Deep Space.

#
###### Declaration

```
    Command autonomousCommand;
    SendableChooser<Command> chooser = new SendableChooser<>();
```	
	
	
###### Adding Autonomous Options
You will need to add your autonomous commands to the SmartDashboard in order to choose between them.   
Place this code in the method that runs when the robot is first initialized within `Robot.Java`.

```
	chooser.addDefault("Autonomous Command", new AutonomousCommand());
	positionChooser.addDefault("Left", "left");
	positionChooser.addObject("Middle", "middle");
	positionChooser.addObject("Right", "right");
	positionChooser.addObject("Cross Line", "cross");
	SmartDashboard.putData("Auto Mode", positionChooser);
```

###### Run Autonomous Command
Place this code where the autonomous phase is initalized within `Robot.Java`.

```
    public void autonomousInit() {
	autonomousCommand = new AUTONOMOUSCOMMANDNAME();
		
	if (autonomousCommand != null) autonomousCommand.start();
```
