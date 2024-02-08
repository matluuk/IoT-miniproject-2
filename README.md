# IoT-miniproject-2

This is a repository for a for Mini project 2 for Internet of Things - Universioty of Oulu course.

# Project idea

The idea of this project is to develop a simple location tracker for a bike. 

The device should be able to work multiple days continuosly.

The Location data would be searched periodically, for example one time in a day. Additionally a accelerometer would be used to detect bike movement and trigger location search.

Two device modes would be implemented. Active mode for continuous location search, and Passive mode for movement detection and 

A website would be made for watching the bike location ands changing the tracker settings such as device mode and time between periodic location searchs.

# inspiration for code

This projects is built on top of Nordic semiconductor's course: [link](https://academy.nordicsemi.com/courses/cellular-iot-fundamentals/)
The nordic semiconductor example application [asset_tracker_v2](https://developer.nordicsemi.com/nRF_Connect_SDK/doc/latest/nrf/applications/asset_tracker_v2/README.html) is used as a inspiration. I took inspiration especially for the application module design and event handling, as I didn't have much experience in these parts of the embedded software development.

# Requirements

## Device hardware
The applicarion is developed for [nRF9160](https://www.nordicsemi.com/Products/nRF9160) SiP. Specifically for [Thingy91](https://www.nordicsemi.com/Products/Development-hardware/Nordic-Thingy-91) Multi-sensor cellular IoT prototyping platform. However [nRF9160 DK](https://www.nordicsemi.com/Products/Development-hardware/nrf9160-dk) would also work with small code changes.

## Linux virtual machine for CoAp server
Linux virtual machine is requred for CoAp server. There is a [quide](https://github.com/matluuk/IoT-miniproject-2-Coap-Server?tab=readme-ov-file#create-linux-virtual-machine) in the CoAp server readme for setting up the virtual machine in Google Cloud.

Requirements for the virtual machine:
- runs linux, preferably Ubuntu 20.04
- external IPV4 address
- port 5683 (CoAp backend) open for udp
- ports 5000 (flask app) and 8000 (http website) open for tcp
- SSH connection to the virtual machine

# Demonstration video
I have recorded a [Demonstration video](https://www.youtube.com/watch?v=Zl9ehaItiA8&ab_channel=jaba4732)
of the project to youtube. In the Video I show that the project is working. One location fix is successfull and is shown on the website.

# nRF9160 - Thingy 91 application readme
Information of the Thingy:91 application can be found on the submodules IoT-miniproject-2-device readme. 
[link](https://github.com/matluuk/IoT-miniproject-2-device?tab=readme-ov-file#iot-miniproject-2)

# CoAp server readme
Information about projects CoAp server can be found from submodules IoT-miniproject-2-Coap-Server readme.
[link](https://github.com/matluuk/IoT-miniproject-2-device?tab=readme-ov-file#iot-miniproject-2)

# Project outcome

I managed to create working location tracker with basic functionalities. Further development of the project would be easy as the tracker application is modular and has advanced event handling between modules. 

I didn't have time to implement all planned features. Biggest missing feature is the lack of movement sensing on the location tracker. Other features, that would be create for the location tracker would be battery level indication and temperature data.

The website to see the locaiton data is good enough for this project, but it is far away from a good truely usable website. For example the website uses plain http server, and it is not therefore secure. It doesnät have any login system to reduce unwanted traffic and overally it is very basic. 

## Testing

I had time to create some unittests for the CoAp server, but there are no tests for the tracker application itself. For the device, all testing was manual. Inorder to develop the tracker further, excessive testing for the tracker application would also be needed.
