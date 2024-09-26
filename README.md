# Intro to XR Design with Bezi Workshop
A Carolina AR/VR workshop that will teach you how to design XR experiences in Bezi – created by Ashley Neall, Stratton, and Arryn O'Brien.

## An Introduction
This workshop introduces students to extended reality (XR) design within **Bezi** – a web-based 3D UI/UX design tool used to plan out mobile, AR, VR, and MR experiences for XR various platforms. Since this workshop is only one hour long, **you _must_ ENTIRELY complete the pre-workshop setup below BEFORE THE WORKSHOP BEGINS**!

## Pre-Workshop Setup
Please make sure to complete the following steps ***before* the workshop begins**, as you will not have time during the workshop. Don't worry, everything below is free and **no downloads** are required!

### Initial Setup
1. Bookmark this repository (as you will be using its assets during _and_ after our workshop)!
2. Join the [Carolina AR/VR Discord server](https://discord.gg/cYseCtevW9).
3. Watch this short [**Welcome to Bezi**](https://www.bezi.com/bezi-101) video.
4. Create a Bezi account.
5. (Optional) Read this guide to [design visionOS apps](https://www.bezi.com/apple-vision-pro-guide) with Bezi.
6. Bring a **laptop** _(and preferably a mouse)_, and your excitement!

## Workshop Steps
### Setup XR Scene
1. Login to your Bezi account
2. Navigate to Drafts and click **New File**
4. Under New Scene, select **AR Ready Scene**
5. Double-click 'Body Rig 1' and rename it to **XR Rig**

### Create a Piano Key
1. In the top navigation bar, click the **Objects** tab
2. Select **Box**, then drag your cursor into the 3D viewport and click multiple times to create the initial dimensions of the box (i.e. cube)
3. Change the cube to the following measurements:
  * Scale – X = 0.12, Y = 0.14, Z = 1.71
  * Box - W = 1.44m, H = 0.68m, D = 0.44m
4. Now your cube should appear to be the size of a piano key
5. Place the rescaled cube (i.e. now a rectangular prism) in front of the user (i.e. XR Rig camera):
  *  Position – X = 0m, Y = 1m, Z = -0.25m
5. Rename the 'Box' to **Key**

### Set up the State Machine
1. Click on the piano key (**Key**)
2. In the bottom naviagtion bar, click the **State Machine** tab
   * _You will see a **Start** and a default **Base State**_
3. Click **New State** to add a new state, then rename it from 'State 1' to **Press State**
5. Click on **Base State** and drag to connect an arrow pointing toward **Press State**
6. Click on the transition arrow _(pointing toward Press State)_ and change 'Pointer down' to **direct touch inside**
7. Click on **Press State** and drag to connect an arrow pointing toward **Base State** and change 'Pointer down' to **direct touch outside**
8. Make sure that the only object added to both transitions is the one called "self", thus signifying that it is the key that should be touched to activate the change

### Add Changes to the State Machine
1. Click the **Key** object and open the State Machine again
2. Select **Press State** and change the following:
  * Position – Lower the Y position slightly
  * Material – Change the color to something other than white, like red or pink

(TODO: Finish instructions)


### Contact Information
* Ashley Neall – aneall@unc.edu
* Arryn O'Brien – arrynco@unc.edu
