Controllers
=============

Creating an xbox controller: 
----------------------------

Most of the time we use an xbox controller, here's how to create a simple one. 

**Step 1:** You need the XboxController include ``#include <frc/XboxController.h>`` put this at the top of robot.h

**Step 2:** inside your robot.h at the bottom of the file create an instance of a controller as a private variable:
``frc::XboxController *[name]``
We usually name controllers driver, codriver, or test 

