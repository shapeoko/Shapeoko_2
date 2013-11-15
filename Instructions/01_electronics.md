# Testing your Electronics
***
![above view of electronics laid out](http://placehold.it/400x400)

### Let's keep a few things in mind:
1. If you unplug a stepper motor from the controller while it's energized (plugged in), you may very well blow up your controller. 
2. Being shocked by electricity is no fun.
3. Being burned by electricity is no fun either.
4. Smart people, who value their eyesight, always wear safetly glasses.
5. If you are unsure of what you're doing. Stop doing it. Ask on the forum before ruining your setup.
6. Have fun. It is, after all, what it's all about. 


###You will need the following components to complete this step:
1. Arduino [preloaded with latest grbl](12_softwaretroubleshooting.md)
2. grblShield
3. Stepper motors (4)
4. Power Supply with wall plug
5. Barrell Connector
6. Small screwdriver
7. Patience (just a little bit)
8. Computer with USB
9. USB Cable (A to B)
10. [Universal GCode Sender installed on your computer](12_softwaretroubleshooting.md)


### Overview
Before we get all crazy bolting our parts together, we will give our electronics a test run. It's frustrating to have the machine fully assembled, only to find there is a problem with your electronics that may require dis-assembly! Let' cut that off at the pass and give everythign a thorough checking first.

Now that we have everything gathered up, you should find yourself with a setup similar to this:

![insert picture of kerning](http://placehold.it/400x400)

If that's true, great! If it's not true, then either make your setup look like the one shown in the picture, or be prepared not to complain when you can't find something. Because it'll be your own fault.

OK, here we go. Let's get talking to the arduino.

1. First thing that we do is plug our arduino into the computer. Remember, the big end of hte cable goes into the arduino. The flat end of the cable goes into your USB port. There are lots of things that could go wrong here (like your computer not recognizing the board, you attempting to plug the cord in upside down, or some other very boring, silly thing). But, chances are the arduino will be recognized by your computer and we can move on to step 2.  [Click here to resolve any arduino issues:](10_arduinotroubleshooting.md)

2. Open Universal gcode sender.
	####how do I open UGS?
	* For windows: Find the folder that you unzipped the file to. And then find startugcs.bat and double click it.
	* For mac: goto your download folder and click UGS
	* For Linux: find the folder where you downloaded UGS, then run: sudo ./startugs.sh. (you may need to 'sudo chmod +x startugs.sh' before attempting to execute the script)


3. Once UGS is open, click the refresh button (two arrows chasing each other in a circle) located towards the top left of the window. This will refresh your choices of serial ports. Now go ahead an select your serial port and click 'connect'. 
	- [no serial ports found error?](10_arduinotroubleshooting.md)
	- [which serial port do I chose?](10_arduinotroubleshooting.md)

	![Universal GCode Sender main screen](http://placehold.it/400x400)

4. If all goes well (went well) you should we should now be able to talk to the arduino through UGS. Let's send a couple of test commands and see if we get a response. 

5. close the connection in UGS, shut down the window, and unplug the big end of the usb cable from your arduino.
***

### It's time to hookup some stuff. 

We have established that your arduino connects to your computer and that you can issue it commands. We have also established that if your motors are not connected to the arduino, then issuing commands doesn't really do anythign at all. So let's go ahead and get everythign hooked up. 

Place the grblShield on your arduino. If you can't figure it out, take a look at this picture for reference:

![insert picture of gshield being placed onto arduino](http://placehold.it/400x400)

Now connect your stepper motors. Connecting the motors is easy, just do this

![black green red blue](http://placehold.it/400x400)

If you're looking at your controller wondering why there are only 3 terminals and 4 steppers motors. We'll get to that later. (_spoiler alert: we are sharing one of them!_)

Let's hookup the power now and get these motors spinning. *Polarity is important*. If you connect the power backwards, there is a good chance your controller will get fried. And if that happens, there is a good chance you might cry. 

Your power should get hooked up like this:

![closeup of power connection](http://placehold.it/400x400)

OK. All set? 

1. Open UGS again
2. Refresh your ports
3. Select your port and click connect
4. Now you should hear a click and a whoooosh!
5. Click 'Machine Control' in UGS
6. Type G0 X10, click go. One of your motors should move! Hoooray for arduino.
7. Type G0 Y10, click go. Another One of your motors should move! Hooray for stepper motors!
8. Type G0 Z10, click go. The other motor that hasnt' moved yet should move! Hooray for you.
9. It's time to assemble the machine. Get your game face ready, it's go time!
10. If  your motors didn't turn, or there was as problem, please don't cry. Check [this page](steppertroubleshooting.md) for some troubleshooting tips/tricks. 
