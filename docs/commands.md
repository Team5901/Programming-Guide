# Overview
Commands are used to execute robot functions.   
Commands call methods of subsystems to execute a task.

## Creating Commands

To create a command, right click subsystems in the explorer and select **`Create a new class/command `**.   
Select  **`command`**, and then name the command appropriately: **NAME**Command.   
For example, the command to stop an elevator should be named **stopElevator**Command.  
![](img/CreateCommand.JPG)

## Calling Subsystem Methods
The command requests the subsystem to perform a function.
For example, stopElevatorCommand will call on subsystem Elevator, and it's method stopElevator using the following code

```
elevator.stopElevator();
```

The next question is, where should this code be placed? See the next section for details.

## Code Placement
* **public stopElevatorCommand()** - If this command **`requires`** complete control of the subsystem, add the following code to this section (replace Elevator with subsystem name):
```
requires(Elevator);
```
Example: What happens if **`raiseElevatorCommand`** is run the same time as **`lowerElevatorCommand`**?   
To ensure both never run at the same time, we should require the subsystem for both commands.

* **protected void initialize()** - Code placed here will one run **once** when the command is run
* **protected void execute()** - Code placed here will run **continously** as long as the command is running
* **protected void isFinished()** - Code placed here determines **when** the command stops
* **protected void end()** - Code placed here runs once the command is **over**
* **protected void interrupted()** - Code placed here runs if the commands is **interrupted** by another command that requires the subsystem

![](img/CreatedCommand.JPG)


