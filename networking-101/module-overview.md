---
description: First Steps in Networking
---

# Module Overview

### Overview

For ages, computer science has taught students to display "Hello, world!" as part of the first program they write.  This text is tangible proof that the code exists: the code has done something that the student can see.  For electronics, the equivalent is a blinking LED: that single, simple flash offers proof that the students has affected the world around them in a way that they can see.  This book builds upon that fundamental existence proof and abuses it in creative ways to demonstrate different principles of networking.

This introductory module begins with an introduction to the recommended hardware platform for this series: the TeensyLC.  Once the platform has been explained, the module also points the interested student to an integrated development environment that should be suitable for development throughout the tutorial.  Next, the development environment is used to construct a blink application that can be run on the TeensyLC.

Once blink has been run successfully, the module explores how one can extend the blink application.  First, the tutorial describes how a second TeensyLC can be added and used to make a LED blink on a physically separate TeensyLC system.  This remote control makes use of the$$I^2C$$support included with most modern microcontrollers, and so the module thus offers an introduction to principles of networking as they relate to $$I^2C$$\(e.g. addressing, clocking, and master / slave\).

Next, the tutorial further extends the system to allow a single TeensyLC to drive a LED to blink on two other systems at once.  This part of the module also relies on$$I^2C$$, and begins to introduce some more advanced concepts \(e.g. the $$I^2C$$general call\).

### Materials

* 3x TeensyLC devices
  * These devices can be purchased with headers pre-soldered
* Jumper wire



