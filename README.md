This code is for the Aerodynamic subsystem optimization
Main code: Aviary, OpenMDAO
Extra CFD solver: FlightStream

Tech setup for this version:
Please follow the order of the steps listed.
Step 1: Install the OpenVSO API. This will create a environment (default env name: vsppytools), and you need a version with a Python version higher than 3.9.
Step 2: Active env vsppytools, then install pyFlightscript, make sure you have FlighStream GUI installed and working.
Step 3: Colone env vsppytools with a new name (you can pick one you want, for example: py_OFA) in case of package conflicts.
Step 4: Active emv py_OFA, install Aviary, pyoptsparse, cyipopt. (There may be some problems due to package conflicts; Mamba installation is recommended.) Command listed below:
        conda install -c conda-forge mamba
        mamba install -c conda-forge pyoptsparse
        mamba install -c conda-forge cyipopt
Step 5: Check all the packages by typing the following command one by one: pip show openvsp, pip show pyFlightscript, pip show aviary, pip show openMADAO, pip show pyoptsparse, pip show                cyipopt.

Workflow one: Use FlightStream to generate aero_polar and load back. See Polar_FS_Comp folder.
1. Save these files to your Aviray file in a suitable place. (Eg: C/User/Aviary/Subsystem/Aerodynamics/FlightStream_based)
2. Update several file paths in GeometryCreator.py, FSpolarAeroComp.py, geo_oas_opt_FSpolar.py
3. Run GeometryCreator.py first to generate a CAD model for FLightStream.
4. Run FSpolarAeroComp.py to generate a high-fidelity aerodynamics polar.
5. Run FSpolarAeroComp.py, which is already combined with Geometry Optimization.

Workflow two: Use FlightStream as a external aerodynamic solver and combine it into a optimization loop. See External_FS_Comp folder.
