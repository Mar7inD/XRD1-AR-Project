# Reflection

[Back - HavenAR](https://github.com/Mar7inD/XRD1-AR-Project)

[Back - EscapeRoomVR](https://github.com/Mar7inD/XRD1-VR-Project)

_Reflections_

_Written by: Martin Donchev_

## Main Contributions

- Developed both the mobile AR application and the HMD XR application independently.
- Designed and implemented core features such as markerless tracking, spatial interaction, and optimized rendering for Quest.
- Authored all DevBlog posts, covering theory, implementation details, and project progress.
- Produced video demonstrations and maintained a clear commit history throughout the semester.

## Reflection on Projects and Theory

Working alone on two XR applications was both challenging and rewarding. To build the AR project I had to grasp how the markerless tracking works underneath. Algorithms like SLAM (Simultaneous Localization and Mapping) were essential to continuously estimate device position and map the environment. Further LiDAR technology helped a lot in detecting surfaces in under bad conditions like low-light. Deepening my knowledge about the AR technology helped me understand better real-world challeges. Implementing AR Foundation allowed me to leverage plane detection better, ensuring stability in virtual object placement.

The HMD XR project introduced a different set of challenges. Developing for Meta Quest meant optimizing for 6 DOF tracking, which provides full positional and rotational freedom. This contrasted with 3 DOF systems, where only rotational tracking is available, limiting immersion. Understanding these concepts helped me design interactions that felt natural and responsive. I also explored locomotion techniques like teleportation to reduce motion sickness, a topic discussed extensively in class.

## Technical Decisions and Issues

I choose Unity 2022 for both AR and HMD projects. AR Foundation helped for AR development as it offered a lot of features out of the box. I further deepened my knowledge in how interactions work on low level. For the HMD app, adopting OpenXR ensured compatibility across devices and future-proofing. To optimize performance I implemented occlusion culling, reduced polygon counts as much as possible and used foveated rendering to try and maintain high frame rates, which were essential given the dynamic light I had in my HMD project.

Another small detail which I think make the immersion better was the audio spatialization using HRTFs (Head-Related Transfer Functions). This enhanced realism by adding sound to interactions. Simple but very impactful feature for user experience.

## Ownership and Learning Outcomes

This course strengthened my ability to:

- Understand better the theoretical knowledge behind tracking algorithms, rendering pipelines, and sensor technologies and apply them in practical implementations.
- Evaluate design decisions and consider usability, performance, and hardware constraints when developing XR solutions.
- Conceive XR applications that leverage spatial interaction to create meaningful user experiences.

Working solo required strong time management and problem-solving skills. It also gave me full ownership of the development process, from concept to prototype. Working on these projects has given me the confidence to approach XR development with both practical insight and theoretical awareness.