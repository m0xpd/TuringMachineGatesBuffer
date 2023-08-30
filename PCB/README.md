# PCB

Design files for the gates buffer printed circuit board in EAGLE format are in this folder.

There is a .sch and a .brd file and a Bill of Materials.

The prototype was manufactured by [JCLPCB](https://jlcpcb.com/) (usual disclaimer), who did a great job. The populated  board is seen below from both sides:

<p width=100%, align="center">
<img width=75%, src="https://github.com/m0xpd/TuringMachineGatesBuffer/assets/3152962/bef1898a-0367-481b-89b8-813649d72350">
</p>

The BoM lists JP1, JP2 and JP3 as PIN HEADERS. It will be seen in the image above that JP1 and JP3 are populated by female headers (sockets) on the underside 
of the board.

JP1 is a 2 * 8, 0.1 inch pitch socket (which mates with the Turing Machine's GATES expander header) and JP3 is a 2 * 5, 0.1 inch pitch socket, which mates 
with the Turing Machine's power connecter.

[I cut these from 2 * 40 socket strips, rather than keep smaller size sockets - it is cheaper and easier in 'stock control'.]

JP2 is a male 2 * 8 header, mounted on the top (component) side of the board, which becomes the new GATES expander.

The buffer specifies a shrouded male header for the power connection, which avoids the possibility of incorrect power cable orientation. You can fit a plain 2 * 5 
male header here if you prefer.

It is seen that the board edge is profiled to allow access to the PULSES expander port.
