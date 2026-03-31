---
title:  "Blind Justice"
excerpt: Exploring Voice-Based Interaction through a Narrative VR Experience
layout: projects   
selected: "False"
homepage: "False"
fullpage: "no"
active: "no"

og_image: /assets/img/projects/blind/og.png

header:
    teaser: /assets/img/projects/blind/og.png
tags: VR Research  

banner_image1:
banner_image1_caption:

team_members: "Laksh Rajpal | Jayesh Pillai"
team_members_align: "text-left"

permalink: projects/blindjustice
---

<figure class="align-center" style="width:100%;">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/img/projects/blind/header.png"
   alt="Blind Justice_banner">
</figure>

## Project Overview

Voice is one of the most natural and expressive human abilities, yet in most digital systems, it is reduced to rigid, efficiency-driven commands. In immersive media like Virtual Reality, interaction remains largely visual, overlooking the emotional and spatial potential of sound.
<br>

Blind Justice is a VR game that explores voice as a primary interaction modality, not just as input, but as a narrative and spatial force. The player acts as an unseen guide for Raju, a blind man attempting to recover stolen money from Shyamlal, a fraudulent beggar. Through spoken cues, loudness, and vocal intent, voice guides characters, shapes environments, and creates tension. Rather than prioritising recognition accuracy, the project focuses on atmospheric and relational uses of sound to drive experience and story.

## Understanding the Problem Space

Secondary research examined voice-based games across multiple decades, identifying four dominant categories of voice interaction:
<br>
- Volume detection
- Pitch and rhythm
- Voice commands
- Conversational dialogue
<br>
These mechanics have been used for navigation, combat, puzzle solving, companionship, and narrative progression. However, most applications treat voice as detached from space, ignoring how sound naturally carries direction, distance, and intent. Cultural practices, such as guiding blindfolded players through sound cues, demonstrate how voice has long been used for navigation, trust-building, and spatial awareness, offering valuable insight for immersive interaction design.

## Hands-On Exploration

<figure class="align-center" style="width:100%;">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/img/projects/blind/mech.png" 
  alt="Voice Mechanics in XR">
  <figcaption>Voice Mechanics in XR
  </figcaption>
</figure>

To ground the research, an earlier VR prototype explored volume-based interaction in a spatial environment. In this experiment, players used loudness to influence the movement of virtual characters, revealing how sound becomes more expressive when mapped into 3D space.
<br>
Participants instinctively leaned, gestured, and modulated their voices, showing that voice interaction is inherently embodied. Social context also played a role, players were more playful and expressive when interacting with friends. These observations validated the idea that ambiguity in voice input can encourage creativity, rather than confusion.

<figure class="align-center" style="width:100%;">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/img/projects/blind/group.png" 
  alt="Voice Mechanics in XR">
  <figcaption>Prototype testing
  </figcaption>
</figure>


## Scoping the Project

Given practical constraints, the project focused on two voice mechanics:
<br>

- Voice commands for intentional control
- Volume-based interaction for expressive, spatial influence
<br>
Pitch-based and conversational systems were excluded due to technical complexity and accessibility concerns. This scoping ensured that the experience remained feasible while still exploring meaningful vocal interaction.

## The Story: Blind Justice

The narrative revolves around two characters:
<br>
Raju, a genuinely blind man
Shyamlal, a fake blind beggar who exploits public sympathy
<br>
Raju witnesses Shyamlal deceiving people and decides to recover the stolen money. To do so, he enters Shyamlal’s house, an unfamiliar and dangerous space. The player assumes the role of Raju’s unseen guide, using voice commands to navigate him safely, while using loud sounds to distract Shyamlal. The goal is to retrieve valuables and escape without being caught. This setup transforms voice into a lifeline, embedding interaction directly into the emotional and ethical stakes of the story.

## Game Mechanics

### Dual-Character Interaction

The experience is built around two contrasting behaviours:
- Raju (ally) responds to precise voice commands like go, stop, and steal
- Shyamlal (antagonist) reacts instinctively to loud sounds
This creates a dynamic loop where the player must coordinate guidance and misdirection simultaneously.

### Spatial Distraction System
Shyamlal’s attention can be redirected using volume-based sounds placed strategically within the house. Loud noises near objects such as a TV or doorway cause him to investigate that area, opening safe paths for Raju. Sound becomes a spatial strategy, not just an input.

### Stealing, Timer, and Progression 

Collectible money bundles are scattered throughout the house. Stealing requires proximity and a vocal command, increasing risk and tension. A countdown timer creates urgency, while scoring rewards for calculated risk-taking. As time runs out, Shyamlal becomes more aggressive, triggering the endgame phase.

## Prototype 

A functional VR prototype was developed in Unity to test the complete interaction loop. The experience unfolds inside a semi-transparent miniature house, allowing players to observe character movement without excessive physical repositioning.
The prototype demonstrated the feasibility of integrating:

- Voice commands
- Volume-based spatial sound
- AI-driven character behaviour
- Narrative tension

Gameplay footage is available via a linked video in the original report

## Technical Challenges

Major challenges included:

- Reliable detection of short voice commands
- Simultaneous processing of voice commands and volume input
- Natural character navigation within a complex space

These were addressed through custom audio pipelines, AI-based navigation systems, and iterative refinement of interaction feedback.

## Design Detailing

<figure class="align-center" style="width:100%;">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/img/projects/blind/env.png" 
  alt="3D environment">
  <figcaption>High Fidelity Environment 
  </figcaption>
</figure>

A high-fidelity environment was later developed in Blender to explore atmosphere and storytelling through space. The house was designed as a worn, modest dwelling, reinforcing themes of secrecy and tension.
<br>
Due to performance constraints, only the core structural elements were imported into Unity, prioritising interaction over visual complexity.

## Outcome

Blind Justice demonstrates how voice can function as a meaningful, embodied interaction medium in VR. By grounding vocal interaction within a narrative of trust, vulnerability, and moral tension, the project moves beyond command-based systems toward emotionally resonant design. The work highlights the potential of sound-first interaction in immersive environments and opens avenues for future exploration in accessibility-driven and narrative-centric XR experiences.






