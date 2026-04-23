---
title:  "WildVue"
excerpt: World Through Animal Eyes
layout: projects   
selected: "false"
homepage: "false"
fullpage: "yes"
active: "yes"
date: 20240101

header:
    teaser: /assets/img/projects/WildVue/wildvue_thumbnail.jpg
tags: VR Interaction Perception Storytelling  

team_members: "Manu Krishnan | Prof. Jayesh Pillai"
team_members_align: "text-left"

permalink: projects/wildvue
---

WildVue is a free-roam VR experience that allows users to switch between human and animal perspectives within a shared environment.

<figure class="align-center" style="width:100%;">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/img/projects/WildVue/wildvue_cover.jpg" alt="wildvue_cover">
  <figcaption>World Through Animal Eyes</figcaption>
</figure>

---

## Project Overview

WildVue, World Through Animal Eyes, is a free-roam VR experience that allows users to switch between human and animal perspectives within a shared space. Each perspective alters how the world is perceived; through changes in color, field of view, scale, and motion. 

The project explores VR as a medium for perceptual storytelling. Instead of explaining animal vision, it translates it into an embodied experience where users move, observe, and interact as different species.

The work functions both as an educational exploration and a personal inquiry into how immersive media can reshape understanding through perspective.

<figure class="align-center" style="width:100%;">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/img/projects/WildVue/wildvue_overview.jpg">
</figure>

---

## Concept

Users move freely through a shared environment inhabited by different animals, switching perspectives at any time. Each shift changes how the same space is seen, through color, distortion, scale, and field of view, supported by six degrees of freedom for a more natural sense of exploration.

The focus is on perceptual plausibility rather than strict biological accuracy. To keep the scope manageable, the experience centers on four animals, bee, cat, dog, and fish, chosen for their clearly different ways of seeing.

Research drew from academic papers, veterinary sources, online simulations, and video references. Each animal’s vision was distilled into a small set of traits that could be translated into real-time VR.

- **Bee** → Wide FOV (~280°), UV sensitivity, high contrast

<figure class="align-center" style="width:100%;">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/img/projects/WildVue/wildvue_concept.jpg">
</figure>

- **Cat** → Low-light vision, limited color range, motion sensitivity  

<figure class="align-center" style="width:100%;">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/img/projects/WildVue/wildvue_concept.jpg">
</figure>

- **Dog** → Broad peripheral vision (~240°), dichromatic color perception 

<figure class="align-center" style="width:100%;">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/img/projects/WildVue/wildvue_concept.jpg">
</figure>

- **Fish** → Near-panoramic (~300°), underwater adaptation  

<figure class="align-center" style="width:100%;">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/img/projects/WildVue/wildvue_animals.jpg">
  <figcaption>Visual differences across species</figcaption>
</figure>

---

## Environment Design

To support all perspectives within one space, the environment was designed as a farm and garden at golden hour. This setting allowed different animals to coexist while offering varied zones for interaction.

Early ideation involved narrative sketches, spatial layouts, and top-down maps, followed by rough 3D visualizations to test scale, flow, and boundaries.

<figure class="align-center" style="width:100%;">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/img/projects/WildVue/wildvue_environment.jpg">
</figure>

The experience is lightly narrative-driven. The narrative exists only to contextualize perspective switching. After exploring multiple directions, the final structure focused on helping animals, where each perspective enables a small, purpose-driven interaction.

---

## Interaction

Early prototypes tested locomotion, camera switching, and basic interactions before moving into a full Unreal Engine build using Blueprint scripting.

<figure class="align-center" style="width:100%;">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/img/projects/WildVue/wildvue_interactions.jpg">
</figure>

Each animal includes a distinct interaction:

- Dog → Maze navigation  
- Cat → Resource protection  
- Fish → Feeding  
- Bee → Nectar collection  

Movement was designed to feel natural while minimizing discomfort. Humans, cats, and dogs use gaze-aligned joystick movement, while bees and fish move in three dimensions using controlled acceleration and gaze-based direction. Spatial audio was integrated throughout to reinforce immersion.

---

## Outcome

WildVue is both an educational tool and an exploration into the potential of VR technology.This project offers interactive educational experience by enabling users to switch between the visual perspectives of different animals, such as insects, mammals, and aquatic creatures.

<figure class="align-center" style="width:100%;">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/img/projects/WildVue/wildvue_result.jpg">
</figure>