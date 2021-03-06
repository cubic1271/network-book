---
description: Making LEDs Blink in New and Creative Ways
---

# Network Design & Implementation

## What is This?

This document is an amalgamation of stuff that experience in network research / application design has taught over the past ten years.  

In other words, it's all the stuff that the original author wishes they would've known when they were getting started.

## Why Write This?

In recent years, the study of networking has started to fragment somewhat.  A disconnect has formed between different elements and approaches: a computer scientist might have a fundamentally different view of what a network is than an electrical engineer, for instance.

As such, this \(open-source\) document tries to fuse these world views by adopting a largely project-driven approach to the subject: it teaches networking concepts from the ground up, with the first experiment involving two Arduino-compatible microcontrollers and a paper clip.  Relevant concepts are progressively introduced as they become necessary to take the project \(and thus the subject\) further.

The hope is that the projects will serve to address the question of "why" by demonstrating exactly what each successive degree \(e.g. layer\) of complexity is designed to address.  

## Who's Writing This?

Gilbert Clark is the document shepherd, but the tutorial itself is built on the generous donation of time and effort by many.  Please see the Acknowledgments section for additional detail.

## How is this Written?

To keep things manageable, however, this tutorial is divided into individual modules.  Each module describes a unique project, where the individual project is intended to introduce different concepts of networking.  Different modules may rely on different hardware.  Roughly equivalent hardware platforms may likely be substituted for the ones suggested in this document ... but the reader does so at their own risk.

## For Whom is this Written?

Individual modules will have different prerequisites.  However, at an absolute minimum, the following is recommended:

* Know enough C to read and write code for Arduino-based platforms
* Understand how to wire Arduino platforms to one another
* Read, think critically, and keep an open mind

Note that both an oscilloscope and multimeter may be useful for troubleshooting.  User-friendly, standalone oscilloscopes can be found for roughly $80 \(USD\).  Multimeters can be found for roughly $15 \(USD\).

Different projects are divided into modules.  Each module will address a different topic, and try to explain the topic by making the ubiquitous blink demonstration work in a different way.  Modules may also include more complex examples based on different hardware platforms - these should be considered as optional.

