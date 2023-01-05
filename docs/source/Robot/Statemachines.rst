State machines
---------------

A subsystem will have a number of states it can be in depending on the system, and your code. 
You create the states by creating an enum class: 


.. code-block:: cpp
  :caption: enum example 
  
  enum class MagStates {
    kEmpty,
    kTransfering
    kOne,
    kTwo,
    kEject,
    kManual 
  };


For this example we had a magazene which could store 2 balls and so these states were needed. 

You will need to create an instance of this enum in the susbystem class

``MagStates _state{ MagStates::kEmpty};``
This makes the default state kEmpty

You should then use a switch case to manage what happens in each of these states. 

.. code-block:: cpp
  switch(_state) {
    case: MagStates::kEmpty
      //here we checked the sensors to check if it was still empty, if a ball was sensed then it moved the state to either One, Transfering or Two
      break;
    case: MagStates::kTransfering:
      //here we moved the ball from the front of the mag to the back, next to the shooter
      break;
    case MagStates::kOne:
      //Set the index motor voltage to 0 and check sensors 
      break;
    case MagStates::kTwo:
      //check sensors, set intake + index motors to 0, and set the intake state to deployed (we couldn't have the intake up with 2 balls)
      break;
    case MagStates::kEject:
      //set the index motor to eject a ball from the mag
      break;
    case MagStates::kManual:
      //manual control of the index motor just in case a sensor broke
      break;
  };


