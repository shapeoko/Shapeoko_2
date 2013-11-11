# Running Your First Real job!
***
![view of finished coaster]()

### Let's keep a few things in mind:
	1. Smart people, who value their eyesight, always wear safetly glasses.
	2. If you are unsure of what you're doing. Stop doing it. Ask on the forum before ruining your machine.
	3. Have fun. It is, after all, what it's all about. 


You will need the following components to complete this step:
	1. Assembled Shapeoko
	2. Computer with internet access
	3. 
	
You will need the following tools to complete this step in the assembly
	1. 
	2. 
	3. 

***

Getting Started: Your first MakerCAM project!

Step #1: Open makerCAM.com. Zoom out until you can see the origin.

Step #2: Select Insert -> Rounded Rectangle. When the dialog box comes up, input 3.5 for both the length and width. leave the radius as 0.2. Click OK. You now have a rounded rectangle! Move the rounded rectangle so the bottom left corner is on the origin (0,0).

Step #3: Select Insert -> Rounded Rectangle. When the dialog box comes up, input 3.125 for both the length and width. leave the radius as 0.2. Click OK. You now have another rounded rectangle! Move the rounded rectangle so the bottom left corner is slightly inside of the bigger rectangle. Like this ->.

Step #4: Select the pencil tool from the toolbar in the top left corner of the screen. Use it to draw the first letter of your last name. Draw it in block style. It might take a few tries. If you mess up, switch to the pointer tool, select your line and press 'delete' on your keyboard. Once you have a rough shape of your letter, take a step back and have a look. A little rough isn't it? That's OK, it's a start!

Step #5: Take the pointer tool with the circle on the end, and start working your letter into shape. Zoom in, and hover over one of the corners. See the red dot? Now you can click and drag that red dot until your line is straight (or in the shape you want it). If you put that red dot onto another one, it will join the two lines together. Now we're getting somewhere! Once you're happy with the letter, go ahead and center it inside the rectangles.

Step #6: Select your letter with the pointer tool. Once it's selected, the border will turn orange. Now, take a deep breath, we're going to make our first toolpath! Click CAM -> Pocket. Fill in the following values then click OK. Your letter should look like it's filled in with a hatch pattern.
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

Step #7: Select the inside rounded rectangle (the one we made in step #3). Click CAM -> Follow Path Operation. Fill in the following values, then click OK. Your line will look highlighted yellow.
name: trim_engrave
tool diameter: 0.125
target depth: -0.03125
safety height: 0.25
stock surface: 0
step down: 0.03125
feedrate: 30
plunge rate: 10

Step #8: Select the outside rounded rectangle (the one we made in Step #2). Click CAM -> Profile Operation. Fill in the following values, then click OK.
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

Step #9: It's time to generate your g-code! If you check the "view cuts" option in the top right portion of the screen, your toolpaths will be filled with nice colors representing the operations. If everything looks OK, go ahead and click CAM -> calculate all. Nice work.

Step #10: Export Your g-code! Your coaster should look a little goofy right now, with colors and curves representing the toolpaths. That's OK, Imaging those toolpaths as a map for your bit to follow. Once you have calculated all toolpaths, let's go ahead an export the file. Click CAM -> export g-code. A couple of things to remember on this screen.
The order should go:
letter_pocket
trim_engrave
coaster_cutout
As long as that's OK, then click 'all' (will highlight all of your operations), then click "Export Selected Toolpaths". A file dialog box will prompt your for a location to save your file. let's name it 'monogram_coaster.nc' and save it somewhere that you will remember. After the file is exported (it'll only take a split second), go ahead and save the svg file from makerCAM. Click file -> save SVG. Save it somewhere that you will remember.