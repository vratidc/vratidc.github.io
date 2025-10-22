---
title:  "Fina: File Management Interactions"
excerpt: Real-Time VR Film
layout: projects
selected: "false"
homepage: "false"
fullpage: "yes"
active: "no"

header:
    teaser: /assets/img/projects/fina/fina1.png
tags: VR Research

banner_image1: /assets/img/projects/fina/fina_thumb.png
banner_image1_caption:

team_members: "Atish Waghwase | Prafulla Chandra GS | Cherian Jeremiah Iype | Apoorv Anurag"
team_members_align: "text-left"

permalink: projects/fina


gallery1:
  - aspect: "1/2"
    url: 
    image_path: /assets/img/projects/fina/Hand_Tracking_Possiblities_Fina.gif
    alt: ""
    title: ""
  - aspect: "1/2"
    url:
    image_path: /assets/img/projects/fina/Ray_Casting_Kebab_Fina.gif
    alt: ""
    title: ""

gallery2:
  - url: 
    image_path: /assets/img/projects/fina/interaction_fina.png
    alt: "Fina 10"
    title: "Fina 10"


gallery3:
  - aspect: "1/2"
    url: 
    image_path: /assets/img/projects/fina/fina2.gif
    alt: "Fina 1"
    title: "Pinch and pull an item to select it. To select multiple files."
  - aspect: "1/2"
    url:
    image_path: /assets/img/projects/fina/fina3.gif
    alt: "Fina 2"
    title: "Grab the selection on the Active Plane to stack and move it anywhere."  

gallery4:
  - aspect: "1"
    url: 
    image_path: /assets/img/projects/fina/fina4.gif
    alt: "Fina 1"
    title: "Pinch and pull the first file, then, without releasing, pinch and pull the last to select all files in between."
  - aspect: "2"
    url:
    image_path: /assets/img/projects/fina/fina5.gif
    alt: "Move the stack near the Clipboard and release to transfer the files. They’ll be removed from the parent folder."
    title: "Move the stack near the Clipboard and release to transfer the files. They’ll be removed from the parent folder." 

gallery5:
  - aspect: "1/2"
    url: 
    image_path: /assets/img/projects/fina/fina6.gif
    alt: "While holding the stack with one hand, grab the Duplicate prompt with the other to create its copy."
    title: "While holding the stack with one hand, grab the Duplicate prompt with the other to create its copy."
  - aspect: "1/2"
    url:
    image_path: /assets/img/projects/fina/fina7.gif
    alt: "Look down to open the Delete Portal."
    title: "Look down to open the Delete Portal."

---
<br>
## Introduction

Most VR headsets still use ray-casting as the default interaction method, which mimics pointer-based interactions for screen-based interfaces. In this project, we imagine, prototype, and showcase how actions like copying, moving, selecting, and deleting files can be made more appropriate for an immersive VR experience through interactions like hovering, poking, pinching, grabbing, and releasing. We showcase our ideas through a file management interface for the Meta Quest 2.

<br>


<figure class="align-center" style="width:100%;">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/img/projects/fina/fina11.jpg" alt="fina13">
  <figcaption>Laval Virtual 2023
 </figcaption>
</figure>
<br>



### Raycasting in File Management

File management in the Meta Quest 2 is currently almost exactly the way it would be on a 2D touchscreen device. Notice the presence of kebab menus for basic tasks like delete and the lack of basic tasks like move or copy.

{% include gallery_captions id="gallery1" caption="The Raycasting interaction method. Source: Meta.com" %}


## File Management

### Let's not reinvent the wheel

When displaying text-based interfaces, a rectilinear layout is the most practical and efficient way to organise elements. So, if we are to design a truly immersive experience that remains usable and efficient, we need to follow some guidelines of 2D design. A 3 dimensional, 6 degrees of freedom interface would be fun to conceptualize but would also probably be extremely unusable with larger organizational systems.

<figure class="align-center" style="width:100%;">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/img/projects/fina/fina1.png" alt="fina3">
  <figcaption>We designed a 2.5D interface, two-dimensional UI with an additional interactive plane on top</figcaption>
</figure>

### Our two core interactions are —

<div class="ulist" markdown="1">
- **Pinching:** Pinching is the act of picking a single object making a precise choice, so we used it as a metaphor for selecting and manipulating individual items.

- **Grabbing:** Grabbing is done to grasp larger objects, maybe to command objects to compress or fall together. Thus, we used grabbing as a metaphor to manipulate a group of multiple files.
</div>

<br>

## Interactions
<br>
### Selecting individual files
{% include gallery_captions id="gallery3" caption="" %}
### Selecting a range and Moving files to clipboard
{% include gallery_captions id="gallery4" %}
### Copying files to clipboard and Deleting a selection
{% include gallery_captions id="gallery5" caption="" %}

## Mitosis inspired Copy action

Since Interaction A wasn’t immediately clear to users, we refined it into Interaction B, which grabs the Copy prompt and now spawns a duplicate of the file, preserving the original intent while offering clarity and consistency across contextual options. Unlike traditional clipboards that reference file locations, ours acts as a temporary folder where dropping a file moves it directly, with the option to duplicate before moving for a clearer mental model. Deletion remains a deliberate two-step process, as the Delete Portal appears only when in view, preventing accidental deletions.

{% include flexgallery id="gallery2" caption="The copy interaction was inspired by Mitosis, the process of cell division, where an identical copy is created by ‘splitting’ the original file in two using both hands.
" %}

<br>

## Exhibition

We designed an early proof of concept to experience interactions in 3D using Gravity Sketch — a VR 3D modelling tool. This was used to get initial feedback on the interactions.

<figure class="align-center" style="width:100%;">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/img/projects/fina/fina10.gif" alt="fina12">
  <figcaption>Exhibition at IDC School of Design, September 2022.</figcaption>
</figure>


<figure class="align-center" style="width:100%;">
  {% include video id="_9cq1qVikcU" provider="youtube" %}
</figure> 







