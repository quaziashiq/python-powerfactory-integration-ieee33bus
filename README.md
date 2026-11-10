Python–PowerFactory Integration for Deterministic Hosting Capacity Assessment of an IEEE 33-Bus Distribution Network

Author: Quazi Ashiqur Rahman
Tools: DIgSILENT PowerFactory 2024 | Python 3.12 | Jupyter Notebook
Application: Distribution network modelling, automated AC power-flow analysis, and photovoltaic (PV) integration assessment

1. Overview

This repository demonstrates the integration of an external Python environment with DIgSILENT PowerFactory 2024 through the PowerFactory Python API. The implementation is developed using the IEEE 33-bus radial distribution network to demonstrate the application of Python-based automation in distribution system analysis and deterministic hosting capacity (HC) assessment.

The Jupyter Notebook illustrates how Python can interact with a PowerFactory network model, access electrical network components, configure distributed PV generation, execute AC power-flow calculations, retrieve simulation results, and evaluate the impact of PV integration on distribution network operating conditions.

The work demonstrates practical programming and engineering-software integration for power system simulation and analysis.

Repository scope: This notebook presents selected deterministic hosting capacity and Python–PowerFactory integration tasks. It is a demonstration of the computational workflow, rather than the complete probabilistic hosting capacity research framework or a fully operational Digital Twin platform.

2. Objectives

The main objectives of this implementation are to:

Establish communication between an external Python environment and DIgSILENT PowerFactory.

Automate selected power system simulation tasks through the PowerFactory API.

Investigate the impact of PV integration on distribution network voltage profiles and operating conditions.

Assess hosting capacity under specified network operating constraints.

Extract and analyse relevant electrical parameters from simulation results.

Demonstrate how Python programming can support distribution network planning and renewable energy integration studies.

3. Network Model and Simulation Environment

The implementation uses the IEEE 33-bus radial distribution test system, a widely used benchmark network for distribution system analysis.

Parameter

Description

Test system

IEEE 33-bus radial distribution network

Nominal voltage

12.66 kV

Power system simulation software

DIgSILENT PowerFactory 2024

External programming environment

Python 3.12

Integration interface

PowerFactory Python API

Computational environment

Jupyter Notebook

Main application

Deterministic hosting capacity and PV integration assessment

The network model is represented in PowerFactory using standard electrical components, including busbars, distribution lines, loads, external grid connections, transformers, and static generators representing PV units.

4. Demonstrated Python–PowerFactory Integration Capabilities

The notebook demonstrates the following capabilities:

4.1 External Application Connection

Initialise and connect to the PowerFactory application using its Python API.

Activate a PowerFactory project and access the relevant study case.

Retrieve network objects required for the analysis.

4.2 Network Data Access

Access busbars (ElmTerm).

Retrieve distribution lines (ElmLne).

Access loads (ElmLod).

Retrieve transformers (ElmTr2).

Access external grid connections (ElmXnet).

Retrieve static generators (ElmGenstat).

4.3 PV Generation Configuration

Access PV generator operating parameters.

Configure active and reactive power setpoints using PowerFactory attributes such as pgini and qgini.

Investigate network operating conditions under different PV generation levels.

4.4 Automated Power-Flow Analysis

Execute AC load-flow calculations using the PowerFactory load-flow command (ComLdf).

Retrieve bus-voltage magnitudes and line-loss information.

Compare network operating conditions before and after PV integration.

4.5 Network Performance Assessment

Examine bus-wise voltage profiles.

Evaluate the impact of PV generation on network operating conditions.

Analyse active and reactive power losses.

Examine PV generation and external-grid power exchange.

Perform active-power balance checks where the required simulation quantities are available.

5. General Simulation Workflow

The computational workflow follows these principal steps:

Initialise the external Python environment and connect to PowerFactory.

Activate the required PowerFactory project and study case.

Retrieve the relevant distribution network components.

Configure the base operating condition and execute the initial AC load flow.

Extract the base-case network operating parameters.

Configure PV generation according to the selected simulation condition.

Execute the subsequent AC load-flow calculation.

Retrieve the resulting bus voltages, generation, and network losses.

Evaluate the impact of PV integration and assess the relevant hosting capacity constraints.

Restore the original generator settings and network operating condition after the simulation, where implemented.

The notebook provides the implementation details for the demonstrated workflow. Exact execution requirements depend on the PowerFactory project configuration and the attributes available in the selected network model.

6. Software Requirements

The following software and configuration are required:

Microsoft Windows operating system.

DIgSILENT PowerFactory 2024 with a valid installation and licence.

Python 3.12 configured to use the Python API supplied with the PowerFactory installation.

Jupyter Notebook or JupyterLab.

Python packages used in the implementation, including NumPy and Pandas.

Important: The PowerFactory Python API is supplied with the PowerFactory installation. It is not a substitute for the licensed PowerFactory software and should not be treated as an ordinary third-party package installable from PyPI.

7. Configuration and Execution

Before executing the notebook, configure the local PowerFactory environment.

Step 1: Configure the PowerFactory Python API

Verify the Python API directory corresponding to the local PowerFactory installation. The API path and Python version must be compatible with the installed PowerFactory release.

Step 2: Configure the PowerFactory Project

Check the project activation commands in the notebook. The project names and study-case configuration must match the local PowerFactory environment.

Configuration note: The project references in the current implementation include PHC and sgphc in different sections. These references should be checked and made consistent with the intended project before execution.

Step 3: Verify the Network Model

Confirm that:

The IEEE 33-bus network is available in the activated project.

The relevant study case is active.

The load-flow command (ComLdf) is available.

PV generators are represented by the expected PowerFactory object class.

The required generator attributes and result variables are accessible.

Step 4: Execute the Notebook

Open the notebook:

Python_powerfactory integration_Deterministic HC.ipynb

Run the cells in sequence after verifying the environment and project configuration.

Caution: Always back up the PowerFactory project before running automation that modifies generator operating parameters or other network attributes.

8. Scope and Limitations

This repository is intended as a technical demonstration of Python-based automation and PowerFactory integration for distribution network analysis.

The current implementation is dependent on the PowerFactory installation, project configuration, study case, network object names, and available result attributes. Users may need to adapt the configuration and object references to their own PowerFactory models.

The repository does not include the proprietary PowerFactory project file or licence-dependent software components. It should therefore be regarded as a code-level demonstration rather than a fully self-contained, independently executable simulation package.

The notebook represents selected deterministic analysis tasks and should not be interpreted as the complete probabilistic hosting capacity framework, machine-learning surrogate modelling implementation, or operational Digital Twin system.

9. Relevance to Distribution Network Research

Python–PowerFactory integration provides a flexible computational approach for automating distribution network simulations, analysing renewable energy integration, and supporting network planning decisions.

The demonstrated capabilities are relevant to research and engineering applications involving:

Distributed energy resource (DER) integration.

Rooftop solar PV hosting capacity assessment.

Distribution network voltage and thermal constraint analysis.

Automated AC power-flow simulation.

Data-driven distribution network planning.

Smart inverter and advanced distribution system studies.

Future development of digital monitoring, simulation, and Digital Twin applications.

10. Author

Quazi Ashiqur Rahman
Executive Engineer, Dhaka Power Distribution Company Limited (DPDC), Bangladesh.

Research interests include:

Distribution network planning and operation.

Renewable energy and distributed energy resource integration.

Probabilistic hosting capacity assessment.

Smart inverter control and voltage regulation.

Power system modelling and simulation.

Python-based engineering automation and machine learning.

Digitalisation of electricity distribution networks.

GitHub: https://github.com/quaziashiq/python-powerfactory-integration-ieee33bus

11. Disclaimer

This repository is shared for academic, research, and educational purposes. DIgSILENT PowerFactory is proprietary software, and its use is subject to the relevant licensing terms. The IEEE 33-bus network is used as a benchmark for demonstrating power system simulation and analysis techniques.

The author welcomes academic discussion, collaboration, and constructive feedback on Python-based power system simulation and distribution network research.
