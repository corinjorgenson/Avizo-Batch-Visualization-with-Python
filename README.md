# Avizo-Batch-Visualization-with-Python
Avizo Batch Visualization with Python
NOTE: This is a work in progress. I will likely add more codes as I learn how to do more things

Avizo has a python console which can be used for ease of batch processes. Avizo's documentation for utilizing this feature is a bit spare so here are some basic information that I found through trial and error and asking Avizo Support. I recommend starting with Avizo's YouTube video on using the Python console https://www.youtube.com/watch?v=tUlZFJj-aYs. The Avizo Help Docs (access through Avizo's Help dropdown), while slightly buried, has some good descriptions. Finally, there is an API that can be accessed via Python> Python Programmers Reference.

This repo is composed of several scripts:
1. The basics of how to make and manipulate an orthoslice
2. How to save an orthoslice (via snapshot and via the viewer)
3. How to add a scalebar to your othoslices
4. How to make volume renderings, manipulate them, and save them
5. How to use the script in 4 to make a loop
6. How to run some basic modules to seperate isolated bubbles (uses filter by measure and arithemtic) 

Also here are some basics/tips of how to run the Python console.

- You run python in the Main Python Console which you can access by pressing the button on the bottom right corner

- The options of what you can do with different commands you can usually access by pressing tab in the console and you should get some popup menus

- You can interact with different parts of the Avizo windows with hx_OPTION. For the project window it is hx_project. For the viewer window it is hx_viewer_manager. Etc. 

- Modules get loaded via hx_project.create('YOUR MODULE'). To find the AvizoPy name of the module you want search for it like you would in Avizo and look for the Type name (e..g Ortho Slice == 'HxOrthoSlice')

- Modules, once loaded works with "ports" which are the options you see in the properties window. There might be other ports you can use and you can find these by typing print(thingyouwant.portnames) (e.g. ortho.portnames)). 

- Modules get connected via module.ports.data.connect(hx_project.get(YOUR DATA)). (e.g. volrendset.ports.data.connect(hx_project.get(name))).
  
- To get things to populate in the viewer you usually need to run XYZ.fire() (e.f. ortho.fire()). OR module.excecute() 

- If there is an option to do something in the module that you cannot get to do via module.ports.etc it is probably something you want to manipulate via the tcl console. See script 3 for how to do this with scalebars.

- All else fails there is always help() to see some documentation


