PDForProtos
===========

PDForProtos is a library of abstractions for [PureData-Extended](http://puredata.info/downloads/pd-extended) which provide utility objects for working with [Arduino](http://arduino.cc/)  and easy-to-use IoT communication channels (e.g., [Dropbox](http://dropbox.com/)  and [IFTTT](https://ifttt.com/)) without writing custom code. [Firmata](http://firmata.org) is used as the foundation of Arduino communication in this library.

Usage
-----
Add the path of this folder to Pd's Search Path. In *Preferences*, click '*New...*', browse to this folder, click '*Okay*' then '*Apply*' and '*Save*'.

To use any of the abstractions, add one to your patch as an object. The library contains:

* monitor_dropbox - Watches a dropbox folder for new files, emitting their contents then deleting them on a 10 second cycle.

### Tests


History
-------
1.0.0	14/04/2014	Initial release. Added 'monitor-dropbox.pd'.

License
-------
PDForProtos is released under the GNU GENERAL PUBLIC LICENSE, Version 2, June 1991. 

Please refer to the LICENSE file.