PEAS-Vacuum-Cleaner-Agent
Implementation of PEAS descriptors using a Vacuum Cleaner Intelligent Agent in Prolog.

PEAS Vacuum Cleaner Intelligent Agent
Practical Assignment 1
This project demonstrates the PEAS framework using a Vacuum Cleaner Intelligent Agent.

PEAS
Performance Measure: Clean all dirty rooms and minimize unnecessary movement.
Environment: Rooms A, B and C.
Actuators: Clean, move and stop.
Sensors: Detect dirt, location and remaining dirty rooms.
Environment
The vacuum starts in Room A.

A → B → C

Initially:

Room A: Dirty
Room B: Clean
Room C: Dirty
Technology
Prolog
SWI-Prolog / SWISH
How to Run
Open vacuum_agent.pl in SWI-Prolog or SWISH Prolog and execute:

start.

Expected Result
The agent cleans Room A, moves through Room B to Room C, cleans Room C, and stops when all rooms are clean.

