# The Freescale Cup / The NXP Cup KL25Z base code
*Note : I am not the author of this repository. Original author was Eli Hughes ?*
*Licensing unknown*
## frdm-tfc 
This repo contains at commit [`c11f3e0`](https://github.com/Overdrivr/frdm-tfc/commit/c11f3e0a3728a2fba9cf7262fa0e61950cce1032) the *original* example code for the Freescale Cup Car using the board NXP KL25Z.

This repository also contains in its most recent commits a fully open-source alternative to the original proprietary labview-based debugging.

To replace and even extend the labview interface far beyond original capabilities, the [Pytelemetry Command Line Interface](https://github.com/Overdrivr/pytelemetrycli) is used.
This CLI offers a powerful way to interact with any embedded device. Just by typing a few commands it is possible to plot data on the car, write parameters and even log an entire communication session for offline inspection.

## improvements

The following modification were performed from the original code:

* todo : Moved project to Kinetis Design Studio (KDS) that is completely free (to confirm)
* todo : Removed TFC_Terminal.c code, that defines a lot of static strings and occupies an import amount of program space
* todo : Removed labview code
* todo : Added uart driver for [`Telemetry`](https://github.com/Overdrivr/Telemetry)
* todo : Added native support for [`Telemetry`]

To use the command line interface :

1. Flash this code on the KL25Z using Kinetis Design Studio
2. Install python 3.3+
2. Install the [command line interface](https://github.com/Overdrivr/pytelemetrycli)
3. type `pytlm` to start the CLI
4. Find your device by typing `ls -s`
5. type `serial comXX -b 115200` to connect to the device
6. type `ls` to see a list of available data (each channel is called a *topic*)
7. open a plot on a topic, for instance `plot pot0`. Move potentiometer 0 and observe the result.
8. Enjoy !

Head to the [wiki](https://github.com/Overdrivr/Telemetry/wiki) of the protocol to leverage all of its powerful features.

It is even possible to output in real-time the entire linescan camera output using `indexed data`. See the [instructions on how to do it](https://github.com/Overdrivr/Telemetry/wiki/Publish-arrays-and-complex-structures).
