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

gallery1:
  - url: 
    image_path: /assets/img/projects/archviz/map1.png
    alt: "Design of the handheld map"
    title: "Design of the handheld map"
  - url: 
    image_path: /assets/img/projects/archviz/map2.gif
    alt: "Handheld map being used"
    title: "Handheld map being used"

gallery2:
  - url: 
    image_path: /assets/img/projects/archviz/sign1.png
    alt: "Signage Design"
    title: "Signage Design"
  - url: 
    image_path: /assets/img/projects/archviz/sign2.gif
    alt: "Signage Demo"
    title: "Signage Demo"

gallery3:
  - url: 
    image_path: /assets/img/projects/archviz/idc50_1.jpg
    alt: "IDC-50 Demo"
    title: "IDC-50 Demo"
  - url: 
    image_path: /assets/img/projects/archviz/idc50_2.jpg
    alt: "Demo presented to a professor"
    title: "Demo presented to a professor"
---

This project was taken up by Arun Babu as part of his M.Des Design Exploration Seminar (DES) 

<br>

## Abstract

Architectural Visualization is one of the core applications of VR, where stakeholders can see and decide on various elements of the building while planning. This helps in understanding how the building could look like after construction. This can speed up the development process as visualising the elements in VR provides the feeling of being present there. This project aims at giving a better experience to the users with respect to navigation and visual fidelity. We chose to visualize the upcoming building near IDC School of Design for this project.

<br>

## The Experience

{% include video id="1cuQF2g36_BkYn24UpnZqhwoZ0ZdWCFc0" provider="google-drive" %}
<figcaption>Demo of the Navigation Experience</figcaption>

<br>

## Components of Navigation

Mutliple interactions and navigational elements were integrated in this project to allow people to explore and move around the space better.

**Teleportation:** A common interaction in VR, which allows to traverse large virtual spaces while the user's phyical space is limited.

**Handheld Map:** An interactive map was attached to the left-hand controller, and it was spawned only when the user held the controller up in front of them. The map allowed the user to transport to any room they select in the building. The selection was done by poiniting at the room's name with the right-hand controller and pressing the trigger button. This map also showed the user's position and orientation that updated in real-time.

{% include gallery id="gallery1" caption="Interactive handheld map with a compass, designed to aid navigation" %}

**Compass:** At the corner of the map, a compass was attached to help them stay aware of their orientation.

**Guiding Arrows:** After teleporting using the map, arrows are spawned in appropriate directions, to show the virtual entrance of the room one had selected.

**Signages:** The building was also provided with signages to assist navigating the space.

{% include gallery id="gallery2" caption="Signages designed for the building interiors" %}

<br>

## Outcome

This project was presented at IDC's golden jubliee celebrations, where alunmi, professors and students were able to navigate through the upcoming spaces designated to IDC School of Design. The people overseeing the construction also experienced the demo at the event.


{% include gallery id="gallery3" caption="Demonstration at IDC-50 Event (Dec 2019)" %}


