# Hepta-Pi
This is a Compute Cluser of 7 Raspberrry Pi CM4 sized boards. One of the boards (Module 0) has a
fairly full compliment of I/O. Boards 1-4, also mounted on the top, have an HDMI and a single USB
port, so can be debugged with a keyboard and monitor.  Boards 5-6 are mounted on the bottom,
and have a bare minimum of I/O.  All 7 boards are connected to an on-board 1G ethernet switch,
which has 1 external connector.  The overall board size is 150X150mm.   The whole thing is powered from a single 12V barrel jack.

I had initially conceived this as a CPU based crypto curency miner, but I later discovered that the ARM 
based CM4 boards and their competitors are not very effective crypto miners. 
So this is left as a generic compute cluster, with workload controlled by something like Kubernetes.

This work is licensed under a
[Creative Commons Attribution 4.0 International License][cc-by].

[![CC BY 4.0][cc-by-image]][cc-by]

[cc-by]: http://creativecommons.org/licenses/by/4.0/
[cc-by-image]: https://i.creativecommons.org/l/by/4.0/88x31.png
[cc-by-shield]: https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg
