---
title:  "Till We Meet Again"
excerpt: A Cinévoqué Experience
layout: projects   
selected: "true"
homepage: "true"
fullpage: "yes"
active: "yes"

header:
    teaser: /assets/img/projects/twma/twma-thumbnail.jpg
tags: VR-Film Storytelling  

banner_image1:
banner_image1_caption:

team_members: " Amal Dev | Amarnath Murugan | Jayesh Pillai"
team_members_align: "text-left"

permalink: projects/twma
---

<figure class="align-center" style="width:100%;">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/img/projects/twma/twma_poster.jpg" alt="twma_banner">
</figure> 

Till We Meet Again is a multi-storyline live-action VR film that was built with [Cinévoqué]({{ site.baseurl }}/projects/Cinevoque).

<br>

## Abstract

This film presents an emotional journey of a small family, as seen from the father's perspective. The user would be immersed in a space that is dear to the character, who is waiting for something or someone. Based on the users' point of view and attention to specific details within that space, the story unfolds. In addition to the 360° narrative, this film presents the user with a stereo 3D and spatial audio experience. The experience has six possible endings and eight storylines. 

<figure class="align-center" style="width:100%;">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/img/projects/twma/twma_narrative.jpg" alt="twma_narrative">
  <figcaption>Branching structure of Till We Meet Again</figcaption>
</figure> 


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
    <img id="twma1" src="{{ site.baseurl }}/assets/img/projects/twma/360_twma_1.jpg">
    <img id="twma3" src="{{ site.baseurl }}/assets/img/projects/twma/360_twma_3.jpg">
    <img id="twma2" src="{{ site.baseurl }}/assets/img/projects/twma/360_twma_2.jpg">
    <img id="twma4" src="{{ site.baseurl }}/assets/img/projects/twma/360_twma_4.jpg">
  </a-assets>
  <!-- 360-degree image. -->
  <a-entity rotation="0 0 0" animation="property: rotation; to: 0 -360 0; loop: true; dur: 500000; easing: linear">
        <a-sky class = "ARcarousel" id="image-360" radius="100" rotation="0 -90 0" src="#twma1"></a-sky>
    </a-entity>
  </a-scene>
    <div class = "vr_overlay">  
    <img src="/assets/img/360/360_icon.png">
    </div>
</div>

  <figcaption>360° screenshots of Till We Meet Again</figcaption>

<br>
Each storyline has a different genre and the storylines are completely unlike each other. 

<figure class="align-center" style="width:100%;">
  <img src="{{ site.baseurl }}/assets/img/projects/twma/endings.jpg" alt="twma_endings">
  <figcaption>Possible storylines of Till We Meet Again</figcaption>
</figure> 

<br>

## Outcomes

This work was presented as a demo at VRCAI 2019 in Brisbane, Australia. 

<figure class="align-center" style="width:100%;">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/img/projects/twma/twma_vrcai.jpg" alt="twma_vrcai">
  <figcaption>Demo at VRCAI 2019</figcaption>
</figure> 

<br>

### **Publication**

- Pillai J.S., Murugan A. and Dev A. (2019). "Till We Meet Again: A Cinévoqué Experience (Demo)", in: 17th ACM SIGGRAPH International Conference on Virtual Reality Continuum and Its Applications in Industry (VRCAI) 2019, Brisbane, Australia.


<script>

    var slideIndex = 0;
    ARcarousel();

function carousel() {
  var i;
  var x = document.getElementsByClassName("mySlides");
  for (i = 0; i < x.length; i++) {
    x[i].style.display = "none";
  }
  slideIndex++;
  if (slideIndex > x.length) {slideIndex = 1}
  x[slideIndex-1].style.display = "inline";
  setTimeout(carousel, 5000); // Change image every 2 seconds
}
    
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
            p.setAttribute('src','#twma1');
        }
    else
    if(slideIndex == 2)
        {
            p.setAttribute('src','#twma3');
        }
    else
    if(slideIndex == 3)
        {
            p.setAttribute('src','#twma2');
        }
    else
    if(slideIndex == 4)
        {
            p.setAttribute('src','#twma4');
        }

  setTimeout(ARcarousel, 7000); // Change image every few seconds
}

</script>
  
