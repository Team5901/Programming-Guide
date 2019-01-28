# Overview
Vision can be used to aim the robot.   
It is most suitable to use when targets are easily distinguishable (bright yellow cubes, orange balls), or for games that have lots of vision targets.   

Implementing vision has two steps: 
* Vision detection (easy) - Camera can detect the target reliably without confusing it with surrounding o bjects
* Vision integration (hard) - Combining vision with the robot

Team 5901 utilzes the Limelight Camera.

##Getting Started

Informating about mounting, wiring, imaging, and setting up the limelight

<http://docs.limelightvision.io/en/latest/>


```
import edu.wpi.first.networktables.NetworkTableEntry;
import edu.wpi.first.networktables.NetworkTableInstance;


    public void robotInit() {
       NetworkTableInstance.getDefault().getTable("limelight").getEntry("ledMode").setNumber(0);
```