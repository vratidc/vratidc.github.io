---
title:  "Manhole VR"
excerpt: A Virtual Reality 6 DoF Narrative Experience
layout: projects
selected: "false"
homepage: "false"
fullpage: "no"
active: "no"

header:
    teaser: /assets/img/projects/socialAR/socialAR_thumbnail.jpg
tags: VR Research

banner_image1: 
banner_image1_caption:

team_members: "<strong>Current Members</strong> : Jayesh Pillai | Abhishek Verma | Banda Shiva Teja | Uttham Prakash | Ananda Bathena"
team_members_align: "text-left"

permalink: projects/manholevr


gallery1:
  - url: 
    image_path: /assets/img/projects/socialAR/socialAR_screen1.gif
    alt: "Social AR 1"
    title: "Social AR 1"
  - url: 
    image_path: /assets/img/projects/socialAR/socialAR_screen2.gif
    alt: "Social AR 2"
    title: "Social AR 2"


---

<figure class="align-center" style="width:100%;">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/img/projects/socialAR/socialAR_banner.jpg" alt="A remote AR session">
</figure> 

Hoping to address some of the challenges imposed by the pandemic on education, we have been adapting our work on the [ScholAR](/projects/scholar){:target="_blank"} project (that focused on physical classrooms) to better support remote learning. While doing so, we have also been presented with interesting design challenges that extend beyond educational use cases, as not much research has explored the use of mobile AR to enable remote collaboration.

<br>

## Introduction

The COVID-19 pandemic has forced all communication online, and video conferencing is currently the primary tool for synchronous remote activities. While the medium has improved considerably over the course of the lockdown, video calls sorely lack the spatial and social dynamics of physical, in-person interactions. This problem is addressed to some extent by more immersive alternatives that make use of head-mounted Virtual and Augmented Reality displays, but such options are still quite inaccessible and unscalable at present.

Mobile Augmented Reality could serve as an ideal midpoint--a medium that can support some of the spatial, immersive interactions in more high fidelity XR experiences, while also being available to many more people, given the increasing number of mobile devices that are capable of markerless AR.

Through this project, we are exploring the use of mobile social AR experiences to support remote learning and collaboration. 

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





