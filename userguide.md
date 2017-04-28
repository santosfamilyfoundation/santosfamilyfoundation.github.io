---
layout: page
permalink: /guides/userguide/
---

# User guide

This user guide walks through every step; opening the application, configuring the project, uploading the video for analysis, and viewing the analysis results.

Explanations for the configuration values can be found either in the program with the **?** tool-tip, or in the [configuration tables section found here](/guides/userguide/configtables).

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

<center>
<img src="/img/software/creat_proj.png" width="80%">
</center>

Users then enter a project name. Any name will work, but the user should choose a name that will allow them to identify it later. Once they have entered a project name, they can click “Next” at the bottom of the dialog box. The user should see a new window pop up, prompting them for more information regarding the uploaded video, as shown below:

<center>
<img src="/img/software/proj_settings.png" width="80%">
</center>

In this new dialog box, the user can enter the video to be analyzed in the file browser. In addition, they must enter the time the video was taken, as well as the video framerate in frames per second (typically 30).

Finally, the user can use the file browser to add the overhead image of the video’s location to the project. They must obtain a satellite aerial image of the location where the video was taken. Google Maps and Google Earth are good options for obtaining this image. High-resolution, with a clear view of the area in question works best for analysis. For a video that looks like this...

<center>
<img src="/img/software/video_img.png" width="80%">
</center>

...a good aerial image would look something like this:

<center>
<img src="/img/software/air_image.png" width="80%">
</center>

After providing all the necessary information to create a new project, the user can click the “Next” button at the bottom of the dialog box. A new window will appear, as shown below:

<center>
<img src="/img/software/creating_project.png" width="80%">
</center>

In this window, the user can click on the orange “Click to create project” button. This button will copy over the video and image files the user selected, and will complete the process of creating a new project. When the process completes and the progress bar reaches 100%, the user can click the “Finish” button at the bottom of the window.

## Geometry Configuration

The first step in analyzing the traffic video is configuring the software so that it can compute the video’s geometry. There are two parts to this step:
<ol>
    <li>Computing a mapping</li>
    <li>Calculating the unit pixel ratio</li>
</ol>

Computing the mapping establishes a geometric relationship between what the camera sees and the overhead view of the world. This allows the project to calculate the speeds of road users, so this step is important.

One note, if a user is  loading an existing project, they can skip this page if they have already calculated a mapping.

### **Step 1: Pick corresponding points on both the video frame and the aerial image (use prominent landmarks for better accuracy).**

The image below shows the “Mapping” tab in the application, where the user will be computing a mapping for their project.

<center>
<img src="/img/software/mapping.png" width="80%">
</center>

There are three panels in this tab. The panel on the far left contains an image from the video. The panel on the far right contains the aerial image. The center panel should be blank. The user can zoom in and out of these images using the “Zoom” sliders directly above each panel.

To compute a mapping, the user selects four or more points in each image. These points should correspond to each other; for example, if the first point in the video image marks a street-lamp, the first point in the aerial image should mark the same exact street-lamp. Note that the user can select as few as four corresponding points in each image, but using more points will generate a more accurate mapping. We recommend selecting between 6 and 8 points.

These points should be as close to the same position as possible. If the user needs to move a point, simply click and drag the point to the appropriate location. If they need to delete a point, right-click on the point and it will disappear. The remaining points will renumber themselves.

### **Step 2: Compute a unit pixel ratio.**

The user will need to enter a “unit pixel ratio” in the box at the bottom. This unit pixel ratio is a way to convert between real-life units (feet, meters, etc) to pixels. The unit pixel ratio means how many meters of real-world distance there are per pixel in the image.

To find the unit pixel, ratio the user must:
<ol>
    <li>Find two objects that are easily recognizable or can estimate the distance between, in meters.</li>
    <li>Find the number of pixels between those two objects.</li>
    <li>Divide the distance between the two objects by the number of pixels between the two objects.</li>
</ol>

Many images, including images obtained from Google Maps, contain a scale bar that indicates how long a real-world image is on the image. If the image has a scale bar, this process is fairly simple.

First, the user must find the scale bar in the aerial image. Zooming in on the scale bar in the bottom right hand corner of our aerial image, we see the following:

<center>
<img src="/img/software/scale_bar_image.png" width="80%">
</center>

The scale bar represents a distance of 20 feet. To compute the unit pixel ratio, the user will need to complete the following steps:
<ol>
    <li>Convert 20 feet to meters.</li>
    <li>Measure the number of pixels in the 20-foot scale bar in a photo-editing program (using Photoshop, GIMP, or some equivalent).</li>
    <li>Divide the calculated number of meters by the number of pixels in the scale bar to obtain the unit pixel ratio.</li>
</ol>

So in the above example image, the user would do the following:
<ol>
    <li>Convert 20 feet to meters. 20 feet = 6.096 meters.</li>
    <li>Measure the number of pixels in the 20-foot scale bar in a photo-editing program (using Photoshop, GIMP, or some equivalent). There are 110 pixels in this scale bar.</li>
    <li>Divide the calculated number of meters by the number of pixels in the scale bar to obtain the unit pixel ratio. In this case, the unit pixel ratio is 6.096 meters / 110 pixels = 0.055167 meters per pixel.</li>
</ol>

The user then can enter this unit pixel ratio into the “Unit Pixel Ratio” box at the bottom of the window.

### **Step 3: Compute the mapping.**

Once the user has finished selecting all the mapping points and they have entered the unit pixel ratio, the user can click the “Compute Mapping” button at the bottom right of the window. After the mapping computation has completed, a new image will appear in the center panel of this tab, as shown below:

<center>
<img src="/img/software/mapping_calc.png" width="80%">
</center>

The image in the center panel shows the accuracy of the mapping. So how do they know if their mapping is accurate?

The red points represent the points the user chose and the blue points represent the points from their other image that have been re-mapped using the computed mapping. Zooming in, we see that there is very little difference between the red points and the blue points in a good mapping.

<center>
<img src="/img/software/mapping_close.png" width="25%">
<img src="/img/software/mapping_close_2.png" width="27%">
<img src="/img/software/mapping_close_3.png" width="19%">
</center>

Remember, a good mapping is critical to the rest of the process. The user must be sure to get a good mapping before they start. They can revisit this mapping at any time if it needs to be corrected.

Now that the user has computed a mapping, they can press the “Continue” button at the bottom right to begin the next step in the process: feature tracking.

## Feature Tracking

The next step in processing the video is feature-tracking. Feature-tracking is where the program tracks road users. When the program sees a moving object, it will notice “features” (points or edges) on this object, and it will follow them as the object moves throughout the video.

The Feature-Tracking tab in the application is shown below:

<center>
<img src="/img/software/test_1.png" width="80%">
</center>

In order to properly track features for the video, the user will have to help the application fine-tune its feature-tracking algorithm. They can do this by modifying certain values called parameters. These parameters are listed on the right-hand portion of the screen. We have suggested some values for these parameters in the following steps.

### **Step 1: Choose the number of frames to process in the test.**

In order to test the parameter values on a short segment of the video first, the first two boxes on the right hand side of the application control which segment of the video the user will be testing. Descriptions of these two values are included in the [Frames to process table](/guides/userguide/configtables#feature-frames-to-process).

### **Step 2: Set the feature-tracking parameters.**

Now the user has to help the program figure out how best to track features. These parameters govern how the program tracks features, so this is a very important part of the process. The user can provide sample values to the program for each of these parameters. They must make sure to provide values for each parameter.

The parameters for feature-tracking can be found in the [Feature-tracking parameters](/guides/userguide/configtables#feature-tracking-parameters).

The parameters used for this video are included in the screenshot below:

<center>
<img src="/img/software/test_1_filled.png" width="80%">
</center>

After the user has entered all the parameter values, they can click the “Set Config” button to save these values.

### **Step 3: Test the parameters.**

After pressing the “Set Config” button to save their parameter values, the user can use the “Test on Sample” button to process the particular section of the video with the given parameter values. This allows the user to view a short preview of the video to make sure that the parameters are working well. Zooming in, a good feature-tracking result looks something like this:

<center>
<img src="/img/software/test_1_results.png" width="80%">
</center>

Each of the moving objects in the frame has lots of brightly-colored “feature-tracks” trailing them. Note that only moving objects will be tracked with features. If an object stops, its feature-tracks will disappear — if the object starts moving again, its feature-tracks will reappear.

### **Step 4: Rinse and repeat.**

If the feature-tracking result doesn’t look something like the example shown above, the user will likely need to continue tweaking the parameters. Just as with the mapping, they can revisit this step at any time.

Once the user is  done, they can click on the “Continue” button to proceed to the next step -- using these features to track road users.

## Tracking Road Users

The next step in processing the video is object-tracking. In this step, the program will take the features the user tracked in the previous step and “group” them into objects representing road users. Again, they will have to enter parameters to help the feature tracking program group features into objects.

The screenshot below shows the road-user tracking stage of our application:

<center>
<img src="/img/software/test_2.png" width="80%">
</center>

### **Step 1: Set object tracking test length.**

Just as in the “feature-tracking” stage, the user can choose the number of frames to process. If the input here is blank, the entire video will be processed which can take a long time depending on the length of the video. The user can change the amount of video to process with the parameters found in the [object frames to process](/guides/userguide/configtables#object-frames-to-process) table.

### **Step 2: Set grouping parameters.**

Now the user has to help the program figure out how best to group features together into objects. These parameters govern how the program determines what objects are. Provided are sample values to the program for each of these parameters. The user needs to make sure to provide values for each parameter!

The parameters for object-tracking can be found in the [object-tracking parameters](/guides/userguide/configtables#object-tracking-parameters) table.

The screenshot below shows these parameter values entered for our example:

<center>
<img src="/img/software/test_2_val.png" width="80%">
</center>

After the user has entered all the parameter values, they can click the “Set Config” button to save these values.

### **Step 3: Test the parameters.**
The user can use the “Test on Sample” button to process the particular section of the video with the given parameter values. This allows them to view a short preview of the video to make sure that the parameters are working well. If they are, they can proceed to the next step. If not, the user can reset the parameter values. Zooming in, a good object-tracking result looks something like this:

<center>
<img src="/img/software/test_2_result.png" width="80%">
</center>

Each of the objects now has a brightly-colored track behind it. Just as with the feature-tracking, note that only moving objects will be tracked. If an object stops, its object track will disappear -- if the object starts moving again, its object track will reappear.

Sometimes, multiple road users will be grouped together as a single user. An example of this is in the image above -- three pedestrians crossing the street together are grouped together as a single object. The user can try to mitigate this issue using the parameters, but they may not be able to completely eliminate this.

Again, this step can be revisited at any time.

### **Step 4: Track the objects throughout the whole video.**

If the user is confident that objects are being tracked properly, they can press the “Run” button to process the whole video with the given mapping and parameters. This will likely take some time, so a user must try to tune the parameters well in the previous steps.

After the video has finished running, the results can be viewed after the user presses the “Continue” button.

## Viewing Results

So the user has processed the video -- this process probably took a long time. Now what?

The software will generate a safety report for the intersection. This safety report will demonstrate key safety metrics and show visualizations to communicate the safety analysis to the traffic engineer.

Further discussion of safety metrics and visualizations takes place in the Safety Metrics portion of this paper. This section will discuss the data and raw statistics generated by our software, as well as the visualizations that our software will create.
