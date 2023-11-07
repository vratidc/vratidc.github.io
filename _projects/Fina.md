---
title:  "Fina: File Management Interactions"
excerpt: Real-Time VR Film
layout: projects
selected: "false"
homepage: "false"
fullpage: "no"
active: "no"

header:
    teaser: /assets/img/projects/socialAR/socialAR_thumbnail.jpg
tags: AR VR Research

banner_image1: 
banner_image1_caption:

team_members: "<strong>Current Members</strong> : Atish Waghwase | Prafulla Chandra GS | Cherian Jeremiah Iype | Apoorv Anurag"
team_members_align: "text-left"

permalink: projects/fina


gallery1:
  - url: 
    image_path: /assets/img/projects/socialAR/Hand_Tracking_Possiblities_Fina.gif
    alt: "Fina 1"
    title: "Fina 1"
  - url: 
    image_path: /assets/img/projects/socialAR/Ray_Casting_Kebab_Fina.gif
    alt: "Fina 2"
    title: "Fina 2"


---

<figure class="align-center" style="width:100%;">
  {% include video id="_9cq1qVikcU" provider="youtube" %}
</figure> 

Given that UI in popular VR headsests still uses raycasting as the default interaction method, we imagine, prototype and showcase how interactions can be made more tangible and literal by utilising full hand tracking by designing a file management scenario.

<br>

## Introduction

As technology is improving, hand-tracking is getting more robust and reliable enough to be implemented on mobile standalone devices with sparse sensors such as the Meta Quest 2. Hand-tracking is a huge leap in immersion and interaction as it breaks extra layer of controller mapping; instead of the user interacting with the controller and the controller affecting the visuals, we can now directly interact and affect the visuals directly using our hands.

Raycasting is the most common UI interaction technique in virtual reality in 2022. It resembles real-life pointing with a laser pointer - the user points a ray of light at the target and confirms its selection by pressing a button on the controller - not unlike a traditional computer mouse. Mouse interactions are bound by physical and technical constraints, but VR interactions don’t have to be.

{% include gallery id="gallery1" caption="IDC Students using our first prototype" %}

As an offshoot from the ScholAR project, our first prototype focused on creating a virtual classroom where the teacher is able to control a shared AR artefact and teach concepts to students who are spatially present in the virtual space. Visual cues & spatial audio were added to give a better sense of other users' relative position. Depending on the active artifact, the users could place a marker or draw on top, and these interactions are reflected for everyone in the session. We had conducted preliminary tests with students from our department to better understand the opportunities and challenges that arise as a consequence. 

{% include video id="FhA2svVtDHk" provider="youtube" %}
<figcaption>Explainer video - Remote collaboration in AR - Teacher + multiple students interaction</figcaption>
<br> 

## Research Directions

While there is a huge body of work on collaboration and remote communication in mixed and virtual reality, their design ideas and findings may not be directly applicable to mobile AR, due to its lower level of immersion, and the affordances of the technology itself. From our initial tests, we have identified the following directions to focus on, in order to establish guidelines for creating better mobile social AR experiences.

<div class="ulist" markdown="1">
- **Social Presence:** This refers to the extent to which a user feels that another person is actually 'present' in a shared virtual space. Higher social presence is important for the participants to establish a rapport and communicate effectively. We plan to compare the level of social presence in mobile AR and other mediums of communication.

- **Representation:** The characteristics of the avatar used in a virtual space also influence the possible interactions in that space. The challenge in the case of mobile AR is that the only information available to gauge a user's pose is the handheld device's position and orientation, as opposed to their head's position & orientation when using Head Mounted Displays (which might also have individual controllers for each hand). We explore an avatar space that compares avatars that vary both in visual and behavioural fidelity to understand how they affect perception and presence.

<figure class="align-center" style="width:100%;">
  <img src="{{ site.url }}{{ site.baseurl }}\assets\img\projects\socialAR\avatarspacereduced.png" alt="ScholAR School">
  <figcaption>Proposed avatar space</figcaption>
</figure> 

- **Interaction techniques:** Having a shared virtual space in mobile AR brings up new challenges in handling interactions. For example, identifying metaphors for disabling audio and video, personal chat, among breakout rooms among others.

- **Applications to Education:** The goal of recreating a classroom through AR is central to this project, so we will be investigating the efficacy of this medium in comparison to the status quo of group video calls, and attempt to identify topics and scenarios best suited for such an AR platform.

</div>

## Publications

- Murugan A., Vanukuru R., and Pillai J.S. (2021). Towards Avatars for Remote Communication using Mobile Augmented Reality, in: IEEEVR 2021 (In press)





