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

## Slides
[Intro to XR Design with bezi slides](https://www.canva.com/design/DAGR4bksGxw/EgbHZYzkK3NQhLEQJvkb5Q/edit?utm_content=DAGR4bksGxw&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton)

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
Before moving on to copying this key to create the rest of the keys, we'll want to make sure what we have so far actually works, so as to save us some time.
1. Grab a headset (anything that can use a browser will likely work, such as a Quest 2, 3, Pro, etc.), and power it on.
2. Ensure you're connected to the internet (at UNC, you need to have the headset set up with the PSK network, but if you're using a CARVR headset, hopefully it's already set up).
   * _If you're not connected to the internet, feel free to send a message in the Discord server, or make use of the contact information down below, and one of us can help you with it._
3. Back on your computer/laptop, click the arrow next to "Play" on the top right of your screen, and click the "Headset" button.
   * You should see a code, similar to in this picture:

![image](https://github.com/user-attachments/assets/0d829d3b-5c17-43a1-af81-415894e99f0a)

4. On your headset, open up the browser, navigate to bezi.com/connect, and then enter the code shown on your computer screen.
5. After entering the code, it should show the scene you just created with the piano key simply in the browser. In order to actually enter the scene, you need to press the headset icon near the top right:
 
![immersive mode](https://github.com/user-attachments/assets/d4015520-a6d7-47b0-9816-73fb2bdc9807)

6. After entering this mode, you should be prompted to "place your scene". Look where you want the center of the scene to be placed, and either click one of the triggers on your controllers or pinch your fingers (if using hand tracking) to confirm the location.

![image](https://github.com/user-attachments/assets/9dbe0e72-06df-48ec-bd9c-81b211572e0e)

7. After placing the scene, you should be able to use the left trigger to move around horizontally, and the right trigger to move up and down, in case you're too far from the key to reach it. Upon getting close enough to the key, put your controller inside the key, and it should change color, move down slightly, and play a sound.

https://github.com/user-attachments/assets/dcea905b-b7a1-42b7-a3e5-f42df912c1eb

8. If any of that didn't work correctly, here's some troubleshooting tips:
   * Ensure the key has a collision added to it of the type "Box".
   * Ensure the key has both the Base State and Press State, and that the trigger to the _Press State_ is set as "direct touch inside", and the trigger to the _Base State_ is set as "direct touch outside". Also verify that both of these have the **Trigger objects** set to just "self".
   * Ensure the same as above but for the **Audio** object, except ensure that the **Trigger objects** is set to **Key** rather than self, for both the *to* and *from* transitions.
   * Ensure each state is configured appropriately:
      * Pressed State on the **Key** should move it down a little and change the color.
      * Pressed State on the **Audio** should change it from "Stopped" to "Playing".
   * If you're still having issues after verifying the above, feel free to contact one of us below for questions.

### Adding More Keys
Now that we have the first key working correctly, all we need to do now is add the rest of the keys.
1. Select the group that you renamed to "C", and press Ctrl + D to _duplicate_ it. Alternatively, right click it and press "Duplicate".
2. Move the new group that was created slightly to the **right** of the first key.
3. Rename this group to "D".
4. Select the **Audio 1** (it usually renames it) inside the new group **D**, and change the audio file from **Music Note C1** to **Music Note D**. Again, you may need to scroll down and scroll back up for it to appear.
5. With **Audio 1** still selected, open the State machine again, and select the trigger from **Base State** to **Press State**.
6. Change the **Trigger objects** to the new **Key 1** that's inside group **D**. When you duplicate the group, it doesn't connect the trigger objects properly, and so you have to correct it manually.
   * It leaves the new audio connected to the old key by default.
7. Do the same for the trigger from **Press State** to **Base State**, so that it's using the new **Key 1** as the trigger object for both directions.
8. Repeat steps 1-7 to create keys for the notes E, F, G, A, B, and C2. C2 is just the same as C1 but an octave higher in pitch, which completes the C major scale.
9. Select all of the groups, which should be named C, D, E, F, G, A, B, C2 from left to right, and group them either by right clicking or pressing ctrl + G like before.
10. Rename the group to "Keys".
11. Test it out again in your headset, following the same instructions from before!
12. (Optional) Play "Mary Had a Little Lamb": E D C D E E E, D D D, E G G, E D C D E E E E D D E D C

https://github.com/user-attachments/assets/5fdcbae9-1dc0-4735-a3f3-bc82a2fe4db4

### (Optional) Adding Black Keys (i.e. sharps and flats)
Following the same process as before, you can also add the black keys on a piano as well, giving you the full range within one octave, rather than just the C major scale.
1. Duplicate the group called C.
2. Rename the new group C#/Db (c sharp / d flat).
3. Position that new key between the first two keys (C and D), and move it upward slightly, and also back slightly.
4. Reconfigure the **Audio** object in this new group to have the correct key set as the trigger object, and set the sound to **Music Note D Flat C Sharp**.
5. Select the **Key** object inside the group, open the state machine and select the "Base State", and then color the key black.

![image](https://github.com/user-attachments/assets/9e02fbfb-7cd1-4ba3-a6ed-ca0d4ae1f7a3)

6. Copy this group over to the right between the 2nd and 3rd keys, setting it to **Music Note D Flat E Sharp**, and renaming it to "D#/Eb".
7. Then skip the black key between the 3rd and 4th notes, and add another between the 4th and 5th, selecting **Music Note G Flat F Sharp**, and renaming it accordingly as well.
8. Then add one between the 5th and 6th notes, setting it to **Music Note A Flat G Sharp**.
9. Now Do one between the 6th and 7th, setting it to **Music Note B Flat A Sharp**.
10. Test it out again! Now you can play a one octave chromatic scale (playing all the pitches consecutively, either to the right or to the left)!

![image](https://github.com/user-attachments/assets/27027769-52ce-453a-b5ad-0768899ca3cb)

https://github.com/user-attachments/assets/8a665782-aec7-4ace-a927-39a16978806b

## Example Play Link
Here's where you can test out the project I built in writing these instructions: [Bezi Workshop Completed](https://bezi.com/play/82415c29-145c-4b9f-9902-63e2f1e9e9a4)

### Contact Information
* Ashley Neall – aneall@unc.edu
* Arryn O'Brien – arrynco@unc.edu
