# Introduction to Data Logging

Overview
======
In this tutorial we'll cover how to log data and how to analyze that data.

Generating Data
-----------
Data should generally be logged in the periodic method of each subsystem. This method is run every 20ms regardless of what commands are active or which subsystems are in use.

To log data, first import the necessary library:

```java
import edu.wpi.wpilibj.smartdashboard.SmartDashboard;
```

Then, inside the subsystem's periodic() method, log your data like this:

```java
@Override
public void periodic() {
  // Use a forward slash "/" to create clean folders inside AdvantageScope!
  SmartDashboard.putNumber("Shooter/RealRPM", m_motor.getVelocity());
  SmartDashboard.putNumber("Shooter/TargetRPM", 60.0);
}
```

Analyzing Data
-----------
We use AdvantageScope to analyze logs. This software can be used to observe data in real-time for real-world data as well as simulation, and it can playback old logs from prior matches.
