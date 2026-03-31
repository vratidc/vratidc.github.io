---
title:  "Star Maze"
excerpt: Asymmetric Multiplayer VR Maze Experience
layout: projects   
selected: "false"
homepage: "false"
fullpage: "yes"
active: "no"
date: 2025-04-01

og_image: /assets/img/projects/Star-Maze/sm1.png

header:
  teaser: /assets/img/projects/Star-Maze/sm1.png
tags: VR Multiplayer Game 

banner_image1:
banner_image1_caption:

team_members: "Anumeha Patoria, Yashwant Rawat, Hayat Tamboli, Tanmay Kuwalekar "
team_members_align: "text-left"

permalink: projects/starmaze


flexgallery1:
  - aspect: "1.33"
    url:
    image_path: /assets/img/projects/Star-Maze/starmaze_vr1.jpg
    alt: "Star Maze VR gameplay"
    title: "VR gameplay"
  - aspect: "1.33"
    url:
    image_path: /assets/img/projects/Star-Maze/starmaze_vr2.jpg
    alt: "Star Maze maze environment"
    title: "Maze environment"
  - aspect: "1.33"
    url:
    image_path: /assets/img/projects/Star-Maze/starmaze_vr3.jpg
    alt: "Star Maze obstacles"
    title: "Obstacles and traps"

flexgallery2:
  - aspect: "1.00"
    url:
    image_path: /assets/img/projects/Star-Maze/starmaze_mobile1.jpg
    alt: "Star Maze mobile interface"
    title: "Mobile control interface"
  - aspect: "1.00"
    url:
    image_path: /assets/img/projects/Star-Maze/starmaze_mobile2.jpg
    alt: "Star Maze maze control view"
    title: "Maze control view"
  - aspect: "1.00"
    url:
    image_path: /assets/img/projects/Star-Maze/starmaze_mobile3.jpg
    alt: "Star Maze player monitoring"
    title: "Player monitoring"

flexgallery3:
  - aspect: "1.77"
    url:
    image_path: /assets/img/projects/Star-Maze/starmaze_setup1.jpg
    alt: "Star Maze setup"
    title: "VR and mobile setup"
  - aspect: "1.77"
    url:
    image_path: /assets/img/projects/Star-Maze/starmaze_setup2.jpg
    alt: "Two player setup"
    title: "Two player setup"
  - aspect: "1.77"
    url:
    image_path: /assets/img/projects/Star-Maze/starmaze_demo.jpg
    alt: "Outreach demo"
    title: "Outreach demo"

---

<figure class="align-center" style="width:100%;">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/img/projects/Star-Maze/starmaze_hero.jpg" alt="Star Maze gameplay view">
</figure> 

## Project Overview

Star Maze is an asymmetric two player multiplayer VR experience created for outreach and public engagement. The project demonstrates how different interfaces can be combined in a single interactive system to create engaging and understandable experiences. One player navigates a maze in immersive VR using natural body movement, while the second player uses a mobile device to control and manipulate the maze environment in real time. The experience introduces audiences to concepts such as shared virtual spaces, real time interaction, and cross device collaboration in a simple and approachable way.

## Recognitions

<figure class="align-center" style="width:20%;">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/img/projects/Star-Maze/hci.png" alt="India HCI 2024 Logo">
</figure>

**Best Project Award, INDIA HCI 2024 (Arts and Installation Track)**  
Star Maze won the Best Project Award at INDIA HCI 2024 in the Arts and Installation track.

<br>

<figure class="align-center" style="width:30%;">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/img/projects/Star-Maze/LV2025.png" alt="Laval Virtual 2025 Logo">
</figure>

**Student Demo Competition, Laval Virtual 2025, France**  
Star Maze was presented at Laval Virtual 2025, an international XR event held in April 2025, as part of the Student Demo Competition.

<br>

## Concept

Star Maze is an asymmetric competitive experience built on the contrast between embodiment and control. One player, the Traveler, is physically immersed in a VR maze, experiencing urgency and spatial uncertainty. The other, the Overseer, uses a mobile device to view the entire map and manipulate the environment from a distance. Inspired by multiplayer games with unequal information, the project explores how differing viewpoints and control schemes shape communication and strategy.

The game loop is designed as a short, intense encounter lasting only a few minutes. This makes it ideal for outreach contexts where spectators can easily follow the visible cause-and-effect between mobile interventions and VR world changes.

## Design Approach

The design approach was guided by outreach constraints and first time user experience.

The experience needed to be easy to explain in less than one minute, simple to operate without prior training, and robust enough to run repeatedly in public settings. Narrative framing was kept minimal and functional, providing context without requiring long explanations. The control scheme for the traveler uses walking in place and head direction to avoid complex controller mappings. The overseer interface was designed as a simple top down view with clear buttons for shifting walls and placing traps.

Playtesting with users unfamiliar with VR was used to refine onboarding, reduce confusion, and adjust pacing. Particular attention was paid to reducing motion discomfort, ensuring that movement felt intuitive and did not cause disorientation.

## Process

The project followed an iterative development lifecycle:

**Initial Stage**: Brainstorming narrative frames and testing "walking in place" detection through early digital prototypes.
**Mid-Stage**: Balancing gameplay by limiting the Traveler’s "wall-breaking" and "teleportation" abilities to ensure the Overseer role remained impactful.
**Final Stage**: Streamlining the setup for facilitators to run multiple sessions with minimal overhead and handling error states for public deployment.

## Gameplay and Roles

**Player 1: The Traveler (VR Headset)**  
The traveler starts at the entry point of the maze. Locomotion is controlled by walking in place, with head direction determining movement direction. The player must navigate corridors, identify viable paths, and manage limited abilities. Walls can be broken by continuous punching for two to three seconds, up to three times per session. A limited teleport ability allows relocation to predefined safe points through a double clap gesture. These mechanics introduce strategic choices about when to take risks and when to conserve abilities.

**Player 2: The Overseer (Mobile Device)**  
The overseer views the maze from a top down perspective. Using the mobile interface, this player can shift selected walls, place traps, and observe the traveler’s movement in real time. The overseer must predict the traveler’s path and decide where to intervene to delay progress. Traps and environmental changes notify the overseer when the traveler is affected, creating feedback loops that support strategic planning.

{% include flexgallery id="flexgallery1" caption="VR gameplay from the Traveler’s perspective" %}

{% include flexgallery id="flexgallery2" caption="Mobile interface for the Overseer" %}

## Development

Star Maze is a networked system connecting a VR application and a mobile device in real time via a lightweight networking layer.
- The VR application manages player embodiment and interaction, while the mobile app provides a live map and manipulation tools.
- A modular maze system allows for various layouts without altering core logic, ensuring replayability and easy adaptation for demos.
- Designed for classrooms and labs, the setup requires only one VR headset and one mobile phone connected over a local network.

{% include flexgallery id="flexgallery3" caption="Two player setup and outreach demonstrations" %}

## Outcome

Star Maze functions as both an interactive game and a demonstrator for VR based interaction design. In outreach settings, it helps audiences understand concepts such as immersive environments, asymmetric multiplayer systems, and cross device interaction. The short session length allows many participants to experience the system within a limited time window. The clear spectator value supports engagement even for those not directly playing, making it effective for public demonstrations.
