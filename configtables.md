---
layout: page
permalink: /guides/userguide/configtables
---

## Feature frames to process

<table border="1">
<tr>
<td><strong>Parameter Name and Sample Value</strong></td>
<td><strong>Parameter Description</strong></td>
</tr>
<tr>
<td>First frame to process. <br /> Starting value: 0</td>
<td>First frame of the video to be processed. Despite the variable name, frames are indexed at 0 -- if the user wishes to start from the beginning of the video, they will set this parameter to 0.</td>
</tr>
<tr>
<td>Number of frames to process. <br /> Starting value: 200</td>
<td>Number of frames to process. The user will set this so they can see at least a few seconds of video. They will be using this to test the other parameters later.</td>
</tr>
</table>

## Feature-tracking parameters

<table border="1">
<tr>
<td><strong>Parameter Name and Sample Value</strong></td>
<td><strong>Parameter Description</strong></td>
</tr>
<tr>
<td>Maximum number of features. <br /> Starting value: 1000 <br /> Recommended range: 1000+</td>
<td>The maximum number of features added at each frame. Note if that there are many moving objects in each frame, and those objects take up a large portion of the frame, this number may be higher. If the user find that not enough features are being tracked, they can increase this parameter.</td>
</tr>
<tr>
<td>Number of displacements. <br /> Starting value: 10 <br /> Recommended range: 2-15</td>
<td>This parameter helps determine how long features will be tracked. If the user increases this parameter, features will disappear less quickly (i.e., after a few frames).</td>
</tr>
<tr>
<td>Minimum feature displacement. <br /> Starting value: 0.0001</td>
<td>Recommended range: 0.0001 to 0.1 | This parameter describes the minimum required displacement to keep a feature (in pixels). If the user has lots of slow-moving (or far-away) objects in their video and find that not enough features are being tracked, they can decrease this parameter. On the other hand, if too many non-road user features are being tracked (i.e., trees swaying in the wind) it may be useful for them to increase this parameter to capture the faster-moving features, which are more likely to belong to road users.</td>
</tr>
<tr>
<td>Maximum number of iterations. <br /> Starting value: 200 <br /> Recommended range: 10-1000</td>
<td>This parameter changes how long after a feature continues to persist after the feature stops moving. If the video features many slow-moving objects, or objects that start and stop frequently, the user may want to increase this parameter.</td>
</tr>
<tr>
<td>Minimum number of feature frames. <br /> Starting value: 15 <br /> Recommended range: 10-25</td>
<td>The minimum amount of time (in video frames) for which a feature must persist before it is considered in the next steps of the tracking process. The user may want to keep this parameter value fairly high to filter out some of the shorter-lived features (which often belong to non-road user objects, such as moving plants in the video).</td>
</tr>
</table>

## Object frames to process

<table border="1">
<tr>
<td><strong>Parameter Name and Sample Value</strong></td>
<td><strong>Parameter Description</strong></td>
</tr>
<tr>
<td>First frame to process. <br /> Starting value: 0</td>
<td>First frame of the video to be processed. Despite the variable name, frames are indexed at 0 -- if the user wishes to start from the beginning of the video, they will set this parameter to 0.</td>
</tr>
<tr>
<td>Number of frames to process. <br /> Starting value: 200</td>
<td>Number of frames to process. The user will set this so they can see at least a few seconds of video. They will be using this to test the other parameters later.</td>
</tr>
</table>

## Object-tracking parameters

<table border="1">
<tr>
<td><strong>Parameter Name and Sample Value</strong></td>
<td><strong>Parameter Description</strong></td>
</tr>
<tr>
<td>mm-connection-distance <br /> Starting value: 1</td>
<td>Maximum connection distance for feature-grouping. Connection-distance is a threshold; it is the maximum world distance at which two features can be connected to the same object. <br /> Note that in this example, this does not mean that the maximum size of an object is 1 meter! Rather, this means that a feature greater than 1 meter away from this object cannot be considered a part of this object.</td>
</tr>
<tr>
<td>mm-segmentation-distance <br /> Starting value: 0.7</td>
<td>Maximum segmentation distance. Segmentation-distance is a threshold; it is the maximum world distance at which two features that are moving relative to each other can be connected to the same object. Again, note that this does not relate to the maximum size of an object. Rather, this means that two features that are moving at different speeds cannot be connected to the same object if they are more than 0.7 meters away from each other.</td>
</tr>
</table>
