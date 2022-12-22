Logic
=======

ngl didn't really know what to call this file, but it's about basic logic things that we use in FRC code. 


Toggle Button 
-----------------

We use toggle buttons alot, especially for things such as pneumatics, it's a good skill to know how to quickly create one. 

In your header file (either robot.h or whatever header file of the subsystem you are working with) create a boolean. 

``bool intakeToggle = false;`` 

Then in your cpp file we use this variable and the input from a controller

``if (driver->GetAButtonReleased()) {
    if (intakeToggle) {
      intakeToggle = false;
    } else {
      intakeToggle = true;
    }
  }
  if (intakeToggle) {
    intakeSolenoid->DoubleSolenoid::Set(frc::DoubleSolenoid::kForward);
  } else {
    intakeSolenoid->DoubleSolenoid::Set(frc::DoubleSolenoid::kReverse);
  }
``

Boom, now you have a toggle button for a solenoid! 


Setting a variable from a trigger with a deadzone 
----------------------------------------------------
Our controllers usually need a deadzone, we can do this very easily with a conditional statement. 

``double armSpeed = driver->GetLeftTriggerAxis() > 0.1 ? driver->GetLeftTriggerAxis() : 0;``

During season there will be a variable called ``deadzone`` that all subsystems will use which can be swapped out in the above code for ``0.1``


