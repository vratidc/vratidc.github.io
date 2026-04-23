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

flex_bee:
  - aspect: "1"
    image_path: /assets/img/projects/WildVue/beedia.png
  - aspect: "1"
    image_path: /assets/img/projects/WildVue/beeview.png

flex_cat:
  - aspect: "1"
    image_path: /assets/img/projects/WildVue/catdia.png
  - aspect: "1"
    image_path: /assets/img/projects/WildVue/catview.png

flex_dog:
  - aspect: "1"
    image_path: /assets/img/projects/WildVue/dogdia.png
  - aspect: "1"
    image_path: /assets/img/projects/WildVue/dogview.png

flex_fish:
  - aspect: "1"
    image_path: /assets/img/projects/WildVue/fishdia.png
  - aspect: "1"
    image_path: /assets/img/projects/WildVue/fishview.png

gallery1:
  - url: /assets/img/projects/WildVue/render.jpg
    image_path: /assets/img/projects/WildVue/render.jpg
  - url: /assets/img/projects/WildVue/sketch.png
    image_path: /assets/img/projects/WildVue/sketch.png

gallery2:
  - url: /assets/img/projects/WildVue/ue1.png
    image_path: /assets/img/projects/WildVue/ue1.png
  - url: /assets/img/projects/WildVue/ue2.png
    image_path: /assets/img/projects/WildVue/ue2.png

flex_row1:
  - aspect: "4"
    image_path: /assets/img/projects/WildVue/out1.png

flex_row2:
  - aspect: "2"
    image_path: /assets/img/projects/WildVue/out2.png
  - aspect: "2"
    image_path: /assets/img/projects/WildVue/out3.png

gallery3:
  - url: /assets/img/projects/WildVue/bee.png
    image_path: /assets/img/projects/WildVue/bee.png
  - url: /assets/img/projects/WildVue/dog.png
    image_path: /assets/img/projects/WildVue/dog.png
  - url: /assets/img/projects/WildVue/cat.png
    image_path: /assets/img/projects/WildVue/cat.png
  - url: /assets/img/projects/WildVue/pig.png
    image_path: /assets/img/projects/WildVue/pig.png
  - url: /assets/img/projects/WildVue/hen.png
    image_path: /assets/img/projects/WildVue/hen.png
  - url: /assets/img/projects/WildVue/fish.png
    image_path: /assets/img/projects/WildVue/fish.png
---

WildVue is a free-roam VR experience that allows users to switch between human and animal perspectives within a shared environment.

<figure class="align-center" style="width:100%;">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/img/projects/WildVue/logo.png">
</figure>

## Project Overview

WildVue, World Through Animal Eyes, is a free-roam VR experience that allows users to switch between human and animal perspectives within a shared space. Each perspective alters how the world is perceived; through changes in color, field of view, scale, and motion.

The project explores VR as a medium for perceptual storytelling. Instead of explaining animal vision, it translates it into an embodied experience where users move, observe, and interact as different species.

The work functions both as an educational exploration and a personal inquiry into how immersive media can reshape understanding through perspective.

---

## 1. Concept

Users move freely through a shared environment inhabited by different animals, switching perspectives at any time. Each shift changes how the same space is seen, through color, distortion, scale, and field of view, supported by six degrees of freedom for a more natural sense of exploration.

The focus is on perceptual plausibility rather than strict biological accuracy. To keep the scope manageable, the experience centers on four animals, **bee**, **cat**, **dog**, and **fish**, chosen for their clearly different ways of seeing.

Research drew from academic papers, veterinary sources, online simulations, and video references. Each animal’s vision was distilled into a small set of traits that could be translated into real-time VR.

- **Bee:** Wide FOV (~280°), UV sensitivity

{% include flexgallery id="flex_bee" %}

- **Cat:** Low-light vision, motion 
sensitivity  

{% include flexgallery id="flex_cat" %}

- **Dog:** Dichromatic vision, wide peripheral  

{% include flexgallery id="flex_dog" %}

- **Fish:** Near-panoramic (~300°), underwater adaptation  

{% include flexgallery id="flex_fish" %}

---

## 2. Environment Design

To support all perspectives within one space, the environment was designed as a **farm and garden at golden hour**. This setting allowed different animals to coexist while offering varied zones for interaction.

Early ideation involved narrative sketches, spatial layouts, and top-down maps, followed by rough 3D visualizations to test scale, flow, and boundaries.

{% include gallery id="gallery1" caption="Environment design iterations and spatial planning" %}

---

## 3. Interaction

Early prototypes tested locomotion, camera switching, and basic interactions before moving into a full Unreal Engine build using Blueprint scripting.

{% include gallery id="gallery2" caption="Development in Unreal Engine" %}

Each animal perspective includes a simple interaction:

- Dog → Navigating a maze
- Cat → Protecting resources 
- Fish → Feeding behaviour
- Bee → Collecting nectar  

Movement was designed to feel natural while minimizing discomfort. Humans, cats, and dogs use gaze-aligned joystick movement, while bees and fish move in three dimensions using controlled acceleration and gaze-based direction. Spatial audio was integrated throughout to reinforce immersion.

---

## Outcome

{% include video id="1034737680?h=9c27d8d19d" provider="vimeo" %}
<figcaption>WildVue VR Experience</figcaption>


{% include flexgallery id="flex_row1" %}

{% include flexgallery id="flex_row2" %}

WildVue is both an educational tool and an exploration into the potential of VR technology.This project offers interactive educational experience by enabling users to switch between the visual perspectives of different animals, such as insects, mammals, and aquatic creatures.

{% include gallery id="gallery3" caption="Final experience and output" %}