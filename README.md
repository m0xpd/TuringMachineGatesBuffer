# Turing Machine Gates Buffer
This repository contains design details for an add-on circuit, which buffers signals from the GATES Expander port of [Music Thing Modular](https://www.musicthing.co.uk/)'s [Turing Machine](https://www.musicthing.co.uk/Turing-Machine/) random looping sequencer.

This buffer circuit was developed in response to my own requirement to obtain reliable output voltages from the Turing Machine's GATES expander port, 
particularly when using the [Voltages expander](https://www.musicthing.co.uk/Turing-Voltages-Expander/) under my ['Tuning Strategy'](https://github.com/m0xpd/TuningStrategyForVoltages), 
where small voltage errors immediately cause noticeable tuning problems.

The buffer requires no modifications to the Turing Machine - it plugs onto the GATES and Power headers, which it replaces. There is an option to add a spacer 
and an M3 screw down to one of the tapped spacers on the Turing Machine, for mechanical stability, which is strongly recommended.

# Background

I had noticed a tendency for the voltages produced at the GATES output of the Turing Machine to droop when a large number of bits were activated in 
the 'gate' sequence. This problem was exacerbated when the [PULSES expander](https://www.musicthing.co.uk/Turing-Pulse-Expander/) was used. 
The Turing Machine's power line '+12V_BACK' was observed to droop by over 1V under such loading conditions (*when no such change was seen on the system 
power supply*), making the fall in the GATEx output voltages less surprising (although the 78L09 regulated supply to the CD4050's *should* have prevented 
this - see below).

Designing a buffer for the GATE outputs under these conditions required that the additional circuit did not rely on the either the board's 12V supply or the 
magnitude of the GATEx signals. 

Although a number of design options were possible, I chose to use CD4066 "Analog Switches" (which are inexpensive and familiar to the synth DIY community) 
controlled by the GATE signals, to switch a steady voltage to the GATES expander port.

In the Turing Machine design, the GATE signals are at 9V (the supply Voltage provided to the 4050 "Buffers"). I decided to drop this to 5V i) to give more clear 
air between the failing supply and the voltage level and ii) because it is consistent with the needs of my [tuning strategy](https://github.com/m0xpd/TuningStrategyForVoltages) (where I already set the SCALE control on VOLTAGES quite low). I couln't go much lower, because I still wanted the LEDs on VOLTAGES to light up with no modifications.

Here's my schematic (click for a full-size version):

<p width=100%, align="center">
<img width=75%, src="https://github.com/m0xpd/TuringMachineGatesBuffer/assets/3152962/2bc19e9c-d881-4f29-9488-9bacee3a887f">
</p>  

There are .sch and .brd files (developed in EAGLE) for the printed circuit board in the [PCB folder](https://github.com/m0xpd/TuringMachineGatesBuffer/tree/main/PCB), along with a BoM (in EAGLE's usual format).

# Specifications

The buffer adds an additional 14 mm of depth to the Turing Machine, making the Turing Machine & Buffer extend 50 mm behind the front panel when a standard power 
header is inserted into the buffer's power receptacle (55mm if the power cable's IDC header has a strain relief fitted).

The buffer draws 2mA of current from the +12V rail and nothing from the 5V or -12V rails. 

# License

This design is published under a [Creative Commons BY-SA 4.0](https://github.com/m0xpd/TuringMachineGatesBuffer/blob/main/LICENSE.txt) License.
