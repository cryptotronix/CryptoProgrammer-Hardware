# Crypto Programmer Hardware

This repo is the hardware files for the Crypto Programmer, a tool that
is hopefully useful for working with the Microchip
CryptoAuthentication Line.

Microchip already makes a useful development git
(https://www.microchip.com/developmenttools/productdetails.aspx?partno=at88ck101sk-mah-xpro),
and the schematics and firmware, but we wanted to "Build our own
Birdfeeder." The intention for this project is to fully Open Source
Hardware, although it doesn't quite meet the definition:
https://www.oshwa.org/definition/

## Overview

The intention of this tool is to expose a scripting-like interface on
a USB-Host that can send the raw byte commands to the part over
I2C. In other words, it is an USB-to-I2C bridge. Most dedicated
USB-to-I2C bridge have a hard-stop of a reasonable number of
bytes. The CryptoAuthentication parts however, send commands in the
few hundred bytes in a continuous I2C frame. Hence, why this tool
exists.

The other use-case for this tool is that you could program the MCU and
then use it to program other CryptoAuthentication parts with the use
of the "extra special button." I often lift CryptoAuthentication parts
from PCBs, drop them in a socket and dump their memory and this tool
should make that easier for me as well.

## Hardware Required

You'll want to attach the USB micro cable to the Crypto Programmer
then attach the plug-side to an appropriate port. I2C lines are on the
right-angle header and you can fly-wire to your heart's content, but
your life will be much easier if you get yourself the AT88CK101 Kit
(https://www.microchip.com/developmenttools/productdetails.aspx?partno=at88ck101sk-mah-xpro)
which comes with a UDFN or SOIC8 socket. The right angle header will
mate with the socket board. This will allow you to test your code
against the Microchip tools, use the CryptoProgammer, and then attach
it to a Microchip development board like a SAMV71.

## Status

Rev A of the Hardware is done and works (we think). We are still
working on the firmware, so once that's in a workable state that will
be released under a BSD license.
