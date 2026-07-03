Elevator Controller (FSM-based) — Verilog

A finite-state-machine (FSM) based elevator controller written in Verilog, modeling a 4-floor elevator that services both internal cabin requests and external floor calls.

Overview --

The controller is built around 4 states:

IDLE , MOVING UP, MOVING DOWN, DOOR OPEN 


Features

-Clean synchronous FSM design (state register + combinational next-state + combinational outputs)
-------Parameterized floor-to-floor travel time (MOVE_TIME) and door-hold time (DOOR_TIME)
-------Request latching and automatic clearing once a floor is serviced
-------Handles simultaneous multi-floor requests
-------state exposed as a top-level output for easy waveform debugging
-------Testbench covering single trips, simultaneous requests, and same-floor requests, with human-readable state names in the console log



Running the simulation

Create a new project and add elevator_controller.v as a design source and elevator_controller_tb.v as a simulation source.
Set elevator_controller_tb as the simulation top module.
Run Behavioral Simulation.
Inspect state, current_floor, motor_up, motor_down, and door_open in the waveform viewer.
<img width="2350" height="1422" alt="Screenshot 2026-07-03 144508" src="https://github.com/user-attachments/assets/1b4a75cf-f234-474d-810b-874ed32f20a9" />
<img width="2360" height="1358" alt="Screenshot 2026-07-03 144723" src="https://github.com/user-attachments/assets/0d13bcff-cf8c-453a-9db6-5f106bb82cd2" />


Possible future improvements

Separate cabin-request and hall-call inputs (with up/down call direction)
Configurable number of floors instead of a fixed 4
Priority/direction-locking logic closer to a real commercial elevator dispatch algorithm
