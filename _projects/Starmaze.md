---
title:  "Star Maze"
excerpt: Asymmetric Multiplayer VR Maze Experience for Outreach
layout: projects   
selected: "false"
homepage: "false"
fullpage: "yes"
active: "yes"
date: 2026-02-08

og_image: /assets/img/projects/StarMaze/sm1.png

header:
    teaser: /assets/img/projects/StarMaze/smlogo.jpeg
tags: VR Multiplayer Game Storytelling 

banner_image1:
banner_image1_caption:

team_members: "Anumeha Patoria, Yashwant Rawat, Hayat Tamboli, Tanmay Kuwalekar "
team_members_align: "text-left"

permalink: projects/starmaze


flexgallery1:
  - aspect: "1.33"
    url:
    image_path: /assets/img/projects/StarMaze/starmaze_vr1.jpg
    alt: "Star Maze VR gameplay"
    title: "VR gameplay"
  - aspect: "1.33"
    url:
    image_path: /assets/img/projects/StarMaze/starmaze_vr2.jpg
    alt: "Star Maze maze environment"
    title: "Maze environment"
  - aspect: "1.33"
    url:
    image_path: /assets/img/projects/StarMaze/starmaze_vr3.jpg
    alt: "Star Maze obstacles"
    title: "Obstacles and traps"

flexgallery2:
  - aspect: "1.00"
    url:
    image_path: /assets/img/projects/StarMaze/starmaze_mobile1.jpg
    alt: "Star Maze mobile interface"
    title: "Mobile control interface"
  - aspect: "1.00"
    url:
    image_path: /assets/img/projects/StarMaze/starmaze_mobile2.jpg
    alt: "Star Maze maze control view"
    title: "Maze control view"
  - aspect: "1.00"
    url:
    image_path: /assets/img/projects/StarMaze/starmaze_mobile3.jpg
    alt: "Star Maze player monitoring"
    title: "Player monitoring"

flexgallery3:
  - aspect: "1.77"
    url:
    image_path: /assets/img/projects/StarMaze/starmaze_setup1.jpg
    alt: "Star Maze setup"
    title: "VR and mobile setup"
  - aspect: "1.77"
    url:
    image_path: /assets/img/projects/StarMaze/starmaze_setup2.jpg
    alt: "Two player setup"
    title: "Two player setup"
  - aspect: "1.77"
    url:
    image_path: /assets/img/projects/StarMaze/starmaze_demo.jpg
    alt: "Outreach demo"
    title: "Outreach demo"

---

<figure class="align-center" style="width:100%;">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/img/projects/StarMaze/starmaze_hero.jpg" alt="Star Maze gameplay view">
</figure> 

## Abstract

Star Maze is an asymmetric two player multiplayer VR experience created for outreach and public engagement. The project demonstrates how different interfaces can be combined in a single interactive system to create engaging and understandable experiences. One player navigates a maze in immersive VR using natural body movement, while the second player uses a mobile device to control and manipulate the maze environment in real time. The experience introduces audiences to concepts such as shared virtual spaces, real time interaction, and cross device collaboration in a simple and approachable way.

The narrative of a stranded space traveler trying to reach a star powered energy beam provides a clear goal that is easy to understand for first time users. The overseer role adds challenge and replay value by dynamically shaping the maze, ensuring that each play session feels different. The project is designed for short sessions, making it suitable for exhibitions, open days, and classroom outreach.

## Recognitions

<figure class="align-center" style="width:20%;">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/img/projects/StarMaze/hci.png" alt="India HCI 2024 Logo">
</figure>

**Best Project Award, INDIA HCI 2024 (Arts and Installation Track)**  
Star Maze won the Best Project Award at INDIA HCI 2024 in the Arts and Installation track. The project was recognised for its use of immersive VR, asymmetric multiplayer interaction, and its effectiveness as an outreach focused interactive installation.

<br>

<figure class="align-center" style="width:30%;">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/img/projects/StarMaze/LV2025.png" alt="Laval Virtual 2025 Logo">
</figure>

**Student Demo Competition, Laval Virtual 2025, France**  
Star Maze was presented at Laval Virtual 2025, an international XR event held in April 2025, as part of the Student Demo Competition. The project was selected for demonstration alongside other student XR works and showcased to an international audience of researchers, industry professionals, and the general public.

<br>

**Academic Context**  
Star Maze was conceptualised, designed, developed, and tested as part of the two week course **Design for Virtual Reality** during the Autumn 2024 semester. The project was created under the guidance of **Prof. Jayesh Pillai** and developed within a short prototyping timeframe, focusing on rapid ideation, interaction design, and real time multiplayer VR systems.
## Concept

The central concept of Star Maze is built around asymmetric power and perspective. The traveler is physically present inside the maze and experiences tension, urgency, and spatial uncertainty. The overseer, in contrast, has an overview of the entire maze and controls the environment from a distance. This contrast creates a dynamic relationship between embodiment and control, immersion and strategy.

The concept was inspired by cooperative and competitive multiplayer games where players have unequal information and abilities. By placing one player in VR and the other on a mobile device, the project explores how different viewpoints and control schemes shape player experience, communication, and decision making.

## Design Approach

The design approach was guided by outreach constraints and first time user experience.

The experience needed to be easy to explain in less than one minute, simple to operate without prior training, and robust enough to run repeatedly in public settings. Narrative framing was kept minimal and functional, providing context without requiring long explanations. The control scheme for the traveler uses walking in place and head direction to avoid complex controller mappings. The overseer interface was designed as a simple top down view with clear buttons for shifting walls and placing traps.

Playtesting with users unfamiliar with VR was used to refine onboarding, reduce confusion, and adjust pacing. Particular attention was paid to reducing motion discomfort, ensuring that movement felt intuitive and did not cause disorientation.

## Final Concept

The final concept positions Star Maze as a short, intense competitive experience between two players with complementary roles. The traveler must balance speed, exploration, and limited use of special abilities to reach the star beam before time runs out. The overseer must decide when and where to intervene, using limited resources to reshape the maze and place traps that slow or mislead the traveler. The game loop is designed to last only a few minutes, making it ideal for repeated play in outreach contexts.

The final experience supports observation by spectators. The clear roles and visible cause effect between mobile actions and VR world changes make it easier for onlookers to understand what is happening, increasing the value of the project in public demos.

## Development

Star Maze was developed as a networked system connecting a VR application and a mobile application in real time. The VR application manages player embodiment, navigation, interaction with walls, traps, and the goal object. The mobile application provides a live map of the maze and tools to manipulate its structure. A lightweight networking layer ensures low latency communication between devices so that changes made by the overseer are immediately visible to the traveler.

The maze is designed as a modular system, allowing different layouts to be loaded without changing the core interaction logic. This supports replayability and easy adaptation for different demo scenarios. Visuals were kept stylized and readable to ensure clarity in VR and to maintain performance on standard VR hardware.

## Process

The project followed an iterative design and development process.

Initial stages involved brainstorming narrative frames and role based mechanics, followed by paper sketches of maze layouts and role interactions. Early digital prototypes focused on testing locomotion methods in VR and verifying that walking in place could be reliably detected. Parallel prototyping of the mobile interface explored different ways to represent the maze and control walls.

Mid stage iterations focused on balancing gameplay. Limits were added to wall breaking and teleportation abilities to prevent the traveler from overpowering the overseer role. Trap placement and notification mechanics were tuned to create tension without making the game feel unfair. Repeated playtests informed adjustments to time limits, maze size, and interaction feedback.

Final stages focused on stability, onboarding flow, and preparing the system for outreach deployment. Instructions were simplified, error states were handled more gracefully, and the setup process was streamlined so that facilitators could run multiple sessions in sequence with minimal overhead.

## Gameplay and Roles

**Player 1: The Traveler (VR Headset)**  
The traveler starts at the entry point of the maze. Locomotion is controlled by walking in place, with head direction determining movement direction. The player must navigate corridors, identify viable paths, and manage limited abilities. Walls can be broken by continuous punching for two to three seconds, up to three times per session. A limited teleport ability allows relocation to predefined safe points through a double clap gesture. These mechanics introduce strategic choices about when to take risks and when to conserve abilities.

**Player 2: The Overseer (Mobile Device)**  
The overseer views the maze from a top down perspective. Using the mobile interface, this player can shift selected walls, place traps, and observe the traveler’s movement in real time. The overseer must predict the traveler’s path and decide where to intervene to delay progress. Traps and environmental changes notify the overseer when the traveler is affected, creating feedback loops that support strategic planning.

{% include flexgallery id="flexgallery1" caption="VR gameplay from the Traveler’s perspective" %}

{% include flexgallery id="flexgallery2" caption="Mobile interface for the Overseer" %}

## Interaction Design

Interaction design emphasizes physical engagement for the VR player and cognitive strategy for the mobile player. Walking in place promotes embodied interaction without requiring large physical space. Punching to break walls provides a clear physical metaphor for exertion and effort. The double clap gesture offers a simple, discoverable trigger for special actions without introducing complex gestures.

For the overseer, interaction is based on direct manipulation of the maze through touch inputs. Clear visual feedback shows which walls can be moved and where traps are placed. Real time updates ensure that both players perceive the consequences of each other’s actions immediately, reinforcing the sense of a shared interactive system.

## System Setup

The system consists of a VR headset connected to the main application and a mobile device connected over a local network. A facilitator can start sessions, reset the maze, and switch players between roles. The setup is designed to be portable and suitable for temporary installations in classrooms, labs, and exhibition spaces. The minimal hardware requirement of one VR headset and one mobile phone makes the system practical for outreach use.

{% include flexgallery id="flexgallery3" caption="Two player setup and outreach demonstrations" %}

## Outcomes and Outreach Use

Star Maze functions as both an interactive game and a demonstrator for VR based interaction design. In outreach settings, it helps audiences understand concepts such as immersive environments, asymmetric multiplayer systems, and cross device interaction. The short session length allows many participants to experience the system within a limited time window. The clear spectator value supports engagement even for those not directly playing, making it effective for public demonstrations.

## Future Scope

Future directions include adding cooperative modes where both players work toward a shared goal, introducing adaptive difficulty based on player performance, and incorporating accessibility options for users with limited mobility. The system can also be extended as a research platform to study collaboration, competition, and communication patterns in asymmetric VR experiences.