NI tools (phoenix tuner, driverstation, robo rio config)
==============

Installing 
----------

https://www.ni.com/en-au/support/downloads/drivers/download.frc-game-tools.html#440024

Using 
-------
The team number at the top of the driver station needs to match the team number on the roborio (this is set when the roborio is configured) 
It should also ideally match the team number on the radio (set when the radio is configured), it should also match the team number in the robot code configur

On the right you have a console, by default it will only errors, however since i'm sure you have no errors this is not incredibly useful. 
To make the console also display printouts you can select the settings button in the top left of the console, select ``+Print``

.. image:: Driverstaion.jpeg
  :width: 700

In the Middle you can see indicator lights for comms, robot code, and joysticks. Comms indicate whether you are connected to your robot, if it's red check your connection. 
Robot code indicates whether you have code on your robot, if it flashes red then goes back to green that means your code has crashed. :(
Joysticks indicate whether or not you have connected joysticks. 

You can see the robot battery in the middle section as well. This should ideally be above 12 V when a new battery is put into the robot, 
if it drops below 11V, switch the battery. 

On the left hand side you can select which mode you would like to enable, this will usually be Teleoperated or sometimes Autonomous. 
Then down the bottom you can choose to enable/disable the robot. **You can disable the robot by pressing the enter key, or you can restart the robot by pressing the space bar** 

When driving the robot, especially in autonomous mode you should always keep a hand over the enter key in case the robot does something *funny*


On the far right, you can select diffent tabs: 

The second one shows communication information + you can restart robot code and the robo rio. This is usually used for diagnostics when something breaks/the robot is unable to connect to the field.

The third section shows the dashboard settings, including changing the team number, practice game timings, dashboard type and any inputted game data. 

The forth section shows inputs (**this is the section you will use the most**)

The fifth section shows more robot information.