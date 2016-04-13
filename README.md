lcdproc-temperature
=============
A small [LCDproc](http://lcdproc.omnipotent.net/) patch adding a custom screen aggregating CPU, memory and temperature info. It is geared towards the Raspberry Pi (any model) and a 4x20 LCD:
```
+--------------------+
|##### CPU MEM #####@|
|----|----|----|----||  CPU usage gauge per core
|%[-----------------]|  Total CPU usage gauge
|E-------F  T: XX°C  |  Memory usage gauge and current core temperature
+--------------------+
```

Details
------------
Temperature information is gathered from `/sys/class/thermal/thermal_zone0/temp`, and can be adapted for other paths in `clients/lcdproc/machine_Linux.c`. The other information is based on LCDproc built-ins.
Since it is not portable and hardware specific, there is no reason to commit this upstream, so the patch is published here. Comments, improvements, corrections, and rants welcome...

Usage
------------
Activate the `[Total]` screen in your lcdproc.conf

Demo:
------------
[![LCDproc mod demo](https://img.youtube.com/vi/_GWDRugxmTc/0.jpg)](https://www.youtube.com/watch?v=_GWDRugxmTc)
