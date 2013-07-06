# efmo example 01

Simple example of using the EFMO method in GAMESS

## Requirements

  * GAMESS version 131, released at the end of May 2013.
    + Configured to run on your super computer through the rungms program in the GAMESS folder.

# What will it do?

This example will run a single geometry optimization on chorismate mutase using the very recent EFMO method with frozen domain and dimers (FDD) to help speedup the computation. There are two coordinates that are harmonically constrained.

## What keywords am I looking for

  * The FD and FDD methods require either MODFD=1 or MODFD=3 in $FMO, respectively. In the present example it is set to 3.
  * Harmonically constrained atoms are defined by the IHMCON arrays. 1,a,b means constrain the *distance* between two atoms a and b. Forceconstants are given by FHMCON and distances in SHMCON. All these are found in $STATPT.
  * In FD and FDD, fragments in layer two carry a special meaning (see [this paper](http://dx.doi.org/10.1021/jz1016894)) since they are part of a buffer region (B). Only some of the atoms are allowed to move in this buffer region (A). The movable atoms are controlled in IACTAT in $STATPT.
  * EFMO can be disabled by writing IEFMO=0 in $FMO
  * The number of nodes can be changed in NGROUP in $GDDI
