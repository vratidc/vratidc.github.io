---
title:  "When it Rains: An AR storybook"
excerpt: AR storybook
layout: projects
selected: "false"
homepage: "false"
fullpage: "yes"
active: "yes"
date: 2018-01-01


og_image: /assets/img/projects/WhenItRains/og.jpg
header:
    teaser: /assets/img/projects/WhenItRains/thumbnail.PNG
tags: AR Research

banner_image1: 
banner_image1_caption:

team_members: "Padmasree M M"
team_members_align: "text-left"

permalink: projects/whenitrains

--- 

<figure class="align-center" style="width:100%;">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/img/projects/WhenItRains/wir_thumb.png" alt="whenitrains_cover">
</figure>

## Introduction

Augmented Reality (AR) is rapidly gaining ground in education, offering a completely new and intuitive method for learning. While bedtime stories remain a cherished memory, children today are heavily engaged with screens, often finding traditional reading dull and boring. Interactive books offer tons of developmental benefits, including fostering critical thinking, early literacy, and a love of reading. However, with traditional books, interactions are purely based on imagination, and the child can only visualize the story vicariously.


<br>

## Narrative
### The Narrative: Simple Moments, Lasting Bonds

The story, "When it Rains," is a simple, character-driven narrative about two friends walking home from school on a rainy day. It focuses on the little moments they share and the sights they encounter. The entire story is driven by the conversation between the children, depicting themes of love, kindness, and friendship for each other.


### Character Design

The story is centered around two main characters: Sophie and Ammu. They are best friends who are both mischievous and playful, and who genuinely care for one another.

<br>

### Visual Development and final illustrations

<figure class="align-center" style="width:100%;">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/img/projects/WhenItRains/wir8.jpg" alt="wir8">
</figure>

<figure class="align-center" style="width:100%;">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/img/projects/WhenItRains/wir9.jpg" alt="wir9">
</figure>

<figure class="align-center" style="width:100%;">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/img/projects/WhenItRains/wir10.jpg" alt="wir10">
</figure>

<figure class="align-center" style="width:100%;">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/img/projects/WhenItRains/wir11.jpg" alt="wir11">
</figure>

<figure class="align-center" style="width:100%;">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/img/projects/WhenItRains/wir12.jpg" alt="wir12">
</figure>

<figure class="align-center" style="width:100%;">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/img/projects/WhenItRains/wir13.jpg" alt="wir13">
</figure>

<br>

## Exploring AR Development Platforms

<div style="max-width:900px; margin:0;">
  <style>
    .no-hover-table tr,
    .no-hover-table td,
    .no-hover-table th { transition: none !important; }
    .no-hover-table tr:hover { background: transparent !important; }
    .no-hover-table td:hover { background: transparent !important; }
  </style>
  <table class="no-hover-table" style="width:100%; border-collapse:separate; border-spacing:8px 3px; font-size:0.82rem;">
    <thead>
      <tr style="transition:none;">
  <th style="text-align:left; padding:4px 6px;">Software</th>
  <th style="text-align:left; padding:4px 6px;">Summary of Functionality</th>
  <th style="text-align:left; padding:4px 6px;">Key Limitation (Why it wasn't chosen)</th>
      </tr>
    </thead>
    <tbody>
    <tr style="transition:none; pointer-events:auto;">
  <td style="padding:3px 6px; vertical-align:top;">Slide AR</td>
  <td style="padding:3px 6px; vertical-align:top;">Allows artists to upload layer-by-layer illustrations and view them instantly in AR.</td>
  <td style="padding:3px 6px; vertical-align:top;">Cannot export the final AR experience for distribution.</td>
    </tr>
    <tr style="transition:none; pointer-events:auto;">
  <td style="padding:3px 6px; vertical-align:top;">Adobe Aero</td>
  <td style="padding:3px 6px; vertical-align:top;">Uploads PSD files and offers extensive interactivity options without coding.</td>
  <td style="padding:3px 6px; vertical-align:top;">The AR experience can only be shared via links, and export formats do not support making a final executable file (like an APK).</td>
    </tr>
    <tr style="transition:none; pointer-events:auto;">
  <td style="padding:3px 6px; vertical-align:top;">Unity</td>
  <td style="padding:3px 6px; vertical-align:top;">A robust platform for overlaying digital content (images, video, text, sound) onto locations, viewed through a device camera.</td>
  <td style="padding:3px 6px; vertical-align:top;">Chosen Platform. Provides the necessary control and export options to create a standalone mobile application.</td>
    </tr>
    </tbody>
  </table>
</div>


<br>

<figure class="align-center" style="width:100%;">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/img/projects/WhenItRains/wir16.png" alt="wir16">
</figure>

<figure class="align-center" style="width:100%;">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/img/projects/WhenItRains/workin.gif" alt="wir16">
  <figcaption>It is exported as an APK for Android from Unity and installed on the mobile phone. </figcaption>
</figure>

### Using video playback

Instead of uploading layer by layer, a video playback is kept by adding a video component for the marker. On viewing the marker illustration, an animated video will be playing.

<br>

## Challenges and Learning

The most significant challenge was the Portal Parallax implementation, the complex technical setup required to create the 3D depth effect. This involved several iterative methods and required custom C# coding in Unity. Note: Collaboration with Prof. Jayesh Pillar and Amarnath Murugan was key to achieving the final technical breakthrough.





