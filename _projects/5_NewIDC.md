---
title:  "Navigation for ArchViz in VR"
excerpt: Architecture VR Walkthrough
layout: projects   
selected: "false"
homepage: "false"
fullpage: "yes"
active: "yes"

header:
    teaser: /assets/img/projects/newidc_thumbnail.jpg
tags: VR  

team_members: "Arun Babu | Rishi Vanukuru | Amarnath Murugan | Jayesh Pillai"
team_members_align: "text-left"
permalink: projects/archviznavigation

flexgallery1:
  - aspect: "1.23319"
    url: 
    image_path: /assets/img/projects/archviz/idc50_1.png
    alt: "IDC50 Demo"
    title: "IDC50 Demo"
  - aspect: "1.26"
    url: 
    image_path: /assets/img/projects/archviz/idc50_2.png
    alt: "Demo next to miniature"
    title: "Demo next to miniature"
---

This project was taken up by Arun Babu as part of his M.Des Design Exploration Seminar (DES) 



## Abstract

Architectural Visualization is one of the core applications of VR, where stakeholders can see and decide on various elements of the building while planning. This helps in understanding how the building could look like after construction. This can lead to increased client satisfaction and speed up the development process as visualising the elements in VR really gives the feeling of being there. This project aims at giving a better experience to the users in terms of navigation and visual
fidelity. We chose to go with the upcoming building near IDC to visualize.

## The Experience

{% include video id="1NAZrbuHWj_LwO8WrOc7InN0UQ2SdZBCa" provider="google-drive" %}
<figcaption>Navigation demo</figcaption>

## Components of Navigation

Mutliple interactions and navigational elements were integrated in this project to allow people to explore and move around the space better

### Teleportation

A common interaction in VR, which allows to traverse large virtual spaces while the user's phyical space is limited.

### Handheld Map

An interactive map was attached to the left controller, and it was spawned only when the user held the controller almost parallely in front of them. The map allowed the user to jump to any room they select in the building, the selection was done by poiniting at the room's name with the right controller and pressing the trigger button. This map also showed the user's position and orientation that updated in real-time.

![Interactive Map](\assets\img\projects\archviz\map.png)

### Compass

At the corner of the map, a compass was attached to help them stay aware of their orientation.

### Guiding Arrows

These arrow were spawned after teleporting using the map to show the virtual entrance of the room they selected.

### Signages

The building was also filled with signages to assist navigating the space

![Signage](\assets\img\projects\archviz\sign1.png)

## Outcome

This project was presented at IDC's golden jubliee celebrations. Where alunmi, professor and students got to see the floors allocated to IDC. The people overseeing the construction were also shown the demo at the event.


{% include flexgallery id="flexgallery1" caption="Demo at IDC50" %}