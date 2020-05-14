---
description: Hardware & Capabilities
---

# Meet the TeensyLC

{% hint style="info" %}
While the TeensyLC is described here, any platform with a functional set of$$I^2C$$pins and around 48KB of SRAM should suffice for this tutorial.  Note that SRAM limitations on the traditional Arduino Uno platform make it a poor fit for later chapters.  Also, note that different systems may require some additional effort to configure $$I^2C$$pins as needed by this tutorial.
{% endhint %}

### Board Selection

One of the challenges with trying to find a microcontroller and / or development board for a project is that there are a virtually infinite number of choices.  There are a large number of popular microcontrollers in use, with some of the more common variants including PIC, AVR, HC11, and ARM.  Given the vast number of options available, how might one identify an option that can work?  In order to answer this question, it's necessary to address a different question instead: what do we want to our system to be and to do?

This involves sketching out a set of things we want our system to be and to do.  In this case, the target is something that:

* Supports Arduino libraries and development patterns
* Supports$$I^2C$$\(which we'll come back to later in this section\)
* Supports$$SPI$$\(important for interfacing with a radio in a future module\)
* Has enough RAM and ROM that we won't be fighting to make our programs fit
* Is cheap enough that we can buy three without breaking the bank

Based on the above, why not go with a vanilla Arduino?  Generally, the Arduino has very little SRAM.  While it's often fun to squeeze incredible capabilities into tiny packages, that kind of optimization often acts to obscure the intent of the development being done.  As such, it's often better to build prototypes on hardware that's a little more powerful than might be absolutely necessary.

Generally, ARM Cortex M0+ / M4 microcontrollers are a pretty good replacement - a large number of them have libraries that support familiar Arduino programming patterns, allowing them to run the same software that an Arduino might.  While a number of platforms would likely be viable \(e.g. any ESP32-based platform, most of Adafruit's Feather line, SparkFun's Artemis Nano\), we've selected the Teensy Low Cost \(or TeensyLC\) as our target platform for this tutorial.  

The TeensyLC strikes a balance between capability and cost.  The boards are \(at the time of this writing\) a little under $15.00 USD each, and offer straightforward integration with the PlatformIO IDE.  With that selection in mind, let's go ahead and take a look at the system.

### Evaluating the TeensyLC

The TeensyLC has two important components: a reference card that describes the pins, and the board itself \(nestled inside a bit of static-resistant packaging\).  Note that it might be worthwhile to take one card and pin it to the wall above the workspace - while this guide does provide pictures of specific configurations, having the guide handy can be useful for sanity checking and the like.

![TeensyLC in packaging](../.gitbook/assets/image%20%284%29.png)

![TeensyLC with headers included](../.gitbook/assets/image%20%286%29.png)



