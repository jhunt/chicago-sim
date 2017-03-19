CHICAGO
=======

Chicago is, well, it's kind of like TCP.  It prescribes a set of
rules that govern the acknowledgement, re-transmission, and
congestion control / avoidance.

The problem is, it isn't terribly well specified or documented.

There's the [NaCl library source code itself][nacl], and the
comments contained therein.  There's also [Matthew Demskpey's
excellent write-up][demps], guided by the NaCl C implementation
and the [golang CurveCP implementation][go1] by David Anderson.

djb alludes to the use of the Chicago schedule when discussing
[decongestion in CurveCP][curved], of which he has this to say:

> Senders increase packet-sending rates until they notice packet
> loss or increased delays as a sign of congestion. Senders then
> adapt packet-sending rates to keep loss and delays under control.
> Queue congestion is minimized.

Great, So Why This Repo?
========================

This repository is my attempt at understanding the performance
traits and behaviors of a live Chicago implementation, primarily
for use in future implementations.  I hope to produce a more
rigorous specification for Chicago, and correct any design
deficiencies found (at which point I will have to rename...)

[nacl]:   https://hyperelliptic.org/nacl/nacl-20110221.tar.bz2
[demps]:  http://shinobi.dempsky.org/~matthew/curvecp/chicago.html
[go1]:    https://code.google.com/archive/p/curvecp
[curved]: http://curvecp.org/decongestion.html
