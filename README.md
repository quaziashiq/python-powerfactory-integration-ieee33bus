Python–PowerFactory Integration for IEEE 33-Bus Distribution Network
Author: Quazi Ashiqur Rahman
Software: DIgSILENT PowerFactory 2024, Python 3.12
Application: Automated power-flow analysis and PV integration assessment
Overview
This repository demonstrates integration of an external Python environment with DIgSILENT PowerFactory 2024 through the PowerFactory Python API. The script was developed in support of distribution-network analysis using the IEEE 33-bus radial distribution system.

The current implementation demonstrates how Python can interact with a PowerFactory project, access network elements, modify PV generator operating parameters, execute AC load-flow calculations, retrieve bus-voltage and line-loss information, compare operating conditions, and check active-power balance.

This is a focused demonstration of selected PowerFactory automation tasks, not the complete probabilistic hosting-capacity (PHC) research framework.
Demonstrated capabilities
- Connect to PowerFactory 2024 using its external Python API.
- Activate a PowerFactory project and access its active study case.
- Retrieve terminals (ElmTerm), lines (ElmLne), loads (ElmLod), transformers (ElmTr2), external grids (ElmXnet), and static generators (ElmGenstat).
- Read and modify PV active- and reactive-power setpoints using pgini and qgini.
- Execute AC load-flow calculations using the ComLdf command.
- Extract bus-voltage magnitudes and line active/reactive losses.
- Compare base-case and PV-integration operating conditions.
- Map PV injections to their connected buses.
- Calculate external-grid infeed and verify active-power balance.
- Store and restore PV operating settings following a simulation.
Demonstration workflow
1. Initialise the PowerFactory application through the Python API.
2. Activate the relevant distribution-network project and study case.
3. Retrieve the network elements required for the analysis.
4. Save the original PV generator operating settings.
5. Set PV active and reactive power to zero and execute the base-case load flow.
6. Record base-case bus voltages, loads, and feeder losses.
7. Apply a specified PV generation level (the current example uses 50 kW per PV unit) and execute a second load flow.
8. Extract post-integration voltages, PV injections, and feeder losses.
9. Compare bus-wise voltage changes and calculate system-level power balance.
10. Restore the original PV settings and rerun the load flow.
Software requirements
- Windows operating system.
- DIgSILENT PowerFactory 2024.
- Python 3.12 configured to use the Python API supplied with the PowerFactory installation.
- Python packages used by the script: NumPy and Pandas.
The PowerFactory Python API is supplied with the PowerFactory installation. It should not be installed from PyPI as a substitute for the licensed installation's API.
Configuration before execution
The current script contains installation- and project-specific settings. Before running it on another computer or PowerFactory project:
1. Verify the PowerFactory Python API installation path.
2. Verify the PowerFactory project name. The current source contains both PHC and sgphc in different sections; make these consistent with the project actually used.
3. Confirm that the active study case contains a load-flow command (ComLdf).
4. Confirm that the PV generators are represented by the expected PowerFactory class (ElmGenstat).
5. Verify that the selected PV objects, connection attributes, and units match the local model.
6. Confirm that the relevant result attributes (for example, m:u, m:Ploss, and m:Qloss) are available for the model and calculation configuration.
Run the script only after checking the project configuration and backing up the model.
