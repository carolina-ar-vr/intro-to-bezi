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
1. In the top navigation bar, click the **Objects** button. It should look like a cube.
2. Select **Box**, then drag your cursor into the 3D viewport and click multiple times to create the initial dimensions of the box (i.e. cube)
3. Your goal here is to make it look similar to a piano key in shape and size, but large enough that the player's entire hand would fit on it (reference the XR rig for scaling).
  * A good example size is a width of about 0.5m, a height of about 0.3 m, and a depth of about 2.3 m.

![image](https://github.com/user-attachments/assets/5ab757a2-cf2d-4f5c-adfc-b98f9fd5b04e)

6. Place the rescaled cube (i.e. now a rectangular prism) in front of the user (i.e. XR Rig) as in the image below:

![image](https://github.com/user-attachments/assets/8a00176c-aa1a-45a0-b867-aa13f2dae62a)

5. Rename the 'Box' to **Key**
6. With **Key** selected in the scene, look over at the right side panel, which should show various properties. To the right of **Colliders**, press the _plus_ icon to add a new collider. It should default to "Box", which is what we want. This collider is necessary for detecting the collisions of the controller, which we'll set up next.

![image](https://github.com/user-attachments/assets/7672d28d-1392-4ca3-aa0c-30d0889d3289)

### Set up the State Machine
1. Click on the piano key (**Key**)
2. In the bottom naviagtion bar, click the **State Machine** tab
   * _You will see a **Start** and a default **Base State**_
3. Click **New State** to add a new state, then rename it from 'State 1' to **Press State**
5. Hover under the base state box and you should see a small yellow-green circle. Click and drag that circle down to the **Press State** you just created to connect it.
6. Click on the transition arrow _(pointing toward Press State)_ and change 'Pointer down' to **direct touch inside**
  * It should be so by default, but ensure that the trigger object shows "Self" and nothing else. This is the object that triggers the change in state, and **Self** refers to the object that this state machine is attached to.
8. Hover just above **Press State** to where you see that same circle from before and drag to connect an arrow pointing toward **Base State** and change 'Pointer down' to **direct touch outside**
  * Again, ensure that the trigger object is set to _Self_.

![image](https://github.com/user-attachments/assets/74dd0da5-1040-406b-b549-657b6b592e45)
![image](https://github.com/user-attachments/assets/78eafede-09bd-40b5-b814-684d3225620a)

### Modify the Pressed State
1. Click the **Key** object and open the State Machine again.
2. Select **Press State** and, with it selected, change the following:
  * Position – Lower the Y position slightly.
  * Material – Change the color to something other than white, like red or pink.
3. The goal with these modifications is to have the Key's properties change to these new properties whenever it transitions to the **Press State**. Verify that it's set up correctly by clicking back and forth between **Base State** and **Press State**. You should see the piano Key change back and forth between your two configurations.

![b7070ac75bdae3835af647dce1147837](https://github.com/user-attachments/assets/cc87eba0-da8c-4639-afcf-ea2abbea4ec8)

### Adding the Audio
1. Click the Object button on the top navigation bar again, and add a **Spatial audio** this time.

![image](https://github.com/user-attachments/assets/55649614-1f35-431c-b7fd-015927392c6f)

2. Click in the scene where you want to place the audio object (i.e., where the sound will come from). If you want to move it, you can do so in the same way you moved the piano key from earlier. Center this sound inside the key, as we want it to sound like it comes from the key itself.
3. Rename this spatial audio to "Audio".
4. Select both the **Key** and the **Audio** in the scene by clicking one and then ctrl + clicking the other.
5. With both of them selected, either right click them and press "Group", or press ctrl + G.

![image](https://github.com/user-attachments/assets/e71e39a0-d620-4a54-8555-0a2e2675c141)

6. Rename this new group "C", as we'll set it up to be the C note on a piano.
7. Expand the group in the scene panel on the left to select the Audio again, and open up the State machine once again.
8. Just like before (_with **Audio** selected_), create a new state, call it "Press State", and click on the arrow to modify the trigger settings.
9. Change "pointer down" to "direct douch inside" again.
10. This time, hover over "self" under **Trigger objects** until you see this little circle/aiming icon on the right. Click that icon, and then select the piano key (in the **Scene** panel on the left is probably easiest).
  * _This is important because, in this case, "Self" refers to the **Audio**, rather than the **Key**. We want this state change to be triggered when the **Key** is interacted with, rather than the **Audio** (as the audio has no collisions)._

![image](https://github.com/user-attachments/assets/d9975fee-8ddc-40a3-b3bc-9641c23948b6)

11. Connect the **Press State** back to the **Base State**, just like with the piano key, and set this trigger to "dierct touch _outside_" instead of inside. Make sure you change "Self" To "Key" again, just like before.

![image](https://github.com/user-attachments/assets/1e7fc5e8-c791-44bf-b1ea-2d814cf57a0e)

12. Now, with the **Audio** selected, move over to the properties panel on the right, and under **Audio**, you can see that it's set to the default audio "Success 1". You can click the play button to test this audio and hear it played on your device, but we want to click the name of the audio in order to swap it out for the piano audio.
13. Select the dropdown that should say "This File", and switch it to "Bezi Library".

![image](https://github.com/user-attachments/assets/e87836cc-bba1-49cc-b99d-f25511606c31)

14. Scroll down until you find "Music Note C1", and select it. You may have to scroll all the way down, and then scroll back up (sometimes it has weird issues with loading all of the audio files).

![image](https://github.com/user-attachments/assets/097762d8-aaac-4a65-9de9-be13d2498e5e)

15. Open the state machine again, with the **Audio** selected. Select **Base State**, and then in the properties, make sure the audio is set to "Stopped" and "Play once".

![image](https://github.com/user-attachments/assets/01816484-e74c-4f38-9a45-1b98ed9a279b)

16. Select **Press State**, and change "Stopped" to "Playing". This will set up the audio such that it will play when it's triggered to **Press State**, and won't play when it's back at **Base State**.

### Testing the First Key


(TODO: Finish instructions)


### Contact Information
* Ashley Neall – aneall@unc.edu
* Arryn O'Brien – arrynco@unc.edu
