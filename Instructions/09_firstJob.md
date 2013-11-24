#Your First Job
##Overview
![exploded view of assembly step](http://placehold.it/200x200)  ![image of completed assembly step](http://placehold.it/200x200) ![exploded view of assembly step](http://placehold.it/200x200) ![video?](http://placehold.it/200x200)

Welcome to Your New Life! After completing this step, you'll be a pro! OK, maybe not a pro, but you will be capable of designing a simple part, generating appropriate toolpaths, and cutting said toolpaths on your Shapeoko 2. This is exciting, get ready!


##Find the Origin
Step #1: Open makerCAM.com. Zoom out until you can see the origin.  

![makercam origin](http://placehold.it/400x400)

##Create Rectangle
Select Insert -> Rounded Rectangle. When the dialog box comes up, input 3.5 for both the length and width. leave the radius as 0.2. Click OK. You now have a rounded rectangle! Move the rounded rectangle so the bottom left corner is on the origin (0,0).  

![rounded rectangle](http://placehold.it/400x400)

##Another Rectangle
Select Insert -> Rounded Rectangle. When the dialog box comes up, input 3.125 for both the length and width. leave the radius as 0.2. Click OK. You now have another rounded rectangle! Move the rounded rectangle so the bottom left corner is slightly inside of the bigger rectangle. Like this:

![another rounded rectangle](http://placehold.it/400x400)

##Draw Freehand!
Select the pencil tool from the toolbar in the top left corner of the screen. Use it to draw the first letter of your last name. Draw it in block style. It might take a few tries. If you mess up, switch to the pointer tool, select your line and press 'delete' on your keyboard. Once you have a rough shape of your letter, take a step back and have a look. A little rough isn't it? That's OK, it's a start!

![freehand](http://placehold.it/400x400)

##Prettify Your Freehand
Take the pointer tool with the circle on the end, and start working your letter into shape. Zoom in, and hover over one of the corners. See the red dot? Now you can click and drag that red dot until your line is straight (or in the shape you want it). If you put that red dot onto another one, it will join the two lines together. Now we're getting somewhere! Once you're happy with the letter, go ahead and center it inside the rectangles.

![clean up](http://placehold.it/400x400)

##Engrave Letter
Select your letter with the pointer tool. Once it's selected, the border will turn orange. Now, take a deep breath, we're going to make our first toolpath! Click CAM -> Pocket. Fill in the following values then click OK. Your letter should look like it's filled in with a hatch pattern.

![another rounded rectangle](http://placehold.it/400x200)

	//makercam settings
	name: letter_pocket
	tool diameter: 0.125
	target depth: -0.03125
	safety height: 0.25
	stock surface: 0
	step over: 40
	step down: 0.03125
	roughing clearance: 0
	feedrate: 30
	plunge rate: 10
	direction: counter


##Engrave Border
Select the inside rounded rectangle (the one we made in step #3). Click CAM -> Follow Path Operation. Fill in the following values, then click OK. Your line will look highlighted yellow.

![engrave border](http://placehold.it/400x400)

	name: trim_engrave
	tool diameter: 0.125
	target depth: -0.03125
	safety height: 0.25
	stock surface: 0
	step down: 0.03125
	feedrate: 30
	plunge rate: 10


##Profile!
Select the outside rounded rectangle (the one we made in Step #2). Click CAM -> Profile Operation. Fill in the following values, then click OK.

![engrave border](http://placehold.it/400x400)


	name: coaster_cut_out
	tool diameter: 0.125
	target depth: -0.26
	inside/outside: outside
	safety height: 0.25
	stock surface: 0
	step down: 0.03125
	roughing clearance: 0
	feedrate: 30
	plunge rate: 10
	direction: clockwise


##Generate G-Code

![calculate toolpaths](http://placehold.it/400x400)

It's time to generate your g-code! If you check the "view cuts" option in the top right portion of the screen, your toolpaths will be filled with nice colors representing the operations. If everything looks OK, go ahead and click CAM -> calculate all. Nice work.


##Export Code

![export screen](http://placehold.it/400x400)

Export Your g-code! Your coaster should look a little goofy right now, with colors and curves representing the toolpaths. That's OK, Imaging those toolpaths as a map for your bit to follow. Once you have calculated all toolpaths, let's go ahead an export the file. Click CAM -> export g-code. A couple of things to remember on this screen.


**The order should go:**
1. letter_pocket
2. trim_engrave
3. coaster_cutout

As long as that's OK, then click 'all' ( which will highlight all of your operations), then click "Export Selected Toolpaths".
![export paths](http://placehold.it/400x400)

A file dialog box will prompt your for a location to save your file. let's name it 'monogram_coaster.nc' and save it somewhere that you will remember.
After the file is exported (it'll only take a split second), go ahead and save the svg file from makerCAM. Click file -> save SVG. Save it somewhere that you will remember.

This is the final test of hooking. This works because of absolute paths.
