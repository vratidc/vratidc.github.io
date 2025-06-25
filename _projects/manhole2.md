---
title:  "Into the Manhole"
excerpt: 6DoF VR Narrative
layout: manholeprojectspage   
selected: "true"
homepage: "true"
fullpage: "yes"
active: "yes"
manholeproject: "yes"
date: 20250102

og_image: /assets/img/projects/manholeproject/manhole2_teaser_small.jpg

header:
    image: /assets/img/projects/manholeproject/manhole2_header.gif
    teaser: /assets/img/projects/manholeproject/manhole2_teaser.png

tags: VR Narrative Research

banner_image1: 

team_members: "Jayesh Pillai | Abhishek Verma | Banda Shiva Teja | Ananda Bathena"
team_members_align: "text-left"

permalink: projects/into-the-manhole

gallery1:
  - url: https://imxd.in/
    image_path: /assets/img/projects/manholeproject/manhole_img/partners_logo_imxdlab.png
    alt: "IMXD Lab"
    title: "IMXD Lab"
  - url: https://www.idc.iitb.ac.in/
    image_path: /assets/img/projects/manholeproject/manhole_img/partners_logo_idc.png
    alt: "IDC School of Design, IIT Bombay"
    title: "IDC School of Design, IIT Bombay"
  - url: https://www.deckor.co/
    image_path: /assets/img/projects/manholeproject/manhole_img/partners_logo_deckor.png
    alt: "Deckor.co"
    title: "Deckor.co"    

---

<strong>Synopsis: </strong> <i>“Compelled by the exigencies of poor economic life and caste identity, Amitabh, a young law graduate, becomes a manual scavenger. One day, to earn some extra money to support his family, he decides to get inside a large unsafe sewer to clear a blockage. He neither has protective gear, nor the accompanying engineer to check for poisonous gases. Will Amitabh come out safely?”</i>
<br><br>

This is a 6 degrees-of-freedom (6DoF) VR narrative experience created using the Unreal game engine. This experience is part of a <a href="{{ site.url }}{{ site.baseurl }}/manhole-project" target="_blank" style="color:#cc9200;">larger project</a>  that aims to spread awareness about the dangers of manual scavenging in India.

<br>
{% include video id="-4-xjF6OTHM" provider="youtube" %}
<figcaption>Into the Manhole - Trailer</figcaption>
<br>


## Introduction

In the evolving landscape of film and storytelling, Virtual Reality (VR) is emerging as a transformative medium. Unlike traditional films constrained by a static frame, VR offers a 360-degree canvas that allows audiences to explore stories from multiple perspectives and move within the environment. This shift from passive observation to active participation poses both thrilling opportunities and intricate challenges for narrative creators. Among the vanguard projects exploring this new frontier is "Into the Manhole" a pioneering work that merges the boundaries between film and interactive gaming.
<br><br>
Directed by Jayesh Pillai and Abhishek Varma, with technical direction by Banda Shiva Teja, and sound design & background score by Ananda Bathena, this project ventures into the harsh realities faced by manual scavengers in India, blending compelling storytelling with real-time VR immersion.
<br><br>

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
        <a-sky class = "ARcarousel" id="image-360" radius="100" rotation="0 -90 0" src="{{ site.baseurl }}/assets/img/projects/manholeproject/ITM_img/ITM_360.jpg"></a-sky>
    </a-entity>
</a-scene>
    <div class = "vr_overlay">  
    <img src="/assets/img/360/360_icon.png">
    </div>
</div>
  <figcaption>A 360° view from the VR Narrative</figcaption>


## Design and Development

### 1. Ideation and Narrative Structure

The genesis of "Into the Manhole" lies in its meticulously crafted narrative. From the initial concept, the goal was to create a non-linear storytelling experience that fully immerses viewers in the plight of its characters. By presenting the story in a way that allows users to explore and interact with the environment, the film aims to foster a deep emotional connection and a heightened sense of empathy.

<figure class="align-center" style="width:100%;">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/img/projects/manholeproject/ITM_img/ITM_screenshot1.jpg" alt="ITM_screenshot1">
  <figcaption>A screenshot from the experience: Amitabh and Bunty looking into the manhole.</figcaption>
</figure> 
<br>


### 2. Production Insights

The production phase of "Into the Manhole" was characterized by a detailed and systematic approach.
Actors and Rehearsals: The casting process was integral to ensuring that the performances conveyed authenticity and emotional depth. Rigorous rehearsals and a talented cast brought the narrative to life, making the harrowing conditions of manual scavenging palpable. 

<figure class="align-center" style="width:100%;">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/img/projects/manholeproject/ITM_img/ITM_mocap.jpg" alt="ITM - Mocap and Facecap">
</figure>
<br>
Filming and Motion Capture: State-of-the-art motion capture technology played a crucial role in capturing nuanced performances. This technology, coupled with efficient filming workflows, allowed for a seamless integration of motion and dialogue, enhancing the immersive quality of the film.
<br>

### 3. Post-Production

Data Processing and Unreal Engine Integration: Advanced processing techniques were used to refine the raw footage, and Unreal Engine was utilized to build a dynamic, interactive world. This phase was critical in turning conceptual ideas into a vivid, engaging VR experience.
<br>
Final Polish and Optimization: The post-production process included enriching the virtual environment with detailed visual and auditory elements. Innovative material adjustments and optimization efforts ensured that the film delivered high performance across various platforms, maintaining both quality and viewer engagement.
<br><br>

## Impact and Future Directions

"Into the Manhole" is more than just a VR film; it's a catalyst for conversation and change. By immersing viewers in the dangerous and degrading conditions faced by manual scavengers, the project seeks to raise awareness and inspire empathy. The film stands as a testament to the power of VR storytelling, demonstrating how this medium can be used to drive social impact and provoke meaningful dialogue.

Looking ahead, future explorations in VR storytelling will likely delve into optimizing resource use, enhancing narrative interactivity, and leveraging real-time data to tailor experiences. As we continue to push the boundaries of what VR can achieve, projects like "Manhole VR" will undoubtedly serve as a beacon for innovative storytelling in this immersive medium.
<br><br>

<figure class="align-center" style="width:100%;">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/img/projects/manholeproject/ITM_img/ITM_screenshot2.jpg" alt="ITM_screenshot2">
  <figcaption>A screenshot from the experience: Amitabh clearing the sludge.</figcaption>
</figure> 
<br>

## Conclusion

"Into the Manhole" exemplifies the potential of Virtual Reality to transform storytelling. By creating an experience that blends film and interactive elements, the project not only showcases the power of VR but also highlights important social issues. As we step into this new dimension of storytelling, "Manhole VR" stands as a pioneering example of how technology and narrative can come together to create profound and impactful experiences.
<br><br>

<br>

<hr style="height:1px;border-width:0;color:#fcd5ce;background-color:#fcd5ce">

## Collaborators

  {% include gallery id="gallery1" %}

<figcaption style="text-align: left; margin-top: 0px;">The production of the VR Narrative was supported by IRCC, IIT Bombay.</figcaption>


<hr style="height:1px;border-width:0;color:#fcd5ce;background-color:#fcd5ce">

## Core Team

<div class="people" style="display:grid">

  <div class="entries-grid">

  <div class="people_grid__item_4">
  <article class="people__item" itemscope="" itemtype="https://schema.org/CreativeWork">  
  <div class="people__item-teaser" style="background-image: url(/assets/img/projects/manholeproject/manhole_img_people/ITM_abhishek.png); background-size: cover;background-position: center;">
  </div>
  <h2 class="people__item-title" itemprop="headline"  style="text-align: center;">Abhishek Verma</h2>
  <p style="margin-bottom: 0px; text-align: center;" class="people__item-excerpt" itemprop="description">Writer & Director</p>
  </article>
  </div>

  <div class="people_grid__item_4">
  <article class="people__item" itemscope="" itemtype="https://schema.org/CreativeWork">  
  <div class="people__item-teaser" style="background-image: url(/assets/img/projects/manholeproject/manhole_img_people/ITM_jayesh.png); background-size: cover;background-position: center;">
  </div>
  <h2 class="people__item-title" itemprop="headline"  style="text-align: center;">Jayesh Pillai</h2>
  <p style="margin-bottom: 0px; text-align: center;" class="people__item-excerpt" itemprop="description">VR Director</p>
  </article>
  </div>

  <div class="people_grid__item_4">
  <article class="people__item" itemscope="" itemtype="https://schema.org/CreativeWork">  
  <div class="people__item-teaser" style="background-image: url(/assets/img/projects/manholeproject/manhole_img_people/ITM_shiva.png); background-size: cover;background-position: center;">
  </div>
  <h2 class="people__item-title" itemprop="headline"  style="text-align: center;">Banda Shiva Teja</h2>
  <p style="margin-bottom: 0px; text-align: center;" class="people__item-excerpt" itemprop="description">Technical Director</p>
  </article>
  </div>

  <div class="people_grid__item_4">
  <article class="people__item" itemscope="" itemtype="https://schema.org/CreativeWork">  
  <div class="people__item-teaser" style="background-image: url(/assets/img/projects/manholeproject/manhole_img_people/ITM_ananda.png); background-size: cover;background-position: center;">
  </div>
  <h2 class="people__item-title" itemprop="headline"  style="text-align: center;">Ananda Bathena</h2>
  <p style="margin-bottom: 0px; text-align: center;" class="people__item-excerpt" itemprop="description">Sound Design & Background Score</p>
  </article>
  </div>


  </div>

</div>

<hr style="height:1px;border-width:0;color:#fcd5ce;background-color:#fcd5ce">

<div class="manhole-team-links" style="min-width: 45%; margin-top: 0px; padding-bottom: 0px; padding-right: 0px;padding-left: 0; display: inline-block; vertical-align : top;">
  <h3 id="page-title" class="page__title" style="margin-top: 20px;">Cast (Voice & Mocap)</h3>
  <p><small>
    <a href="https://www.linkedin.com/in/aniruddha-deodhar-040534223?" target="_blank"><b>Aniruddha Deodhar</b></a> : Bunty Ram<br>
    <a href="https://www.linkedin.com/in/adarsh-kumar-85a91a272/" target="_blank"><b>Gandharva Walavalkar</b></a> : Amitabh Ruth<br>
    <a href="https://www.linkedin.com/in/adarsh-kumar-85a91a272/" target="_blank"><b>Adarsh Kumar</b></a> : Amitabh Ruth<br>
    <a href="http://linkedin.com/in/gvsree" target="_blank"><b>G V Sreekumar</b></a> : Angry Uncle<br>
  </small></p>
</div>  

<div class="manhole-team-links" style="min-width: 50%; margin-top: 0px; padding-bottom: 0px; padding-right: 0px;padding-left: 0; display: inline-block; vertical-align : top;">
  <h3 id="page-title" class="page__title" style="margin-top: 20px;">Production Team</h3>
  <p><small>
    <a href="https://www.linkedin.com/in/artarivu/" target="_blank"><b>Arivukkarasu Periyasamy</b></a> : MoCap Cleanup & Character Animation<br>
    <a href="https://www.linkedin.com/in/harshal-yadav-125a8a195/" target="_blank"><b>Harshal Yadav</b></a> : MoCap Cleanup & Character Animation<br>
    <a href="https://www.linkedin.com/in/uttham-prakash-926024286/" target="_blank"><b>Uttham Prakash</b></a> : Unreal Technical Artist<br>
    <a href="https://www.linkedin.com/in/zecharia-s-490853261/" target="_blank"><b>Zechariah Sari</b></a> : Unreal Technical Artist<br>
    <a href="https://www.linkedin.com/in/muskan-ahuja-918aab222/" target="_blank"><b>Muskan Ahuja</b></a> : Additional 3D Modeling & Texturing<br>
    <a href="https://www.linkedin.com/in/bishal-brahma-543678312/" target="_blank"><b>Bishal Brahma</b></a> : Additional 3D Modeling & Texturing<br>
    <a href="https://www.linkedin.com/in/pranjal-saini-609911225/" target="_blank"><b>Pranjal Saini</b></a> : Posters & Branding<br>
    <a href="https://www.behance.net/nandhinsreekum1" target="_blank" style="color:#cc9200;"><b>Nandhini Sreekumar</b></a> : Posters & Branding<br>
  </small></p>
</div>

<hr style="height:1px;border-width:0;color:#fcd5ce;background-color:#fcd5ce">


