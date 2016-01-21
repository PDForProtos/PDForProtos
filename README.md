PDForProtos
===========

PDForProtos is a library of abstractions for [PureData-Extended](http://puredata.info/downloads/pd-extended) which provide utility objects for working with [Arduino](http://arduino.cc/)  and easy-to-use IoT communication channels (e.g., [Dropbox](http://dropbox.com/)  and [IFTTT](https://ifttt.com/)) without writing custom code. [Firmata](http://firmata.org) is used as the foundation of Arduino communication in this library.

As of 2016-01-21, it has been expanded to provide a number of utility abstractions to support DMX devices, using the `SerialToDmx` Arduino firmware distributed with DmxSimple. [DmxSimple](http://code.google.com/p/tinkerit/wiki/SerialToDmx) needs to be installed in the `Arduino`→`Libraries` directory (or wherever Arduino is set to find code). A single Arduino board *cannot* have both the Firmata and SerialToDmx code running at the same time - get a second board!

Usage
-----
Add the path of this folder to Pd's Search Path. In *Preferences*, click '*New...*', browse to this folder, click '*Okay*' then '*Apply*' and '*Save*'.

To use any of the abstractions, add one to your patch as an object. The library contains:

## File System and Dropbox interaction

* monitor_dropbox - Watches a dropbox folder for new files, emitting their contents then deleting them on a 10 second cycle. (Inputs, from left: Toggle on/off, offset path inside Dropbox, pattern to watch for)
* random_filename - Generates a random filename based on the system clock. Will append ".txt" by default, though this can be changed. (Inputs, from left: Bang to generate, set filename extension)
* update_dropbox - Writes a message to a named file in a dropbox folder. (Inputs, from left to right: Bang to write(s), offset path inside dropbox, filename to write, content to write)

## DMX Lighting interaction

* dmxRGB2RGBA - Takes in four floats, from 0-1, mapping to Red, Green, Blue and a 'brightness' values (low is dark, high is bright) and generates Red, Green, Blue, and Amber floats in the range 0-1 suitable for DMX Light colourspaces.
* dmxRGBA2DmxSimpleMsg - takes in four floats, mapping to Red, Green, Blue and Amber, and outputs messages suitable to send to an arduino running **DmxToSerial** firmware.

### Tests


History
-------
1.0.2	2016-01-21  Added dmx* components, 'dmxRGB2RGBA.pd' and 'dmxRGBA2DmxSimpleMsg.pd'
1.0.0	2014/04/14	Initial release. Added 'monitor_dropbox.pd'.
			2015/04/17 Added 'update_dropbox.pd'

License
-------
PDForProtos is released under the GNU GENERAL PUBLIC LICENSE, Version 2, June 1991. 

Please refer to the LICENSE file.
