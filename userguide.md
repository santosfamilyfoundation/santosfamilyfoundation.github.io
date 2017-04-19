---
layout: page
permalink: /guides/userguide/
---

# User guide

This user guide walks through every step; opening the application, configuring the project, uploading the video for analysis, and viewing the analysis results.

## Installation information

SantosPlatform consists of three parts: SantosCloud, TrafficIntelligence, and SantosGUI. SantosCloud and TrafficIntelligence are meant to be installed on remote servers, and SantosGUI will be installed on the user’s machine. Users can find installation instructions for each component on the respective repository:
- [SantosGUI](https://github.com/santosfamilyfoundation/SantosGUI)
- [SantosCloud](https://github.com/santosfamilyfoundation/SantosCloud)
- [TrafficIntelligence](https://bitbucket.org/Nicolas/trafficintelligence/wiki/Home)

To install the server component, the [SantosInstallation](https://github.com/santosfamilyfoundation/SantosInstallation) repo contains all necessary instructions.

Once the GUI software is installed on their system, users need to follow these steps to get their video analyzed:
<ol>
    <li>Create the project and input the necessary videos and images.</li>
    <li>Configure parameters that the software needs to compute the video’s geometry.</li>
    <li>Configure parameters that the software needs to perform feature tracking.</li>
    <li>Configure parameters for object tracking analysis.</li>
    <li>Upload their video and configurations and view the results of the analysis that are returned from the server.</li>
</ol>

## Creating a project

The first step for users is creating a new project. To create a project, the user presses “File” -> “New project”. Users who have previously created a project can instead select “Open project” to use their old project.
