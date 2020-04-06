# Module Overview

This module explores Ethernet in more depth.  It takes a close look at the frame format, explaining the different parts to an Ethernet frame.  The various forms of addressing are discussed as well.

Common approaches to implementing Ethernet on an embedded device are covered here as well: it includes the difference between Ethernet PHY, MAC, and the interfaces commonly used to link the two.  This section references the NUCLEO-F746ZG as a relatively small micro controller that ships with a physical LAN controller on-board, as well as code that links the MAC support on the processor with a separate PHY on the board itself.

The module then proceeds to describe how NICs \(as one might find in a modern PC\) hide much of this complexity, integrating PHY, MAC, and hardware acceleration into a single, integrated package.  As an example of such a device, a w850io from WizNet is used to add Ethernet support to a TeensyLC.  A crossover cable is used to connect two w850io's via Ethernet.  Finally, the "remote blink" example is adapted to support operation over Ethernet instead of GPIO.

