# EscapeRoomVR - Wrappiing up

[Back - HavenAR](https://github.com/Mar7inD/XRD1-AR-Project)

[Back - EscapeRoomVR](https://github.com/Mar7inD/XRD1-VR-Project)

_Week 11 (Lab 6)_

_Written by: Martin Donchev_

## Progress

### Creating the Chest Clue

My last week began with working on the chest clue.

First, I placed the chest behind one of the server racks so it wouldn’t be too easy to spot. I added a text hint on the bottom of the chest. 

For both the light clue and the chest clue, I decided to give the player small tasks:

- The light clue required counting the rugs and trays in the room and multiplying the numbers, providing the first two digits of the passcode.

- The chest clue was a simple math problem where the player had to divide the number of degrees in a circle by 10.

Once the chest was set up, I positioned the lock inside the hole and added an XR Socket Interactor with an attach point where the key should snap into place when inserted.

Originally, I placed the key on one of the trays located on top of a shelf in the first room. Then I had a better idea—why use only one key? It would be much more interesting to scatter multiple keys around the environment and make the player search for the correct one.

With that idea, I began writing the interaction scripts. These scripts make setting up objects much faster: you simply attach the script, and it configures everything automatically when the game runs.

- [Key](https://github.com/Mar7inD/XRD1-VR-Project/blob/main/EscapeRoomVR/Assets/Scripts/Key.cs) script: Makes the key interactable in VR and assigns it an identifier so the lock can verify whether it’s the correct one.

- [Lock](https://github.com/Mar7inD/XRD1-VR-Project/blob/main/EscapeRoomVR/Assets/Scripts/Lock.cs) script: Checks the key, triggers the chest to open, configures the XR socket, and destroys the lock once it has been unlocked.

- [Chest](https://github.com/Mar7inD/XRD1-VR-Project/blob/main/EscapeRoomVR/Assets/Scripts/Chest.cs) script: Handles the lid-opening animation, including speed and stopping point, since the full animation both opens and closes the chest.

### Audio enhancement

For the VR game to be more immersive I added special effects to the object interactions. When you put the key in the lock you hear a sound after which you hear unlocking the lock if the key is the right one and finally you hear how the chest is opening. Another example is with the flashlight which you can hear the on/off sound when switching the light. Adding this sound really enhanced the immersive feeling as I was ensured with one more sense that the action I did was received. 

### Keypad - Non-VR interations

Next, I moved on to finding the final component—the keypad. I found a well-designed model, but reviews mentioned that people had trouble integrating it with VR and implementing proper VR interactions. I decided to try anyway. My idea was to use a raycast approach similar to what I used in my AR project.

I added an XR Raycast Interactor to the XR Origin so the button presses could be detected. Then I created a KeypadButtonXR script to handle VR interactions using XRSimpleInteractable. The buttons already had colliders, so no changes were needed there. When I tested it, everything worked smoothly, which made me happy because I really liked how the model looked.

After that, I created a TimerManager script responsible for counting down the time and displaying the end screen. I connected it to the keypad so it could be triggered when the player enters the correct code—or reduce time if the code is incorrect. I placed the timer text above the door so it’s one of the first things the player notices.

Finally, I played through the game several times from start to finish to test and fine-tune all the functionalities.