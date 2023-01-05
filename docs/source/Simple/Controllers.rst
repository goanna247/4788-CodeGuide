Controllers
=============

Creating an xbox controller: 
----------------------------

Most of the time we use an xbox controller, here's how to create a simple one. 

**Step 1:** You need the XboxController include ``#include <frc/XboxController.h>`` put this at the top of robot.h

**Step 2:** inside your robot.h at the bottom of the file create an instance of a controller as a private variable:
``frc::XboxController *[name]``
We usually name controllers driver, codriver, or test 

**Step 3:** To use the controller there are a number of functions you can use to call different buttons/axis on xbox and joystick controllers 
They can all be found in https://github.com/wpilibsuite/allwpilib/blob/176fddeb4c44d7fc36d8a1358eb9ea5606660443/wpilibc/src/main/native/cpp/XboxController.cpp

**Step 4:** When coding for the robot you need to make sure that you are not using the same controller buttons/axis as someone else, communicate with the programming captain to ask which buttons you can use. 
During main build season we will have a meeting mid way through season where we will disucss which controls each susbsystem is using. 


