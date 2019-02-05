# BikeEnvironment
This is a simulation environment for a bicycle and controller created by [Michael Marne](https://github.com/Kalveo) and [Ivar Wikenstedt](https://github.com/Wikenvar). 

There is a 3D visualization tool that visualizes the simulationdata from the simulinkfile created by Michael.

The plan is to continue working on a few features in the future, however this is currently not a prioritzed project.

You are free to use this environment and edit it for simulation. If you do use this, please add an acknowledgement to Michael and Ivar in your report!

### Using the environment

Model:

	The simulink model contains NO OPTIONS within the simulink file.
	All options and parameters are contained in the following files located in the directory "./Setup":
		ModelSettings.m
		ModelParams.m
		ModelStateSpace.m
		ModelEKF.m
		ModelPosition.m
		ModelController.m
		ModelObserver.m
		
In order to run a simulation:

    Run the script "RunEnvironment.m"

NOTE:
    
    The simulink model was made in Matlab 2018b, thus older versions can not open it.
    To change which simulink file to run, edit "./Setup/RunFullSimulation.m"
		
3D visualization:

    A 3D model of the bike can visualize a simulation. 
    This can be done automatically after a simulation run through "RunEnvironment.m" 
    by pressing "yes" when prompted.
	
To manually run the 3D model:

    Make sure "bike3D_V2.m" is in MATLABs path	
	Then:
		Initialize the 3D bike object:
			b = bike3D_V2();
		Supply the data:
			b.fromData(sim_true_state);
				
	sim_true_state is a variable pointing to the data output from the simulation, located: 
	simOut.sim_true_state in the workspace after a simulation.
				
		b.fromStateFile(fileName);
				
	fileName is the location of the file containing the true state. 
	This file is located in "saved_simulation_results\simulation#" if the results of a simulation were saved 
	(saving is automatic if "yes" is selected when prompted). 
	The file name is "sim_true_state.mat".
