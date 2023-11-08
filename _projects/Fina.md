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
    image_path: /assets/img/projects/fina/Hand_Tracking_Possiblities_Fina.gif
    alt: "Fina 1"
    title: "Fina 1"
  - url: 
    image_path: /assets/img/projects/fina/Ray_Casting_Kebab_Fina.gif
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

<br>

### Raycasting in File Management

File management in the Meta Quest 2 is currently almost exactly the way it would be on a 2D touchscreen device. Notice the presence of kebab menus for basic tasks like delete and the lack of basic tasks like move or copy.

{% include gallery id="gallery1" caption="The Raycasting interaction method. Source: Meta.com" %}


## File Management

### Let's not reinvent the wheel

When displaying text-based interfaces, a rectilinear layout is the most practical and efficient way to organise elements. So, if we are to design a truly immersive experience that remains usable and efficient, we need to follow some guidelines of 2D design. A 3 dimensional, 6 degrees of freedom interface would be fun to conceptualize but would also probably be extremely unusable with larger organizational systems.

<figure class="align-center" style="width:100%;">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/img/projects/fina/fina1.png" alt="fina3">
  <figcaption>We designed a 2.5D interface — two-dimensional UI with an additional interactive plane on top</figcaption>
</figure>

### Our two core interactions are —

<div class="ulist" markdown="1">
- **Pinching:** Pinching is the act of picking a single object — making a precise choice — so we used it as a metaphor for selecting and manipulating individual items.

- **Grabbing:** Grabbing is done to grasp larger objects, maybe to command objects to compress or fall together. Thus, we used grabbing as a metaphor to manipulate a group of multiple files.
</div>

<br>

## Interactions

### Selecting individual files

Pinch an item and pull it towards you to select it. To select multiple files, pinch and pull each file that you want to select. All selected files will stay on the Active Plane.

<figure class="align-center" style="width:100%;">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/img/projects/fina/fina2.png" alt="fina4">
</figure>

<!-- - Murugan A., Vanukuru R., and Pillai J.S. (2021). Towards Avatars for Remote Communication using Mobile Augmented Reality, in: IEEEVR 2021 (In press) -->





