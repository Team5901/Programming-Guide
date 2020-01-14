# Overview
Controllers are operated by human players in order to command the robot.
In this section, you will create the controller and button objects in Java.
If you have completed the [command section](commands.md), you can then assign commands to specific button.

![](img/FlowRobotContainer.JPG)

## 1. Creating a Joystick Object

The example below declares to the program that there is an object named CONTROLLERNAME that is a joystick.
This should be placed under **`public class OI`**. 
The port number tells the computer which USB slot this controller should be in.

```
XboxController Controller1 = new XboxController(0);
```

## 2. Creating Button Objects 


```
new JoystickButton(<controllername>, Button.kA.value)
```

In the example above, we create the A button on a xbox controller named `Controller1`.

## 3. Assigning Commands to Buttons

NOTE: To complete this section, you must have completed the [command section](commands.md) of the is guide.

Depending on your design, you may want your buttons to behave differently.
Here are 3 possible button types you can use, depending on your application.

Add this immediately after you have created your button object.

###### whenPressed
Command starts when button is pressed, and it runs **until** the command's **`isFinished()`** method is satisfied.
```
.whenPressed(new ExampleCommand());
```

###### whileHeld (Most Common)
Command runs while button is held down, and is **interrupted** once the button is released. Note that interrupting a command does NOT automatically end it! You will need to modify the `interrupted()` method in the command by anding end(); to make sure it stops.
```
.whileHeld(new ExampleCommand());
```

###### whenReleased
Start command when button is released, and run **until** the command's **`isFinished()`** method is satisfied.
```
.whenReleased(new ExampleCommand());
```

###### ExampleCommand
![](img/Controller - Example.JPG)