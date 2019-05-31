# PORT MANAGER PACKAGE


## Description

This package supports the capability to turn up ports and make them available for use.

## Key features

* Turn up one or more ports on a device
* Support for both trunk and access ports
* Turn up an entire port or create subinterfaces for specific vlans
* Manage multiple vlans on trunk ports
* Manage other port parameters including mtu, speed, duplex

## Supported Device Types

This package supports Cisco IOS-XR devices.
It also contains the code to support Cisco IOS and Juniper JUNOS devices.  This code has been commented out so that the only dependency is on the Cisco IOS-XR NED.  To support Cisco IOS and/or Juniper JUNOS, un-comment the code, download the relevant NED(s) and rebuild.
Support for other device types can be added by following the example of the commented-out code.

## Supported NSO Versions

This package supports NSO 5.1 and later.

## Author
**iemsley**

## Version
1.0

## Release Date
24 - April - 2019

## Installation
* Download package from Github
* Place the downloaded package in packages directory located under your nso run directory
* Make and Reload the package

## Dependencies and How to Build

The package contains a YANG module and a XML template.
The only dependencies are on NSO (5.1 or later) and the Cisco IOS-XR NED.  It can be used with the "getting started" version of NSO that's available for download from the NSO DevNet community:  https://developer.cisco.com/docs/nso/#!getting-nso

###To build:

    cd src && make

###In NCS CLI:

    packages reload

## To add support for Cisco IOS or Juniper JUNOS

These files have commented-out sections that reference the IOS and Junos NEDs:
* src/yang/port-manager.yang
* templates/port-manager-template.xml
* src/Makefile

Edit the files and rebuild with the new NED(s).

## How to Use

This package can be run from the NSO GUI or the CLI.
In the NSO GUI, select the Service Manager tile.  Then choose the port-manager service point.
Push "+" to create a new instance of a service.  Chose the device, and give the service a name.
From the list of services, chose the one just created and push "edit".
Enter the desired port parameters.  Port-type is a mandatory attribute.
Choose an interface-type (e.g., GigabitEthernet), and then choose the interfaces on the device that you wish to put into the port group.
The Commit Manager will show the changes that will be pushed to the device.

## Demo Link :
Play recording :  https://community.cisco.com/t5/nso-developer-hub-videos/nso-port-manager-service-for-port-turnup/ba-p/3843219

## Contact:
The NSO developer hub:  https://community.cisco.com/t5/nso-developer-hub/ct-p/5672j-dev-nso
The NSO DevNet community: https://developer.cisco.com/site/nso
