# Behavioral and Local Planner in Urban Environment

In this project we will be implementing many of the behavioral and local planning concepts discussed in Course 4. The goal of this project will be to have a functional motion planning stack that can avoid both static and dynamic obstacles while tracking the center line of a lane, while also handling stop signs. To accomplish this, you will have to implement behavioral planning logic, as well as static collision checking, path selection, and velocity profile generation.

![Planner simulation in CARLA](img/planner_sim.gif)

## Download this repository
Download the repository and unpack into the  subfolder folder "PythonClient" inside the "CarlaSimulator" (root) folder. This will create a subfolder "Course4FinalProject" under "PythonClient" which contains the assignment files.

It is very important to have the contents of this repository be under the folder "PythonClient\Course4FinalProject" (for Windows) or "PythonClient/Course4FinalProject" (for Ubuntu). Installing it into another directory might cause runtime issues.

After successfully downloading CARLA and this repository, we are ready to run the planner and visualize the results.

## Running the CARLA simulator
In one terminal, start the CARLA simulator at a 30hz fixed time-step:

Ubuntu:

'$ ./CarlaUE4.sh /Game/Maps/Course4 -windowed -carla-server -benchmark -fps=50'

Note that both the ResX=<pixel_width> and ResY=<pixel_height> arguments can used to create a fixed size window, if you find the simulation to run too slow. See the CARLA installation guide for more details on how to use the arguments.

## Running the Python client (and controller)
In another terminal, change the directory to go into the "Course4FinalProject" folder, under the "PythonClient" folder.

Run your controller, execute the following command while CARLA is open:

Ubuntu  (use alternative python commands if the command below does not work, as described in the CARLA install guide):
'$ python3 module_7.py'

The simulator will begin to run if the module_7.py client connects to the server properly. It will open two new feedback windows (unless live_plotting is disabled - see the changing the live plotter refresh rate section below for more details), one of which shows the top-down trajectory and the other which shows the controls feedback.

## Changing the live plotter refresh rate
If the simulation runs slowly, you can try increasing the period at which the live plotter refreshes the plots, or disabling the live plotting altogether. Disabling the live plotting or changing its refresh rate does not affect the plot outputs at the end of the simulation. 

To do this, edit the options.cfg file found in the "Course1FinalProject" folder for the relevant parameters. The following table below explains each option:

| Parameter  | Description  | Value |
| -------- | ----------- | ------------ |
| live_plotting | Enable or disable live plotting. | true/false |
| live_plotting_period | Period (in seconds) which the live plot will refresh on screen. Set to "0" for an update every simulation timestep. | [seconds] |
