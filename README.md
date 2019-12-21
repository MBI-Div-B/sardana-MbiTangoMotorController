# sardana-MbiTangoMotorController
Sardana contoller for standard MBI Tango motor controller

You need to set the Tango device name for each axis of this generic controller by the axis_attribute: Tango_Device

The state and status of the Tango device are direclty mapped as state and status of the sardana motor.
The limit switches are read by the attributes: limit_plus and limit_minus

The Position is read by the Tango attribute: Position
To set the position the same Tango attribute is used.

The Sardana Stop and Abort methods both call the Tango Stop command.

Velocity, Acceleration, and Step_Per_Unit can be directly set.

The Sardana macro %set_pos #motorname #value calles the Tango command: set_position

The Tango commands Homing_Plus and Homing_Minus can be accessed via the Sardana Macro:
%send2ctrl MbiTangoMotorController homing #axis #directrion(0/1)
