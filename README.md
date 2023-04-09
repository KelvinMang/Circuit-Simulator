# Small-Signal AC Analysis Simulation Software: Year 1 End-of-Year Project

## Table of Contents
1. [Overview](#overview)
2. [Features](#features)
   - [Parse the Netlist File](#parse-the-netlist-file)
   - [Set Up the Simulation](#set-up-the-simulation)
   - [Construct and Solve the Conductance Matrix](#construct-and-solve-the-conductance-matrix)
3. [Usage](#usage)
4. [Documentation](#documentation)
5. [License](#license)

<a name="overview"></a>
## Overview

This repository contains a software package for performing small-signal AC analysis simulations of electrical circuits, similar to LTspice. Developed as part of a Year 1 end-of-year project, this software includes features such as parsing the netlist file, setting up the simulation, and constructing/solving the conductance matrix.

For more details, please refer to the project report:
[View the PDF document](Circuit_Simulator_Report.pdf)

<a name="features"></a>
## Features

The main components of this system are:

<a name="parse-the-netlist-file"></a>
### Parse the Netlist File

The netlist is specified in a file using a simplified SPICE format. The software reads the file, converts the circuit to its small-signal equivalent, and stores it in an appropriate data structure.

<a name="set-up-the-simulation"></a>
### Set Up the Simulation

The AC analysis is performed by calculating the transfer function of the linearized (small-signal equivalent) circuit over a specified frequency range. The circuit must have an input defined by a voltage or current source, and a designated output node. Reactive components are substituted with a complex impedance based on their value and the frequency step. Non-linear components are replaced with their small-signal equivalent circuits, while non-dependent sources are replaced by open or short circuits.

<a name="construct-and-solve-the-conductance-matrix"></a>
### Construct and Solve the Conductance Matrix

Nodal analysis is used to analyze the circuit by writing an equation for each node that satisfies Kirchoff's current law. These equations are then solved simultaneously to determine the unknown node voltages. This system of linear equations can be systematically solved by writing them in matrix form and solving for the vector of unknowns.

<a name="usage"></a>
## Usage and Example

To test whether the nodal analysis was working correctly with the conductance matrix method. We tried a very simple circuit that could be solved by hand as well to compare answers.

![Screenshot 2023-04-09 at 7 25 59 PM](https://user-images.githubusercontent.com/42444869/230790059-2592cd20-104f-40aa-8875-53cf8e8cd20c.png)


This is the circuit that we drew to test the conductance matrix. We then converted it into SPICE format according to the nodes in the drawing.

![Screenshot 2023-04-09 at 7 26 23 PM](https://user-images.githubusercontent.com/42444869/230790071-173f3deb-217c-4727-bf49-03a0d0cf6945.png)

Also, the output shows the voltage at node 1 until node 3, then the bottom 2 values are the current through the 2 voltage sources, however, they are not needed in this case.

![Screenshot 2023-04-09 at 7 26 32 PM](https://user-images.githubusercontent.com/42444869/230790076-e69611b3-0181-44aa-8df8-d4785051a4a3.png)

<a name="documentation"></a>
## Documentation

For a comprehensive understanding of the project, refer to the project report:
[View the PDF document](Circuit_Simulator_Report.pdf)

<a name="license"></a>
## License

(Include licensing information here.)
