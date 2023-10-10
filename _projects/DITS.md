---
title:  "Death in the Suburbs"
excerpt: Interactive 360° Immersive Mystery Story
layout: projects   
selected: "false"
homepage: "false"
fullpage: "no"
active: "no"
date: 20231005

header:
    teaser: /assets/img/projects/twma/twma-thumbnail.jpg
tags: VR-Film Storytelling  

banner_image1:
banner_image1_caption:

team_members: "Sanat Prasad | Jayesh Pillai"
team_members_align: "text-left"

permalink: projects/deathinthesuburbs

gallery1:
  - aspect: "16/9"
    url:
    image_path: /assets/img/projects/dits/image_1.png
    alt: "Information card inside the AR story"
    title: "Information card inside the AR story"
  - aspect: "16/9"
    url:
    image_path: /assets/img/projects/dits/image_2.png
    alt: "Final conclusion of the investigation"
    title: "Final conclusion of the investigation"

gallery2:
  - aspect: "4/3"
    url:
    image_path: /assets/img/projects/dits/user_testing_gif_1.gif
    alt: "Information card inside the AR story"
    title: "Information card inside the AR story"
  - aspect: "4/3"
    url:
    image_path: /assets/img/projects/dits/user_testing_gif_2.gif
    alt: "Final conclusion of the investigation"
    title: "Final conclusion of the investigation"

---

<figure class="align-center" style="width:100%;">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/img/projects/dits/thumbnail.png" alt="twma_banner">
</figure> 

## Introduction

‘Death in the Suburbs’ is an interactive 360° detective story, designed to place the user at the centre and make them feel like the detective conducting the investigation, rather than merely observing it as a bystander.

## Outcomes

The experience was prototyped on Wonda VR, and can be [accessed here](https://wvr.li/1ltg21){:target="_blank"}

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
  <a-assets>
            <!-- Images. -->
    <img id="dits1" src="{{ site.baseurl }}/assets/img/projects/dits/360_dits_1.jpg">
    <img id="dits2" src="{{ site.baseurl }}/assets/img/projects/dits/360_dits_2.jpg">
    <img id="dits3" src="{{ site.baseurl }}/assets/img/projects/dits/360_dits_3.jpg">
    <img id="dits4" src="{{ site.baseurl }}/assets/img/projects/dits/360_dits_4.jpg">
  </a-assets>
  <!-- 360-degree image. -->
  <a-entity rotation="0 0 0" animation="property: rotation; to: 0 -360 0; loop: true; dur: 50000; easing: linear">
        <a-sky class = "ARcarousel" id="image-360" radius="100" rotation="0 -90 0" src="#dits1"></a-sky>
    </a-entity>
  </a-scene>
    <div class = "vr_overlay">  
    <img src="/assets/img/360/360_icon.png">
    </div>
</div>
<figcaption>The 360° view of the rooms in Abhishek's apartment</figcaption>

Abhishek, 24, is found dead in his apartment from an unusual neck wound. A private investigator, Sanjay Sharma, is called in to investigate the death. Sharma searches all the rooms of the apartment while questioning all three others who lived there with Abhishek. Each of them could potentially be the killer, and the user embodies Sharma as he combs through all the evidence to figure out who it was, and why.

{% include video id="1kn5x9rbCha343ma_hktVl8U7pbJd2S2d" provider="google-drive" %}
<figcaption>Prototype video - user interacting with the 360° detective story</figcaption>
<br> 

{% include gallery id="gallery1" caption="Clue card & final investigation conclusion" %}

## User testing

{% include gallery id="gallery2" caption="User-testing with WondaVR" %}

The experience takes place within a virtual house, and the user has freedom to enter all the rooms and look around. The environment also contains hotspots that users can press to receive information through clue cards and audio. As with any investigation, the real clues are within a pool of irrelevant clues and red herrings, and the user has to decipher which ones are the real clues. They get to select which character they suspect before the truth is revealed.

## Experience Structure

<img src="{{ site.baseurl }}/assets/img/projects/dits/experience_structure.png">

<script>

    var slideIndex = 0;
    ARcarousel();
    
    function ARcarousel() {
      var i;
        var x = document.getElementsByClassName("ARcarousel");
        var p = document.querySelector('a-sky');
        
      slideIndex++;
        
      if (slideIndex > 4) 
      {
          slideIndex = 1;
      }
        
        if(slideIndex == 1)
            {
                p.setAttribute('src','#dits1');
            }
        else
        if(slideIndex == 2)
            {
                p.setAttribute('src','#dits2');
            }
        else
        if(slideIndex == 3)
            {
                p.setAttribute('src','#dits3');
            }
        else
        if(slideIndex == 4)
            {
                p.setAttribute('src','#dits4');
            }

      setTimeout(ARcarousel, 7000); // Change image every 7 seconds
    }

</script>