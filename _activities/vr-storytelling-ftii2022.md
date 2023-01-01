---
title:  "Introduction to VR Filmmaking"
type: "Workshop"
publication: "no"
activity: "yes"
authors: "Jayesh Pillai and Amal Dev"
year: "2022"
date: 2022-12-17

venue: "Art Direction & Production Design, Film and Television Institute of India (FTII) Pune"
excerpt: Workshop & Invited Talk at FTII Pune
homepage: "no"
fullpage: "no"
permalink: workshops/FTII2022/
header:
    teaser: /assets/img/activities/icon-pub-ftii.jpg
layout: publications  

gallery1:
  - url: /assets/img/publications/workshops/ftii2018/ftii_workshop1.jpg
    image_path: /assets/img/publications/workshops/ftii2018/ftii_workshop1.jpg
    alt: "FTII Workshop"
    title: "FTII Workshop"
  - url: /assets/img/publications/workshops/ftii2018/ftii_workshop2.jpg
    image_path: /assets/img/publications/workshops/ftii2018/ftii_workshop2.jpg
    alt: "FTII Workshop"
    title: "FTII Workshop"
  - url: /assets/img/publications/workshops/ftii2018/ftii_workshop3.jpg
    image_path: /assets/img/publications/workshops/ftii2018/ftii_workshop3.jpg
    alt: "FTII Workshop"
    title: "FTII Workshop"
  - url: /assets/img/publications/workshops/ftii2018/ftii_workshop4.jpg
    image_path: /assets/img/publications/workshops/ftii2018/ftii_workshop4.jpg
    alt: "FTII Workshop"
    title: "FTII Workshop"

---

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
        <a-sky class = "ARcarousel" id="image-360" radius="100" rotation="0 -90 0" src="{{ site.baseurl }}/assets/img/publications/workshops/ftii2018/360_ftii_facourse.jpg"></a-sky>
    </a-entity>
</a-scene>
    <div class = "vr_overlay">  
    <img src="/assets/img/360/360_icon.png">
    </div>
</div>
  <figcaption>Participants at the Talk</figcaption>

<br>


## Workshop

The VR filmmaking workshop was an introductory workshop for the students of Art Direction & Production Design at FTII Pune. The students went through a hands-on process of creating a  360° film narrative, from pre-prodcution to experiencing.


{% include gallery id="gallery1" layout="half" caption="Images from the Workshop" %}

## ***Outcomes***

The workshop concluded with students creating two 360° film narratives (Replaced & Vrida), produced within the campus.

<!-- 360-degree image embed. -->
<div class = "vr_single">
<a-scene loading-screen="dotsColor: white; backgroundColor: #008055;" class = "" embedded vr-mode-ui="enabled: false" style="margin:0px; padding:0px;">
  <!-- 360-degree image. -->
  <a-entity rotation="0 0 0" animation="property: rotation; to: 0 360 0; loop: true; dur: 500000; easing: linear">
        <a-sky class = "ARcarousel" id="image-360" radius="100" rotation="0 -90 0" src="{{ site.baseurl }}/assets/img/publications/workshops/ftii2018/360_ftii_replaced.jpg"></a-sky>
    </a-entity>
</a-scene>
</div>
  <figcaption>360° Poster of 'Replaced'</figcaption>

<br>

<!-- 360-degree image embed. -->
<div class = "vr_single">
<a-scene loading-screen="dotsColor: white; backgroundColor: #008055;" class = "" embedded vr-mode-ui="enabled: false" style="margin:0px; padding:0px;">
  <!-- 360-degree image. -->
  <a-entity rotation="0 0 0" animation="property: rotation; to: 0 360 0; loop: true; dur: 500000; easing: linear">
        <a-sky class = "ARcarousel" id="image-360" radius="100" rotation="0 -90 0" src="{{ site.baseurl }}/assets/img/publications/workshops/ftii2018/360_ftii_vrida.jpg"></a-sky>
    </a-entity>
</a-scene>
</div>
  <figcaption>360° Poster of 'Vrida'</figcaption>

<br>
