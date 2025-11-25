# HavenAR - Ground work

[Back - HavenAR](https://github.com/Mar7inD/XRD1-AR-Project)

[Back - EscapeRoomVR](https://github.com/Mar7inD/XRD1-VR-Project)

_Week 5 (Lab 2)_

_Written by: Martin Donchev_

# Progress

By the end of the first week and into the second, my focus was on building the core interactions for the AR app. I started with a prototype that allowed users to spawn environments on a detected plane. Users could open a menu, select an environment, drag it onto the surface, and scale it to fit different spaces. While it worked, the prototype quickly revealed areas that needed refinement. Plenty of opportunities for me to learn.

## Script Organization

Initially, I had multiple scripts handling overlapping tasks, which started to feel messy. To simplify things, I consolidated everything into a single AR Placement Manager. This script now handles drag-and-drop for both the environment objects and placeable objects, and I added a tagging system to distinguish between them.

This restructuring not only made the scripts cleaner and more robust, but also laid the foundation for future features, like dynamic object spawning and more complex interactions with and between objects.

## Scaling Objects

One of the trickiest parts was scaling, especially for complex assets like the bonfire fire effect. I learned to use mesh colliders, which allowed me to use the prefabs themselves to create more accurate colliders. Some colliders like the dog I needed to use a small trick. I created a child object and rotated it so the collider is rotated the same way as the prefab. This final result made placement smoother, though scaling remained inconsistent for some asset store models.

After trial and error, I built a new Scale Manager to allow users to scale objects individually via touch. Handling parent-child relationships was a challenge at first, but a small [PrefabIdentifier](../HavenAR/Assets/Scripts/PrefabIdentifier.cs) script solved the issue, keeping child objects aligned with their parent while staying on top of the environment.

## Handling Assets and Rendering Challenges

There were a few other surprises along the way:

- Some assets didn’t play well with the rendering pipeline, which required switching to alternative versions.
- The bonfire needed recursive resizing for its child objects, but the first approach added too much complexity, so I adjusted the asset instead.
- Shader behavior differed between computer and mobile, especially for outlining selected objects. After debugging, I found a more robust solution that worked across platforms.

By far a lot of ground feeling was made and many of the scripts have a fallback procedures, so the application remained responsive so I could see how everything works together and debug.

An interesting observation was that some materials in my app appeared overly bright or looked unusually flat. Initially, I assumed it was an issue with my own setup, but after doing some research, I discovered that AR Foundation’s estimated light intensity doesn’t always quite match the real-world lighting conditions.

## Audio
I spend some time debugging and trying to resolve the issue with not hearing audio when I build the app on my iPhone and after research on the internet I found out that the mute switch must be toggled off in order to hear the sounds. So the sounds now are in place and I can here them.


## Panel workflow
The environment and object panels were overlapping is both buttons were clicked and the object were able to be spawned multiple times in one environment. After some thinking and consideration I come up with clear panel flow. Where as expected you start with selecting your environment and then you are able to select objects you want to place. Further I blocked buttons of already spawned object and visualizing that with a red box around the button picture. This workflow made the process of creating environment more focused. Instead of not sure about rules of objects and can they be spawned on top of land or not now the user is forced to chose environment and then spawn its objects.

## Plane detection challenge

When the environment lacked texture or had poor lighting, it became much more difficult for visual SLAM to support accurate plane detection. This happened because the system couldn’t find enough reliable feature points to properly analyze the surface. Since I also had access to an iPhone equipped with a LiDAR sensor, I repeated the same tests to compare the results. The difference was clear: in challenging scenarios, SLAM benefits greatly from the additional depth information provided by LiDAR.

With LiDAR enabled, plane detection was noticeably easier because it doesn’t rely on visual features alone. Instead, it emits depth-measuring pulses, allowing the device to map surfaces even in feature-poor or low-light environments.

Overall, this experiment highlighted how LiDAR—and additional sensors like the IMU (accelerometer + gyroscope)—enhance AR tracking robustness and reduce the dependency on strong lighting or detailed surfaces.