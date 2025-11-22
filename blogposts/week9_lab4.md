# EscapeRoomVR - Concept Overview

[Back - HavenAR](https://github.com/Mar7inD/XRD1-AR-Project)

[Back - EscapeRoomVR](https://github.com/Mar7inD/XRD1-VR-Project)

_Week 9 (Lab 4)_

_Written by: Martin Donchev_

## Introduction

For my VR project, I decided to create an Escape Room game. I liked this idea as it gave me opportunity to explore and showcase some of the interactive capabilities of VR technologies. The other motivation around proceeding with this idea was remembering Kasper presenting an AR example involving an extremely expensive machine that could be “reseted” with a single click if for some reason broken. In my case would be cleaning the escape room with the click of a button. 

### Goal

A critical bug has occured in the system and the servers have went in self-destuction mode. As you might guess, the overall theme of the scene will be sci-fi.

The goal will be to solve different puzzles and find out the passcode for deactivating the servers from imploding using the keypad attached to them. The player must find the correct code within the given time limit to prevent the system from imploding. Every wrong passcode brings the player more closer to failing the mission.

## Progress

I started by brainstorming potential clues. The main direction I was thinking about was what cool stuff to do in order to utilize VR interactions in the best possible way and make the experience feel unique. Something more engaging than a standard computer game but also far cheaper and more flexible than building a real-life Escape Room.

The first clue I developed was a UV flashlight. When the player shines it on certain surfaces, hidden text is revealed, guiding them toward the solution.

For a second clue I wanted to implement a chest where I could simulate a opening it by putting a key into a lock, followed by animation of opening the lid of the chest. 

The final thing I needed to think about was the keypad and how to connect all 3 together. I was not sure at this time how exactly this would be done but the one sure was that the 2 clues should reveal a passcode.

On the first day, I my main focus was on getting my workflow set up. I initially tried developing with the Quest 3 but ran into issues with controller connectivity. After some time troubleshooting, I discovered the controller batteries were simply dead. Once replaced, I finally got the headset running. This was my first time using a VR headset and it was quite new to me how everything works.

However, I quickly noticed that my laptop, while it should be meeting the hardware requirements, was still giving issues. The connection to the headset felt slightly laggy, and I kept receiving GPU-related warnings. After two to three hours of debugging, I decided to switch to the lab computer. I originally avoided it because I prefer working on my own device, but switching ended up easing my future work.

Once I was setted up, I started looking through various assets and testing them. I began by gathering the sci-fi environment pieces and building the basic scene, which took the rest of the day.

My next step will be implementing the first clue: setting up the flashlight interaction and making the hidden text appear.

## Asset and Code References:
- [Sci-fi scenery](https://assetstore.unity.com/packages/3d/environments/sci-fi/free-sci-fi-office-pack-195067)
- [Flashlight](https://assetstore.unity.com/packages/3d/props/electronics/free-flashlight-293680)
- [Keypad](https://assetstore.unity.com/packages/3d/props/electronics/keypad-free-262151)
- [Chest, lock and keys](https://assetstore.unity.com/packages/3d/environments/dungeons/n-gonforge-dungeon-low-poly-303819)
- [Sounds](https://pixabay.com/)
