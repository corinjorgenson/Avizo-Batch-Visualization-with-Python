# Avizo-Batch-Visualization-with-Python
Avizo Batch Visualization with Python
NOTE: This is a work in progress. I will likely add more codes as I learn how to do more things

Avizo has a python console which can be used for ease of batch processes.

Avizo's documentation for utilizing this feature is a bit spare so here are some basic information that I found through trial and error. I recommend starting with Avizo's Youtube video on using the Python console https://www.youtube.com/watch?v=tUlZFJj-aYs. The Avizo Help Docs (access through Avizo's Help dropdown), while slightly buried, has some good descriptions.

Here is some basics/tips of how to run the Python console. Otherwise in this repo you'll find some basics codes for taking and saving images (numbered in increasing complexity).

- You run python in the Main Python Console (don't try run in the Tcl concole lol) which you can access by pressing the button on the bottomright corner

- The options of what you can do with different commands you can access usually by pressing tab in the console and you should get some popup menus

- You can intreact with differnt parts of the Avizo windows with hx_OPTION. For the project window it is hx_project. For the viewer window it is hx_viewer_manager. Etc. 

- Modules get loaded via hx_project.create('YOUR MODULE'). To find the AvizoPy name of the module you want search for it like you would in Avizo and look for the Type name (e..g Ortho Slice == 'HxOrthoSlice')

- Modules, once loaded works with "ports" which are the options you see in the properties window. There might be other ports you can use and you can fidn these by typeing print(thingyouwant.portnames) (e.g. ortho.portnames)). 

- Modules get connected via module.ports.data.connect(hx_project.get(YOUR DATA)). (e.g. volrendset.ports.data.connect(hx_project.get(name))). 
- To get things to populate in the viewer you usually need to run XYZ.fire() (e.f. ortho.fire()). 

- All else fails there is always help() to see some documentation

