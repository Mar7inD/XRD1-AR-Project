# EscapeRoomVR - First clue and lightning challenges

[Back - HavenAR](https://github.com/Mar7inD/XRD1-AR-Project)

[Back - EscapeRoomVR](https://github.com/Mar7inD/XRD1-VR-Project)

_Week 10 (Lab 5)_

_Written by: Martin Donchev_

## Progress

### Ligthning setback

Last week, I started assembling the scene and arranging the environment. I also found some good flashlight models on the Asset Store, which I decided to use for what I call my light clue.

When I imported the flashlight, it came as a simple model without an actual light component, so I added a spotlight to the front with increased intensity. However, the light wasn’t projecting onto the walls as expected.

I began debugging by checking whether the spotlight itself was working and whether my [FlashlightToggle](https://github.com/Mar7inD/XRD1-VR-Project/blob/main/EscapeRoomVR/Assets/Scripts/FlashlightToggle.cs) script was correctly triggering the light on and off. After that, I tested various lighting settings such as lightmaps, the position of the main directional light, and the sci-fi lamps from the asset pack.

In the end, the solution was to reposition the spotlight slightly lower, adjust its direction, and remove shadow settings from the sci-fi lamps, as they were interfering with the flashlight. I also changed all lights to baked, which noticeably improved the game’s frame rate. With these adjustments, the scene lighting looked correct and the flashlight became visible when activated.

### VR Controlls for flashlight

To make the flashlight interactable using the VR controllers, I added an XR Grab Interactable component and placed a grab point on the back of the flashlight so it is always held correctly. When the player grabs it, it snaps naturally into their hand.

I also added a cookie texture to the flashlight’s light emission to make the beam look more realistic when it hits surfaces. To enhance immersion further, I included switch on/off sound effects for toggling the flashlight.

### UV text

As mentioned earlier, the [FlashlightToggle](https://github.com/Mar7inD/XRD1-VR-Project/blob/main/EscapeRoomVR/Assets/Scripts/FlashlightToggle.cs) script handles all flashlight interactions.

To make the hidden text appear and disappear, the script modifies the alpha value of the text’s color. It uses colliders on both the flashlight beam and the text objects to detect when the light hits them. When illuminated, the alpha increases to 100%.

The script also keeps a list of objects tagged as ReactiveText and resets their alpha to 0 when the flashlight is turned off. This was necessary because I found that turning off the flashlight while still pointing at the text would otherwise leave it visible.

### Flashlight Falling Trough the Ground

At one point, the flashlight occasionally fell through the floor. After experimenting with the Rigidbody settings, I fixed the issue and also improved the physical behaviour—now it drops more realistically, with better bounce and fall timing.

### Concern around performance

Since I used dynamic lighting for the flashlight, I was worried about staying within the batch and triangle limits that our teacher, Kasper, had set. Keeping the scene lightweight would ensure enough computational headroom for the dynamic light to not influence the overall perform. In the end, even with all the sci-fi assets included, the flashlight system ran smoothly on the Quest 2. I was really happy with the result, especially because it turned out to be a fun and rewarding challenge.

### Started Working on the Second Clue

I began searching for the next clue, which required a chest with a key and lock. It took some time, but after browsing several assets, I finally found one that fits my needs.

With that, my fifth lab week came to an end. Next week, I hope to assemble everything and test whether all the mechanics work properly. I still need to implement the keypad and make the chest unlock and open.