# Software Bootcamp Tutorial 3
## More Commands
Created Wednesday 13 August 2026

Overview
=====
- Another look at Commands: Decorators
- Commands as classes in separate files


Decorating Commands
----------------
In this tutorial, you'll explore several ways of modifying your commands. First, take a look at the [API referece for the Command class](https://github.wpilib.org/allwpilib/docs/release/java/edu/wpi/first/wpilibj2/command/Command.html#method-summary). In the method summary table, you'll see various methods described as decorating the command (e.g. andThen(), beforeStarting(), onlyWhile()). These decorators can be appended to your command triggers to add additional features or requirements.

1. Modify your LED project to wait 1.0 seconds after pressing X before turning on the light.

To do this, look at the beforeStarting(Command before) decorator. Note that this decorator is expecting a Command as its only parameter, not a duration in seconds like you might expect. While this makes things a bit more complicated, it also makes the decorator more powerful as you can imagine using it to wait for another command to complete and not just a fixed duration. For the purpose of this assignment, you'll need to provide a command that waits 1 second. Fortunately, WPILib provides a [WaitCommand](https://github.wpilib.org/allwpilib/docs/release/java/edu/wpi/first/wpilibj2/command/WaitCommand.html).

The general syntax for decorators looks like the following:

```java
m_driverController.a().whileTrue(m_exampleSubsystem.turnOn().beforeStarting(commandName));
```

2. When a limit switch is triggered, turn off the LED.


Commands as Explicit Classes
----------------
Commands can be written inline as we've done previously, or as their own explicit classes in separate files. As things get more complex, writing commands in their own files can significantly help with code readability.
