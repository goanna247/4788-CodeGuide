Your Subsystem!
----------------

So your creating your subsystem, here is a quick guide with some suggestions about the best way of doing things. However 
keep in mind programming is creative, there are many ways to do things, that might possibly be better/more effecient/you might understand it better 

The first thing to do when creating a subsystem for the actual robot is setting up it's structure, create it's struct in robotmap, create the files you are gonna need starting with your subsystem.h eg. ``Intake.h``. 

Inside your subsystem.h you need to create a class for it! You will also need a statemachine (a tutorial can be found in the statemachine tab)

eg. 
.. code-block:: cpp

  class Subsystem : public behaviour::HasBehaviour {
    void OnUpdate()
  }

