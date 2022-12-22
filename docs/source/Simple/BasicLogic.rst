Basic Logic 
=============


Introduction to FRC Programming
------------------------------------

The starting 3 files in FRC code are: ``Robot.h`` , ``Robot.cpp`` and ``Main.cpp``
You will be using and editing Robot.h and .cpp alot throughout season, however please do not touch Main.cpp.



A FRC robot has 3 modes, Teleop, Autonomous and Test. This modes are not fixed (as in you can put driver controller code in auto and autonomous code in teleop)

**Teleop** 
Teleop is the driver controlled portion of the match, however there also may be autonomous portions of this, for example a magazine may be completely autonomous 

**Autonomous** 
Auto is usually the first 15 seconds of the match where the robot must move without input from a controller, when enabling autonomous you must make sure everyone around you is aware it's in auto mode, and you have someone who can pressed the enter key (disables the robot) if something goes working

**test** 
We havent used test mode much in the past, but is something we will definetly be exploring more this season, it is used to run simple programs on a subsystem to check that everything is correct. This mode is not enabled at any point during a real match 


You will find these modes in Robot.cpp 
``RobotInit`` runs once when the robot is first turned on, put all you initialisation stuff in here 
``RobotPeriodic`` runs whilst the robot is on, this is where you would call OnUpdate functions from subsystems 

``AutonomousInit`` runs once when autonomous is first enabled, schedule things here, zero sensors/encoders, ect. 
``AutonomousPeriodic`` runs whilst in autonomous mode 

``TeleopInit`` Runs once when teleop is first enabled 
``TeleopPeriodic`` runs whilst in autonomous mode 

``DisabledInit`` Runs once when the robot is diabled 
``DisabledPeriodic`` runs whilst the robot is diabled 

``TestInit`` runs once when the robot enters test mode
``TestPeriodic`` runs while the robot is in test mode 

