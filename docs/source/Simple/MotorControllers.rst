Motor Controllers + Pneumatics
===============================
Most of the time, unless you are doing thing's with physics calcs you dont need to care about the type 
of motor just the motor controller.

TalonSRX's 
------------
The most common type of motor controller our team uses is a TalonSRX 

**Include:** ``#include <frc/>

In robot.h you can create the TalonSRX:

``TalonSRX *intakeMotor;``

In RobotInit you can initialise the motor by giving it a port:

``intakeMotor = new TalonSRX(99);``
Set the port number to 99 if you don't yet know what it is, this makes it easy the ctr f through the code later and assign ports all at once.


To set the motor you can either set power(0-1) or voltage (usually between 0 and 12)
``intakeMotor->Set(ControlMode::PercentOutput, 0.6);``
``intakeMotor 



VictorSPX's 
-------------
These are a slightly older motor controller, we dont use them on competition robots but they might pop up on a test bench or test but

**Include:** ``#include <>``

Spark Max's 
------------
Spark max's are used with Neo's and Neo 550's, they are used pretty common on final robots + sometimes on test robots if we are trying to test whether something is powerful enough

**Include:** ``#include <>``

Talon FX's 
------------
Talon FX's are the inbuilt motor controller in the Falcon motor.

**Include:** ``#include <>``

Double Solenoid 
-----------------
We almost always use pneumatics in the 

**Include:** ``#include <>`` 




Spark's 
---------
We only have one of this motor controller and you will probably never use it but here is the code just in case.

**Include:** ``#include <>``