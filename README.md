# Pi TV Streamer

Pi TV Streamer is a set of instructions on how to setup a Raspberry Pi to look and act more like a smart TV.


## Project Status

The instructions in this repository are an ongoing work-in-progress.

They are more or less complete, and can be followed to setup a functional media center.

However, they need refinement, and will occasionally be updated with new services, screenshots, etc.

## Supported Devices

These instructions were written with a Raspberry Pi 4 or 5 in mind.

However, they should also work with other ARM SBCs, such as an Orange Pi.

They should also work with an x86 machine, such as an Intel NUC.

Basically, anything that can run [Plasma Bigscreen](https://plasma-bigscreen.org) is suitable.

Just make sure that your device is powerful enough to run your target resolution. 4k displays are pretty demanding, for example, and require a more powerful device than a 1080p display would.

* Note that the instructions and screenshots throughout this guide depict Raspberry Pi OS. So some sections of this guide will require tweaking for other platforms.

## Overview

The instructions in this repo will result in:

- A Raspberry Pi (or other device) running [Plasma Bigscreen](https://plasma-bigscreen.org)
- Desktop apps for streaming services (where possible)
- PWAs for the web versions of other streaming services
- A working remote control

The goal is to have tiles on Plasma Bigscreen which look and act like app tiles on a smart TV.

They will mostly be websites rather than apps, since streaming services don't usually provide Linux clients.

## Requirements

- A Raspberry Pi 4 or other suitable target device
- A secondary device other than the Raspberry Pi (eg. a mobile phone or laptop) to read these instructions from
- (Optional) A case/dongle with an IR receiver
- (Optional) An IR remote control

A second device is recommended because this guide will have you logging in/out and rebooting at times, so it's easier to keep the instructions open on a separate device.

The remote control and receiver are optional, but recommended for a more TV-like experience.

## Get Started

[Follow this link](install/README.md) to start setting up your device.