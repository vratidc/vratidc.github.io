---
title:  "Mobile Social AR"
excerpt: Remote AR Environment
layout: projects
selected: "false"
homepage: "false"
fullpage: "yes"
active: "no"

header:
    teaser: /assets/img/projects/Scholar/scholar_thumbnail.jpg
tags: AR Research

banner_image1: 
banner_image1_caption:

team_members: "<strong>Current Members</strong> : Amarnath Murugan | Rishi Vanukuru | Amal Dev | Pratiti Sarkar | Jayesh Pillai"
team_members_align: "text-left"

permalink: projects/mobilesocialar

flexgallery1:
  - aspect: "0.7218"
    url:
    image_path: /assets/img/projects/Scholar/scholar_lines1.jpg
    alt: "scholar_lines1"
    title: "scholar_lines1"
  - aspect: "0.9557"
    url:
    image_path: /assets/img/projects/Scholar/scholar_lines2.jpg
    alt: "scholar_lines2"
    title: "scholar_lines2"
  - aspect: "1.4668"
    url:
    image_path: /assets/img/projects/Scholar/scholar_lines3.jpg
    alt: "scholar_lines3"
    title: "scholar_lines3"

flexgallery2:
  - aspect: "1.1441"
    url:
    image_path: /assets/img/projects/Scholar/scholar_presentation1.jpg
    alt: "scholar_presentation1"
    title: "scholar_presentation1"
  - aspect: "0.8661"
    url:
    image_path: /assets/img/projects/Scholar/scholar_presentation2.jpg
    alt: "scholar_presentation2"
    title: "scholar_presentation2"
  - aspect: "0.8603"
    url:
    image_path: /assets/img/projects/Scholar/scholar_presentation3.jpg
    alt: "scholar_presentation3"
    title: "scholar_presentation3"

flexgallery3:
  - aspect: "1.38302"
    url:
    image_path: /assets/img/projects/Scholar/scholar_school3.jpg
    alt: "scholar_school3"
    title: "scholar_school3"
  - aspect: "2.491"
    url:
    image_path: /assets/img/projects/Scholar/scholar_tata1.jpg
    alt: "scholar_tata1"
    title: "scholar_tata1"
  - aspect: "1.38302"
    url:
    image_path: /assets/img/projects/Scholar/scholar_school4.jpg
    alt: "scholar_school4"
    title: "scholar_school4"


---

<figure class="align-center" style="width:100%;">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/img/projects/socialAR/banner.jpg" alt="A remote AR session">
</figure> 

This project was the result of us bridging the work done through [ScholAR](/projects/scholar){:target="_blank"} for physical calssrooms to remote learning; hoping to address some of the challenges imposed by the pandemic on teaching. With relatively less exploration in remote handheld AR, we were also presented with intersting design challenges that extend beyond educational use cases.

<br>

## Introduction

The COVID-19 pandemic has essentially forced all communication to happen through virtual media. While video conferencing has improved considerably over the course of the lockdown and is the primary tool for synchronous remote activities, it lacks the spatial dyanmics of physical interactions and the social dynamics brought about by the same. Telepresence systems are thereby a desirable alternative, but the requirement of specialized & expensive hardware (HMDs) has made the high end options unscalable for the time being. Through this project we explore the use of mobile social AR as a relatively more accessible telepresence system. With more devices supporting ARCore/ARKit, their spatial movement and orientation obtained from tracking could be used to create shared spaces for multiple people. 

As an offshoot from the ScholAR project, our first prototype focused on creating a virtual calssroom where the teacher is able to display a shared artefact and teach concepts to students who are spatially present in the virtual space. Spatial audio and visual cues were added to give a better sense of the relative position of other users. Depending on the active artifact, the users could place a marker or draw on top, and these interactions are reflected for everyone in the session. We had conducted preliminary tests with students from our department to better understand the opportunities and challenges in this space. 


<figure class="align-center" style="width:100%;">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/img/projects/socialAR/banner.jpg" alt="Students in our first prototype">
  <figcaption>IDC Students using our first prototype</figcaption>
</figure> 

## Research Directions

While there's a huge body of work on collaboration and remote communication in mixed and virtual reality, but they may not be entirely applicable to mobile AR due its lower level of immersion and the affordances of the tech itself. Furthermore, from our tests we have identified the following directions to focus on to establish guidelines for creating better mobile social AR experience.

- **Social Presence:** It is the extent to which an user feels that the other person is actually there in a shared virtual space. Higher social presence is important for the involved parties to establish rapport and communicate effectively. We would be comparing the level of social presence in mobile AR and other mediums of communication.

- **Representation:** The characteristics of the avatar used in a virtual space also influences the interatctions in that space. The challenge in accurate avatar representation is that the only information available to gague to user's pose is the handheld device's position and orientation, as opposed to their head's position & orientation of HMDs (which might also have individual controllers for each hand). We explore an avatar space that compares avatars that vary both in visual and behavioural fidelity, to understand how they affect perception.

- **Interaction techniques:** Having a shared virtual space in mobile AR, brings up new challenges in handling interactions. For example, identifying metaphors for concepts such as disabling video & breakrooms. Whilst also trying to recreate the dynamics and interactions of a physcial space. 

- **Education:** The goal of recreating a classroom through AR is central to this project, so we'd be investigating the efficacy of this medium in education and will attempt to identify topics and scenarios suited for this platform.


## Publications

- Murugan A., Vanukuru R., and Pillai J.S. (2021). Towards Avatars for Remote Communication using Mobile Augmented Reality, in: IEEEVR 2021 (In press)




