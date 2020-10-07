---
title:  "Dragonfly"
excerpt: Making of a Stereo 3D Ambisonic VR Film
layout: projects   
selected: "true"
homepage: "true"
fullpage: "yes"
active: "yes"

header:
    teaser: /assets/img/projects/Dragonfly/dragonfly_thumbnail.jpg
tags: VR-Film Storytelling Research  

banner_image1:

team_members: "Jayesh Pillai | Azif Ismail"
team_members_align: "text-left"

permalink: projects/dragonfly


---

<figure class="align-center" style="width:100%;">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/img/projects/Dragonfly/dragonfly_poster.jpg" alt="dragonfly_poster">
  <figcaption>Dragonfly Poster</figcaption>
</figure>


<!--
This project's details will be posted here soon.

## Abstract

Will be added


## Outcomes

Will be added
-->

Official Website: [dragonflymovie.in](https://dragonflymovie.in/){:target="_blank"}

Cast & Crew Details: [Dragonfly](https://www.jayeshpillai.com/2018/03/dragonfly360.html){:target="_blank"}

<br>

## Trailer
   {% include video id="oGD7U2uLTCI" provider="youtube" %}
   <figcaption>Dragonfly Trailer (2D)</figcaption>

Links : [Trailer (2D)](https://youtu.be/oGD7U2uLTCI){:target="_blank"}, [Trailer (3D)](https://youtu.be/G0Farj8T1j8){:target="_blank"}


<!-- 360-degree image embed. -->
<div class = "vr_single">
    <a-scene loading-screen="dotsColor: white; backgroundColor: #008055;" class="" embedded style="margin:0px; padding:0px;" vr-mode-ui="enterVRButton: #myEnterVRButton; enterARButton: #myEnterARButton" >
          <a id="myEnterVRButton" href="#">
            <div id="VRButton">
              <i class="fas fa-expand"></i>
              <i class="fas fa-vr-cardboard"></i>
            </div>
          </a>
          <a id="myEnterARButton" href="#"></a>
  <!-- 360-degree image. -->
  <a-entity rotation="0 0 0" animation="property: rotation; to: 0 360 0; loop: true; dur: 500000; easing: linear">
        <a-sky class = "ARcarousel" id="image-360" radius="100" rotation="0 -90 0" src="{{ site.baseurl }}/assets/img/360/360_dragonfly.jpg"></a-sky>
    </a-entity>
</a-scene>
    <div class = "vr_overlay">  
    <img src="/assets/img/360/360_icon.png">
    </div>
</div>
  <figcaption>A 360° screenshot of Dragonfly</figcaption>

<br>

<!--
## Publication

- Will be added
-->
