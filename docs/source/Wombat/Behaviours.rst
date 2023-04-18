Behaviours
===========


Behaviours are Wombat's innovative solution to scheduling and organising complex robot code, allowing for increased modularity past regular functions. 


Behaviours are how you use the robot code, it can be thought of like the controller and the subsystem files the actual system. 


A system should only be controlled by 1 Behaviour at a time, a behaviour cannot call a behaviour (potench feature) 




Regular Robot Code 
====================

The first step of creating robot code using the behaviour system is creating the subsystem program, eg. Gripper.cpp and Gripper.h. When creating the class extend the class to also have the behaviour::HasBehaviour class which can be found in the #include "behaviour/HasBehaviour.h" file. 
We use statemachines within this file, more information on this can be found in the statemachine tab. 

You then create behaviours which control this system. 
Any behaviour needs to be created by extending the class behaviour::Behaviour found in the #include "behaviour/Behaviour.h"

There are a couple key functions you can use within a behaviour: 

**OnStart()** Runs when the behaviour is initially started
**OnTick()** Called periodically while thhe behaviour is running, where the most logic goes
**OnStop()** Called when the behaviour is finished 


**SetPeriod(units::time::second_t period)**
**GetName()** 
**GetPeriod()**
**GetRunTime()**
**GetBehaviourState()**
**GetRunTime()**

**Interrupt()**
**SetDone()**
**IsRunning()**
**IsFinished()**

**Controls()** Is required inside the constructor to define which subsystem the behaviour is controlling, if you doing have this you're system just isn't gonna work, but it also wont throw an error. If your system isnt working this is the first thing to check

.. code-block:: cpp
  :caption: regular behaviour example .h file 

  #pragma once 

  #include "behaviour/Behaviour.h"
  #include "Gripper.h" //this is the header file of the system the behaviour is controlling 

  class GripperBehaviour : public behaviour::Behaviour {
   public: 
    GripperBehaviour(Gripper *gripper, frc::XboxController &codriver); //most regular behaviours that run during teleop will also include the controller, if your system does not require driver control disregard

    void OnStart() override;
    void OnTick(units::second_t dt) override;
  
   private: 
    Gripper *gripper; //system the behaviour is controlling
    frc::XboxController &_codriver;
  };

.. code-block:: cpp
  :caption: regular behaviour example .cpp file 

  #include "GripperBehaviour.h" //wherever your behaviour header file 

  GripperBehaviour::GripperBehaviour(Gripper *gripper, frc::XboxController &codriver)
    : gripper(gripper), _codriver(codriver) {
    Controls(gripper);
  }

  void GripperBehaviour::OnStart() {
    //whatever you want the system to do when the behaviour starts
  }

  void GripperBehaviour::OnTick(units::second_t dt) {
    //runs every tick whilst the behaviour is running

    if (_codriver.GetRightTriggerAxis > deadzone) {
      gripper->SetIntaking(); //calling functions from the subsystem
    else {
      gripper->SetIdle();
    }
  }


Autonomous
============

The Behaviour system is especially useful when creating autonomous code, allowing for almost drag and drop style simplicity. 

To make a string of behaviour's you can do the following: 

.. code-block:: cpp
  :caption: autonomous behaviour system 

  std::shared_ptr<Behaviour> AutoName(Drivebase drivebase, Armavator *armavator){ //these are the subsystems which you are passing into the behaviour
    return
      make<ArmavatorGoToAutoSetpoint>(armavator, 0.9_m, -25_deg)->WithTimeout(2_s)
      << make<DrivebasePoseBehaviour>(drivebase.swerve, frc::Pose2d{0.3_m, 0_m, 0_deg})->Until(make<OtherBehaviour>())
      << make<WaitTime>(20_s); //last behaviour called needs a semi-colon
  }

**->WithTimeout(x_s)** You can add a timeout to a behaviour, if the behaviour ends before the time then it is disregarded, if the timer finishes first then the behaviour ends

**Parrallel Execution** 
By using '&' 2 behaviours will run at the same time, until both are complete 
By using '|' 2 behaviours will run at the same time, until either one is complete. 

you can also wait until a specific behaviour is complete by using the Until function: 


**Waiting** 
the behaviour <WaitTime>(x_s) allows for an easy delay in a behaviour chain. 

Some weirder/ more untested functions 
========================================

Tick()

**->SetPeriod(x_ms)** You can also tell a behaviour to run at a different speed, this is not used often. 
