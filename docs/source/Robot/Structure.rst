Structure
===========

..*@ANNA figure out how behaviours fits into this system

RobotMap.h
-------------
RobotMap is where we store almost all of our common includes as well as structs for each subsystem. 

We define our controllers at the top of the RobotMap struct, usually we have 3 controllers, a driver, coDriver, and a test controller. You can use any of these in your own code, just communicate to make sure people arent using the same buttons/trigger/ect 

We then have structs for each subsystem, this features all the motors, gearboxs, solenoids, sensors, ect in that subsystem. This is the actual physical stuff that gets passed into your subsystem later. Because of that we define ports, names and other stuff here. 

``struct intakeSystem {
  TalonSRX frontIntakeMotor{ControlMap::Intake::frontIntakeMotorPort};
  TalonSRX backIntakeMotor{ControlMap::Intake::backIntakeMotorPort};
};
``


ControlMap.h 
--------------

ControlMap is where we store variables and map controls (hence the name controlmap)

To organise these variables and make it a little neater we use structs: 

``struct Intake {
  static constexpr int frontIntakeMotorPort = 99; //this is a constant
  inline static bool intakeToggle = false; //not a constant 
};``

Note we use 99 when you dont know a port number yet just to make it easy to search through the code for unassigned port numbers 


At the bottom of ControlMap we define the controls, when you are adding a new controller button/trigger/ect please make sure another system is not already using it.


Behaviours
--------------

