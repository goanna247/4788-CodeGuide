Basic Logic 
=============

The most important thing to know is where to put your code. This changes every year (soz) depending on things like whether we are running simulations, the libraries we use and even how the lead programmer feels. 
This year the code is stored in the root directory because we will be running simulations + its easy :) 

There is a cpp, an include and a deploy folder in here. You don't need to worry about the deploy folder, i havent touched it once in my 4+ years of doing this however for some reason last season CJ and Viola put a semi disturbing image of a hairless cat in there. 
The cpp folder is where you put all of your .cpp files (omg), find Robot.cpp here. 

The include folder is where you store all your header files, such as Robot.h 

for nearly every cpp file there will be a corresponding header file, please for the love of all that is good name them the same thing.

Introduction to FRC Programming
------------------------------------

The starting 3 files in FRC code are: ``Robot.h`` , ``Robot.cpp`` and ``Main.cpp``
You will be using and editing Robot.h and .cpp alot throughout season, however please do not touch Main.cpp.


A FRC robot has 3 modes, Teleop, Autonomous and Test. This modes are not fixed (as in you can put driver controller code in auto and autonomous code in teleop)

**Teleop** 
Teleop is the driver controlled portion of the match, however there also may be autonomous portions of this, for example a magazine may be completely autonomous 

**Autonomous** 
Auto is usually the first 15 seconds of the match where the robot must move without input from a controller, when enabling autonomous you must make sure everyone around you is aware it's in auto mode, and you have someone who can pressed the enter key (disables the robot) if something goes wrong

**test** 
We havent used test mode much in the past, but is something we will definitely be exploring more this season, it is used to run simple programs on a subsystem to check that everything is correct. This mode is not enabled at any point during a real match 


You will find these modes in Robot.cpp 
``RobotInit`` runs once when the robot is first turned on, put all you initialisation stuff in here 
``RobotPeriodic`` runs whilst the robot is on, this is where you would call OnUpdate functions from subsystems 

``AutonomousInit`` runs once when autonomous is first enabled, schedule things here, zero sensors/encoders, ect. 
``AutonomousPeriodic`` runs whilst in autonomous mode 

``TeleopInit`` Runs once when teleop is first enabled 
``TeleopPeriodic`` runs whilst in autonomous mode 

``DisabledInit`` Runs once when the robot is disabled 
``DisabledPeriodic`` runs whilst the robot is disabled 

``TestInit`` runs once when the robot enters test mode
``TestPeriodic`` runs while the robot is in test mode 


Building + running your code
-------------------------------

You should be building your code fairly regularly, especially when you are just starting to learn FRC programming. Better to solve 1 error lots than hundreds of errors once. 

To build code in a termainal inside VS code you can run the command ``./gradlew build ``
or on an command line just ``gradlew build``

To clean build your code run ``gradlew clean build``, dont worry too much about this 

To **Deploy** your code run ``./gradlew deploy`` or ``gradlew deploy`` for terminal and command line respectively. Whilst doing this you must be connected to the robot, to do this go into where you would select your wifi 
network and select the radio name (usually the team number and or name of the robot you are trying to connect to, for us it is usually 4788)

After you have deployed code you can use driverstation to enable and use the robot. 
