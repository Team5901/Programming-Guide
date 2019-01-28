# Overview
A camera is used to provide vision to the driver.   
The camera is connected directly to the RoboRio via USB port.



## Importing
You will need to import some existing libraries to utilize the camera.   
This will go at the top of `Robot.java` along with the other imports.

```
import edu.wpi.first.wpilibj.CameraServer;
import edu.wpi.first.wpilibj.IterativeRobot;
```

##Adding a Camera
You will want to place this code when the Robot first starts up.   
Hint: The first file run is `Robot.java`. What method within this file is run first?

###### Declaration & Start Recording
```
USBCamera CAMERANAME = CameraServer.getInstance().startAutomaticCapture();
```

###### Change Resolution and Frame Rate
There is a limit on wireless bandwidth, so one MAY need to adjust quality and frame rate (FPS).
```
camera1.setResolution(320, 240);
camera1.setFPS(10);
```