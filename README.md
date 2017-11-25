# ngspice-voltage-divider
So! Let's get started with a simple voltage divider. We have two resistors R1,
and R2. We will hook them in series and attach across them some sort of
battery. We will then attach a probe between them, and if luck holds out, this
should give us a voltage drop of  R1/(R1+R2)


```
Voltage Divider
vin 1 0 1.0
r1 1 2 5K
r2 2 0 5K

.dc vin 0.0 1.0 .1
.plot dc v(1)
.end
```


```
$ ngspice vd.cir
******
** ngspice-27 : Circuit level simulation program
** The U. C. Berkeley CAD Group
** Copyright 1985-1994, Regents of the University of California.
** Please get your ngspice manual from http://ngspice.sourceforge.net/docs.html
** Please file your bug-reports at http://ngspice.sourceforge.net/bugrep.html
** Creation Date: Fri Sep 15 04:36:30 -03 2017
******

Circuit: voltage divider

ngspice 1 -> run
Doing analysis at TEMP = 27.000000 and TNOM = 27.000000



No. of Data Rows : 11
ngspice 2 -> plot V(1),V(2)
ngspice 3 ->
The file "/tmp/hc8788" may be printed on a postscript printer.
^Dquit
```



```
$ ngspice vd.cir
******
** ngspice-27 : Circuit level simulation program
** The U. C. Berkeley CAD Group
** Copyright 1985-1994, Regents of the University of California.
** Please get your ngspice manual from http://ngspice.sourceforge.net/docs.html
** Please file your bug-reports at http://ngspice.sourceforge.net/bugrep.html
** Creation Date: Fri Sep 15 04:36:30 -03 2017
******

Circuit: voltage divider

ngspice 1 -run
Doing analysis at TEMP = 27.000000 and TNOM = 27.000000



No. of Data Rows : 11
ngspice 2 -hardcopy xyPlot.ps v(1),V(2)

The file "xyPlot.ps" may be printed on a postscript printer.
ngspice 3 -> ^Dquit
```
