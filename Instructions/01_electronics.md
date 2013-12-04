# Testing Electronics
## Overview
![Wiring diagram](http://placehold.it/200x200)  ![Arduino, gShield, wiring, stepper motors, lit](tPictures/so_e_arduino_wired_li_2.jpg) ![image of required components](tPictures/so_electronics_parts_2.jpg) ![Tools](tPictures/so_e_tools_2.jpg)

Before we get all crazy bolting our new machine together, let's give our electronics a test run. It's frustrating to have the machine fully assembled, only to find there is a problem with your electronics that may require disassembly! Let's cut that off at the pass and give everything a thorough checking first.

## Requirements

![image of required components](tPictures/so_electronics_parts_4.jpg) 

* **Arduino with Grbl firmware** (contains an AVR processor, USB connector and I/O pins)
* (Arduino) **gShield** (formerly GrblShield, takes the signals Grbl generates and drives the steppers. Small pots are used to adjust)
* **Stepper motors** x 4pcs
* **Power Supply** with wall plug
* **Barrel Connector** (for connecting the power supply to the gShield)
* Computer with a **Grbl Communication/Control program** installed
* **USB Cable** (A to B)
* Patience (just a little bit)

## Tools

![Tools](tPictures/so_e_tools_4.jpg)

* Wire stripper (for 18–20 gauge wire)
* 3/32" (medium size jeweler's) flat blade screwdriver
* 1/8" (fine tip) flat blade screwdriver 
* Wire cutters
* #2 Phillips or 9/32" flat blade screwdriver
* (optional and not shown) Multimeter for testing continuity

The terminal blocks use a combination screw which will accept either a Phillips or flat blade screwdriver. (There is a custom driver which incorporates both and makes a compleat connection with the screw head, but that degree of torque is not needed in this application.)

##Connect Arduino
Now that we have everything gathered up, you should find yourself with a setup similar to this:

![image of required components](tPictures/so_electronics_parts_4.jpg)  

First thing that we do is plug our Arduino into the computer.

![Arduino plugged into USB cable](tPictures/so_e_arduino_lit_4.jpg)

Remember, the big end of the cable goes into the Arduino. 

Chances are, the Arduino will be recognized by your computer. 
If not, download the appropriate drivers/software for your platform (do not proceed beyond Step #4 or you will erase Grbl):

* [Mac OS X](http://arduino.cc/en/Guide/MacOSX#toc2)
* [Windows](http://arduino.cc/en/Guide/Windows#toc2)
* [Linux]([http://playground.arduino.cc/Learning/Linux)

##Communication / Control Program

Once the Arduino is recognized by your computer system, install a Communication / Control Program.

###UGS
![UGS](http://placehold.it/400x400)  
*(universal gcode sender by will winder)*

If Java isn't an option for your machine there are other [Communication/Control programs](http://www.shapeoko.com/wiki/index.php/Communication_/_Control).

##Hook Stuff Up##

![Arduino and gShield](tPictures/so_e_arduino_gshield_2.jpg) ![Arduino and gShield on edge](tPictures/so_e_arduino_gshield_oe_2.jpg) ![Arduino and gShield assembled](tPictures/so_e_arduino_gshield_aa_2.jpg)

The first step is to plug the Arduino into the gShield. The Arduino will run Grbl, while the gShield will be connected to the stepper motors and will control them. Be careful of the electronics, not to bend any pins, or to allow static electricity to damage them.

You will need to connect the gShield to the terminal blocks (using the 4 conductor grey wire) and the terminal blocks to the motors. If you have very long wires coming off of the stepper motors you will have the option of choosing where the terminal blocks are placed, either on the gantry, or connected to the electronics. If the wires are short, then the terminal blocks will need to be attached to the gantry. On the gantry minimizes the wear and tear on the motor leads, limiting it to the 4 conductor grey wire (this is easily sourced at any home improvement store), while hiding the terminal blocks away provides for a neater appearance.

![Stepper motor, terminal block, screwdriver](tPictures/so_e_stepper_motor_tb_2.jpg) ![Stripped wires](tPictures/so_e_wire_stripped_2.jpg)
![Stepper motor connected to terminal block, connected to grey wire](tPictures/so_e_steppermotor_tb_wir_2.jpg) ![Wiring Y-Axis motors to terminal block](tPictures/so_e_steppermotor_tb_y_2.jpg) ![Stepper motors and terminal blocks wired up](tPictures/so_e_steppermotors_wi_a_2.jpg) ![Open connector on gShield](tPictures/so_e_arduino_open_2.jpg) ![Arduino, gShield, terminal blocks, wiring, stepper motors](tPictures/so_e_arduino_usb_2.jpg) ![image of required components](tPictures/so_e_arduino_wired_lit_2.jpg)


Start by cutting the grey wire to length (either equal thirds, or some proportion which takes into account the wire for the Y-axis having a slightly shorter run than the X- and Z-axes.

Next, strip all of the wire ends. The ends which will attach to the terminal block should be approximately 3/8" so as to be twisted into a hook so as to wrap around the terminal block screws. The other end of the grey wire should be stripped approximately 1/4" of an inch so as to fit into the gShield. Be careful of stripping too much and leaving wire unnecessarily exposed which could create the possibility of a short.

![Stripped wire](tPictures/so_e_wire_stripped_2.jpg)

Next, loosen up all the screws on one terminal block, then begin making connections by twisting the wire ends into hooks, hooking them onto the screws oriented so that the turning of the screw will tighten them and tighten the wire.

Make all connections in the same colour order. Shown is:

* Red
* Blue/White (Please match the other 3 colours and pair this odd twain)
* Green
* Black

![Stepper motor connected to terminal block, connected to grey wire](tPictures/so_e_steppermotor_tb_wired_.jpg)

Since the ShapeOko 2 uses two motors on the Y-Axis and the gShield only has 3 stepper drivers, it is necessary to wire the two motors to one terminal block as shown below. Note that it is necessary to reverse one pair of wires so that the motors will run in opposite directions when placed on the gantry in opposite orientations.

![Wiring Y-Axis motors to terminal block](tPictures/so_e_steppermotor_tb_y_4.jpg)

(red and blue to make purple was selected)

Carefully make each connection. Be careful not to lose any screws. If necessary, trim wires and re-strip so as to achieve a good connection.

![image of required components](tPictures/so_e_steppermotors_wired_4.jpg)

Next, connect the grey wires from the terminal blocks to the stepper motors. Make all of the connection initially in the same order. Later, when configuring the machine, it may be necessary to swap wires around so as to achieve the desired rotational direction.

![image of required components](tPictures/so_e_steppermotors_ar_4.jpg)

Please note the gShield takes two different sizes of screwdriver. 1/8" for the screws in the blue power connector, 3/32" for the screws in the green stepper motor connectors.

The green stepper motor connectors should be unscrewed so as to open them up as the right-most connector is below.

![Open connector on gShield](tPictures/so_e_arduino_open_4.jpg)

Connect the grey wires from the stepper motors. Lastly one must connect the power. Note that each green block represents one axis. Be certain to connect the dual-motor Y-Axis to the correct block.

Once completed, all wires will be connected and none will be loose. It is important that the wires be connected securely since the various parts will be in motion, and applying power to a stepper driver which is not connected to a motor may damage the driver.

If you have a multimeter you may wish to test the connections for continuity.

###Power###

_Be careful with the power supply, and don't work on power wires when the power supply is plugged in._

**Caution:** Please note that the 12V power supply has a connector which matches the Arduino's 5V power supply connection — it must not be plugged into said connector. The Arduino is able to draw its power over the USB connection, so the power connector on the Arduino is not used.

First, strip the power lead, it may also be necessary to split the lead at the end so as to allow it to neatly connect to the power connector on the gShield.

![Stripped lead for barrel connector](tPictures/so_e_powerwire_stripp_2.jpg)

Connect it to the Arduino. There are two leads, one a solid black wire, the other black w/ a white stripe. 

* black == (-)
* black/white == (+) (or red)

Please connect each lead to the appropriate side of the gShield's blue power connector.

![Power connections](tPictures/so_e_arduino_usb_4.jpg)

Plug the barrel connector into the matching connector from the power supply, plug it into a grounded outlet. Your gShield should light up blue and be ready for operation.

![image of required components](tPictures/so_e_arduino_usb_lit_4.jpg)



##Testing##

Attaching tape to the motor shafts makes it easier to see the rotation.

Load up a Communication / Control program and use its jog functionality to test each Axis.

###Go For a Spin###

Z-Axis

###Another Spin###

X-Axis

###And a Final Spin###

Y-Axis — make certain that the two motors for the Y-axis are rotating in opposite directions.
