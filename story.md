---
layout: page
permalink: /story/
---

# The Development of Santos Traffic Platform

In 2014, the Olin College of Engineering teamed up with the Santos Family Foundation to begin a multi-year project working in the traffic safety space. The first part of the project began in June of 2014, and laid some of the ground work which future teams built on. Olin then transferred this project to the Senior Capstone program (SCOPE) at Olin, which meant that 4-6 Seniors would be dedicating a full year of class time on this project.

## Senior Capstone Project 2014-2015

The 2014-2015 SCOPE Team began work by conducting user interviews and determining the best direction to take the project. A majority of the year was spent on narrowing the project definition into something that future teams could begin technical work on. This team discovered intersections to be a major pain point and began ideation on how to work in this space.

## Senior Capstone Project 2015-2016

The 2015-2016 SCOPE team took the previous year's findings and expanded on them. They conducted in-depth interviews with advocacy groups and traffic engineers, who they identified to be the major change-makers in intersection infrastructure. After gathering a surplus of information, they began developing a software system which could produce safety metrics of any intersection. To accomplish this, the team adopted a pre-existing traffic analysis library produced by Dr. Nicolas Saunier from Polytechnic Institute of Montreal. His library provides video analysis functions which use OpenCV to create vehicle counts, speeds, and trajectories. From these speeds and trajectories, another layer of analysis can be run to determine collision data and near miss counts. The team managed to produce a rough User Interface which called these functions and aided the user in understanding the data from the video they are processing.

## Senior Capstone Project 2016-2017

Our team picked up the project from the stopping point of the 2015-2016 team. We immediately began work on the User Interface, using it to better understand functionality of the underlying library.

### Our First Traffic Study

We began a traffic study in Needham, MA, first by asking permission of a local shop owner, Harvey's Hardware, to put a camera on top of their roof with view of the intersection. After 24 hours of collecting video data, we went back, removed our installation and began processing our data. We had about 10 hours of usable data from the installation, since it was powered by a battery, and we eventually depleted it. After we had completed several hours of analysis, we took the data to the Needham Heights Neighborhood Association to show them the results of our findings and begin the conversation of how to most effectively use the data we gathered for the community.

### Separation of User and Process

One of our immediate reactions to the software from the 2015-2016 SCOPE team was the difficulty of installing both the user interface and the traffic analysis library which was provided by Dr. Saunier. We knew that with the challenges we faced, many potential users would not be able to easily finish the installation, instead hitting errors which would prevent the software from running. To solve this, our team moved the processing and analysis library to a cloud-based platform. No users would be required to download and install this portion of the software. We developed a Vagrant image with all the software and dependencies required to make the user interface functional. Using the Tornado framework, we developed an API for the user interface to connect to the cloud processing functions. This has several benefits: developers can use the API to make calls to the server, the server components can be spun up in AWS on multiple machines, and developers can create their own front-end for different use cases we have not thought of..

### Code for Boston

As our project comes to a close, we have looked for interested people who want to continue the technical development of our software. Code for Boston is a group of civic-minded developers who hack on open source projects in their free time. We have approached them about adding the Santos Traffic Platform to their list of projects and the group is interested. If they decide to adopt this project, development and refinement can continue to occur, even though the Olin SCOPE program will no longer be working with the software.

### Creating Kross, a Civic-Focused Company

Two members of the 2016-2017 SCOPE team have been accepted into the Summer Venture Program with Babson College. Through this program, these members will create Kross, a business venture utilizing the software created during SCOPE. In this capacity, our pilot ventures will continue with the guidance of Kross, as well as continued support for the software development.

### Signing on Early Users

The software is available for download and use, and we encourage anyone who is interested in running a study to go ahead and try. Contact us with any questions or comments.
