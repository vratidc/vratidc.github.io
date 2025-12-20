---
title:  "Belonging"
excerpt: Interactive 360° Immersive Mystery Story
layout: projects   
selected: "false"
homepage: "false"
fullpage: "yes"
active: "yes"
date: 2024-07-01


og_image: /assets/img/projects/belonging/og.jpg

header:
    teaser: /assets/img/projects/belonging/Diagrams-00_Teaser.png
tags: VR Film Storytelling

banner_image1:
banner_image1_caption:

team_members: " Jayesh Pillai | Tushar Vaid |  Priyanshu Thakur "
team_members_align: "text-left"

permalink: projects/Belonging
---
<figure class="align-center" style="width:100%;">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/img/projects/belonging/Belonging_RV_Thumbnail.jpg" alt="belonging_banner">
</figure>

## ABSTRACT

VR narratives provide viewers with the feeling of being immersed in a story environment by giving them the freedom to look
around and change their point-of-view during the experience. Storytellers use various techniques to guide the viewers to important
plot points in a VR narrative. Previous studies have examined various methods to design narratives for 360-degree VR films with
linear and non-linear narratives. In this study, we look at the grammar of storytelling in a real-time 6 degrees of freedom (6DoF) VR
experience.
<br>
<br>
 We created ’Belonging’, a real-time VR narrative in which one has the freedom to experience the story by physically
moving around in the environment and changing point-of-view as the story progresses. Through this project, we intend to explore
design-related aspects of narrative and associated technical challenges for creating a compelling 6DoF real-time VR experience. In this
narrative, we focus on the audio and visual cues that would effectively guide the viewers to the plot points.

ArtsTrack Film : [Belonging | IndiaHCI | ArtsTrack](https://youtu.be/GQ5aEutfYxw?feature=shared){:target="_blank"} 
<br>
<br>

## Introduction

VR filmmaking challenges traditional storytelling. While traditional films confine viewers to a fixed perspective, VR immerses users in 360-degree environments, allowing them to freely explore and choose their own viewpoint. This freedom presents unique challenges for storytellers who must guide the user's attention effectively.

Previous research has explored how visual and audio cues can influence user experience in linear VR narratives. However, real-time 6DoF VR films, where users can both look around and move within the environment, offer new possibilities and require innovative storytelling techniques.

This project aims to investigate the grammar of storytelling in 6DoF VR, particularly focusing on the role of audio and visual cues in shaping the narrative experience. By understanding these techniques, we can create more engaging and impactful VR films.

<br>

## Perceptual Cues

This study primarily focuses on how the various cues help the viewer navigate the space successfully in an intuitive
way. The space and the timeline of the narrative were accordingly planned with careful attention to the timings of each
plot point.

<br>

### Space and Plot Points
<br>

<figure class="align-center" style="width:100%;">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/img/projects/belonging/Diagrams-01.jpg" alt="belonging_Participants">
  <figcaption> Spatial representation of the narrative with plot points and ideal path of the viewer </figcaption>
</figure>
<br>

There are three scenes in the narrative of ‘Belonging’. The various plot points, along with the ideal path and direction
of the viewer, are shown in the given figure, using a top-view of the story space. The placement and timing of these plot points
were designed to guide the viewer gradually towards specific locations in the narrative space.

<br>

### Timeline and Audio-Visual Cues

<figure class="align-center" style="width:100%;">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/img/projects/belonging/Diagrams-02.jpg" alt="belonging_Participants">
  <figcaption> Temporal representation of the narrative with audio and visual cues </figcaption>
</figure>
<br>

It was essential to visualise the narrative in a temporal manner since there were multiple plot points taking place in
parallel. The three scenes mentioned above, along with the starting and ending credits, are represented as a timeline
in Figure. The visual and audio cues that were designed to aid attention shifts from one plot point to another are also
captured under the timeline in the above figure.

<br>

## Technical Implementation

<figure class="align-center" style="width:100%;">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/img/projects/belonging/dev_ue5.png" alt="belonging_Participants">
  <figcaption> Spotlights and spatial audio setup in the Unreal Engine 5 Editor </figcaption>
</figure>

This VR narrative was created using Unreal Engine 5 in the above figure with the 3D objects created in Blender. In order to overcome
the technical challenges that came with the experience of real-time VR films, we used a few unique techniques that are
explained below.

<strong>Triggering Plot Points :</strong>
To ensure effective storytelling, the VR film incorporates fixed plot points and triggerable events based on the viewer's position or POV. For example, at plot point 11, visual cues guide the viewer to enter a room where plot point 12 unfolds. Proximity-based logic triggers animations and dialogues, maintaining narrative flow while avoiding missed story elements.

<strong>Spatial Audio :</strong>
Spatial audio, powered by Unreal Engine 5's attenuation system, enhances immersion by guiding attention to character dialogues and events based on directionality. Sound effects like door creaks, spotlight activations, and footsteps further engage the viewer in the story.

<strong>Out of Bounds Control :</strong>
To keep viewers within the narrative space, a fade-to-black mechanism activates when nearing the boundaries of the environment. Gradual fading ensures players remain within the intended area, triggered by proximity detection using raycasting.

<br>

## Prototyping & Testing

<figure class="align-center" style="width:100%;">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/img/projects/belonging/Diagrams-04.jpg" alt="belonging_Participants">
  <figcaption> Participants experiencing the VR narrative </figcaption>
</figure>

As part of a pilot study, our prototype was tested with six participants. The study aimed to evaluate the effectiveness of the audio-visual cues designed to guide the narrative experience.

The findings revealed that spatial audio cues were particularly effective in directing the viewer’s attention. Since the sculptures within the narrative remained stationary while engaging in dialogue, the lack of significant character movement reduced the reliance on visual cues, making audio cues the primary focus in certain instances.


Additionally, the sequencing of dialogue among the sculptures played a critical role in guiding viewers through the narrative, enabling a smooth progression toward key plot points. Most notably, post-experience feedback indicated that participants comprehended the essence of the story, affirming the success of the narrative design.

<br>

## Conclusion and Future Work

We believe that through this demonstration, we will be able to study how viewers experience stories in 6DoF VR
narratives. Understanding audio-visual cues is key to understanding the evolving grammar of storytelling in VR. We
intend to conduct an in-depth analysis of these perceptual cues and propose guidelines to help VR filmmakers in
designing effective VR narratives.

<br>

## Publications

- **Jayesh Pillai**, Priyanshu THakur, and Tushar Vaid. 2023. **Belonging: Exploring Audio-Visual Cues in Real-time 6DoF VR Narrative**. In ACM Designing Interactive Systems (DIS) 2023, November 23-25, 2023, Dehradun, India. ACM, New York, NY, USA.  
 

