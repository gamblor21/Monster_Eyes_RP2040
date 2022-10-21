# Monster Eyes RP2040

Based on https://github.com/adafruit/Adafruit_Learning_System_Guides/tree/main/M4_Eyes this is porting the Monster Eyes code to run on RP2040 based chips.

There are many support libraries required for this code to run. Adafruit Arcada did not support the RP2040. I will try to reference which ones files changed and point out and include what needs to be done in case the changes are not included upstream (and in many cases until I can polish it, for good reason!).

The code for two eyes takes advantage of both RP2040 cores. It needs some mutexs on updating where the eyes are looking. Right now both eyes can get their own ideas on where things should be going.

I had to manually download the latest version of Adafruit TinyUSB Arduino. There is some weird behavior that seems to come from having a Serial connection over USB while also mounting mass storage. It (mostly) works.

I compiled it on "Optimize" and overclocked to 150Mhz. Setting the optimization level higher led to the project not starting (not sure why).

This is a work in progress!

Changed libraries:
Adafruit Arcada (Board definition, Adafruit_Arcada_InternalFlash.cpp and Adafruit_Arcada_Filesystem.cpp)

Changes can be found in my fork https://github.com/gamblor21/Adafruit_Arcada
You will have to manually install this library as it is not in the Arduino library manager.
