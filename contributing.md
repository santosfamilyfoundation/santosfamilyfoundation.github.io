---
layout: page
permalink: /contributing/
---


# Contribute to Santos Traffic Platform

_If you are interested in __only using__ the software and __not modifying the code__, please see our [downloads page](/downloads/)_

## Setup Guide

### Front-End Dev

If you are only interested in improving the front end, __it is not required to install SantosCloud__. A cloud instance is running and is accessible at __http://server.santostraffic.com__.

1. Fork the [SantosGUI repo](https://github.com/santosfamilyfoundation/SantosGUI) and follow the [SantosGUI installation instructions](https://github.com/santosfamilyfoundation/SantosGUI#installation)
2. Try [running the front-end](https://github.com/santosfamilyfoundation/SantosGUI#running)  
3. When creating a new project, point to __http://server.santostraffic.com__.
4. Learn more about the cloud API by reading the [SantosCloud API docs](http://santostraffic.com/SantosCloud/app/static/apidoc/).

### Full-Stack Dev

For running the server code locally, we setup a Vagrant box running the server.

Please see our [__SantosInstallation__](https://github.com/santosfamilyfoundation/SantosInstallation) repository for instructions.


## Software Architecture
SantosPlatform is built from three components working in tandem:  TrafficIntelligence, SantosGUI, and SantosCloud.  These components each handle a part of the work of analyzing a user’s video -- from project creation, configuration, uploading, and analyzing.  The relations between these components are detailed below.

<center>
<img src="/img/System_Diagram.jpg" width="100%">
<p>System diagram detailing relationships between TrafficIntelligence, SantosGUI, and SantosCloud</p>
</center>

__TrafficIntelligence__ is a computer-vision tool that tracks cars, bikes, and pedestrians.  The TrafficIntellingence project is traffic analysis software created by Dr.  Nicolas Saunier from the Poly-technique University of Montreal.

__SantosCloud__ is the portion of the software system that runs TrafficIntelligence on remote servers. SantosCloud provides a web API which will perform video analysis.

__SantosGUI__ is a front-end for users to add video data, configure mapping, and modify analysis parameters for more accurate tracking.  Once the user has performed all of the necessary configuration in this user interface, their video and configuration are uploaded via SantosCloud’s API for processing.  Once processing is complete, SantosGUI displays the resulting trajectory video footage and generated metrics.
