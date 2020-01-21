# Overview
Vision can be used to aim the robot.   
It is most suitable to use when targets are easily distinguishable (bright yellow cubes, orange balls), or for games that have lots of vision targets.   

Implementing vision has two steps:      

* Vision detection (easy) - Camera can detect the target reliably without confusing it with surrounding objects.     
* Vision integration (hard) - Combining vision with the robot     

Team 5901 utilzes the Limelight Camera.

##Recommended Reading

Link | Description 
-----|------------
Mounting/Wiring/Imagine/Networking setup | <http://docs.limelightvision.io/en/latest/getting_started.html#>
Theory of how a vision processing works. Highly recommended to read to understand process. | <http://docs.limelightvision.io/en/latest/theory.html> 
How to tune the limelight | <http://docs.limelightvision.io/en/latest/vision_pipeline_tuning.html>


## Vision Code

The vision subsystem code has been created in previous years and can be reused.     
Several methods were created that can be called by different commands, can be summarized in the following table:

Method Name | Description | Example
------------|-------------|---------
getTx() | returns horizontal offset angle to camera | m_VisionSubsystem.getTx();
getTy() | returns vertical offset angle to camera | m_VisionSubsystem.getTy();
getTa() | returns target area, used to approximate distance to target) | m_VisionSubsystem.getTa();
targetAvailable() | returns a boolean if a target is detected | m_VisionSubsystem.targetAvailable();
turnOffLED() | turns off camera lights | m_VisionSubsystem.turnOffLED();
turnOnLED() | turns on camera lights | m_VisionSubsystem.turnOnLED();


##VisionSubsystem.java

```
/*----------------------------------------------------------------------------*/
/* Copyright (c) 2019 FIRST. All Rights Reserved.                             */
/* Open Source Software - may be modified and shared by FRC teams. The code   */
/* must be accompanied by the FIRST BSD license file in the root directory of */
/* the project.                                                               */
/*----------------------------------------------------------------------------*/

package frc.robot.subsystems;

import edu.wpi.first.networktables.NetworkTable;
import edu.wpi.first.networktables.NetworkTableEntry;
import edu.wpi.first.networktables.NetworkTableInstance;
import edu.wpi.first.wpilibj2.command.SubsystemBase;

public class VisionSubsystem extends SubsystemBase {

  public VisionSubsystem() {   

  }

  //Get Horizontal Offset Angle
  public double getTx(){
    return NetworkTableInstance.getDefault().getTable("limelight").getEntry("tx").getDouble(0);
  }

  //Get Vertical Offset Angle
  public double getTy(){
    return NetworkTableInstance.getDefault().getTable("limelight").getEntry("ty").getDouble(0);
  }

  //Get Target Area
  public double getTa(){
    return NetworkTableInstance.getDefault().getTable("limelight").getEntry("ta").getDouble(0);
  }

  //Return true if target is available, otherwise false
  public boolean targetAvailable(){
    if (NetworkTableInstance.getDefault().getTable("limelight").getEntry("tv").getDouble(0) < 1.0)
    {
      return false;
    }
    else
    {
      return true;
    }  
  }

  public void turnOffLED(){
    NetworkTableInstance.getDefault().getTable("limelight").getEntry("ledMode").setNumber(1);
  }

  public void turnOnLED(){
    NetworkTableInstance.getDefault().getTable("limelight").getEntry("ledMode").setNumber(3);    
  }

  @Override
  public void periodic() {
    // This method will be called once per scheduler run
  }
}

```