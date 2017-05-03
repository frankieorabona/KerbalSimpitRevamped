# Kerbal Sim Pit Changelog

## v0.7 prerelease (2017-05-01)

Big focus on getting the KSPSerialPort class receiving properly on Windows.

* Switched from SerialPortLib2 to PsimaxSerial for the underlying serial
driver. This will soon be migrated (again), to my own fork of mono's
System.IO.Ports class.
* Added a new serial read thread to, that just periodically polls.
* Currently using regex matching on the serial port name and initialisation:
  * COM ports imply Windows, and the new serial polling read thread is used.
  * For all other ports, the existing async event handler thread is used.

## v0.6 prerelease (2017-04-24)

* Add support for standard action groups (staging, abort, lights etc). As
with custom AGs, packets for enable, disable and toggle have been added.

## v0.5 prerelease (2017-04-22)

* Add toggle Custom AG packet and handler.

## v0.4 prerelease (2017-04-20)

* Fix off-by-one errors in the array iteration loops. This was most
obvious in the staging handler, but potentially happening elsewhere.

## v0.3 prerelease (2017-04-01)

* Modify Staging handler to accept byte array payload (can now enable and
disable the staging AG in a single packet).

## v0.2 prerelease (2017-03-29)

* Custom Action Group support added (including Action Groups Extended
integration)

## v0.1 prerelease (2017-03-26)

* Asynchronous serial read thread complete.
* Echo handler implemented.
* Staging test handler implemented.
* Altitude handler implemented.
* Initial release.