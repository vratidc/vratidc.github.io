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
  - aspect: "4/3"
    url: 
    image_path: /assets/img/projects/fina/Hand_Tracking_Possiblities_Fina.gif
    alt: ""
    title: ""
  - aspect: "4/3"
    url:
    image_path: /assets/img/projects/fina/Ray_Casting_Kebab_Fina.gif
    alt: ""
    title: ""

gallery2:
  - url: 
    image_path: /assets/img/projects/fina/fina8.svg
    alt: "Fina 10"
    title: "Fina 10"


gallery3:
  - aspect: "1/2"
    url: 
    image_path: /assets/img/projects/fina/fina2.gif
    alt: "Fina 1"
    title: "Pinch and pull an item to select it. To select multiple files, pinch and pull each one; they’ll stay on the Active Plane."
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
    alt: "While grabbing the stack with one hand, grab the newly created Duplicate prompt with the other hand to create a copy of the stack."
    title: "While grabbing the stack with one hand, grab the newly created Duplicate prompt with the other hand to create a copy of the stack."
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


Given that UI in popular VR headsests still uses raycasting as the default interaction method, we imagine, prototype and showcase how interactions can be made more tangible and literal by utilising full hand tracking by designing a file management scenario.

<figure class="align-center" style="width:100%;">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/img/projects/fina/fina11.jpg" alt="fina13">
  <figcaption> </figcaption>
</figure>

### Raycasting in File Management

File management in the Meta Quest 2 is currently almost exactly the way it would be on a 2D touchscreen device. Notice the presence of kebab menus for basic tasks like delete and the lack of basic tasks like move or copy.

{% include gallery_captions id="gallery1" caption="The Raycasting interaction method. Source: Meta.com" %}


## File Management

### Let's not reinvent the wheel

When displaying text-based interfaces, a rectilinear layout is the most practical and efficient way to organise elements. So, if we are to design a truly immersive experience that remains usable and efficient, we need to follow some guidelines of 2D design. A 3 dimensional, 6 degrees of freedom interface would be fun to conceptualize but would also probably be extremely unusable with larger organizational systems.

<figure class="align-center" style="width:100%;">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/img/projects/fina/fina1.png" alt="fina3">
  <figcaption>We designed a 2.5D interface — two-dimensional UI with an additional interactive plane on top</figcaption>
</figure>

### Our two core interactions are —

<div class="ulist" markdown="1">
- **Pinching:** Pinching is the act of picking a single object — making a precise choice — so we used it as a metaphor for selecting and manipulating individual items.

- **Grabbing:** Grabbing is done to grasp larger objects, maybe to command objects to compress or fall together. Thus, we used grabbing as a metaphor to manipulate a group of multiple files.
</div>

<br>

## Interactions

### Selecting individual files



{% include gallery_captions id="gallery3" caption="" %}


### Selecting a range and Moving files to clipboard

Pinch and pull the first file of the range to be selected. Without letting go, pinch and pull the last file of the range to select all the files in between the two.

{% include gallery_captions id="gallery4" %}

You can move the stack near the Clipboard and release to move the files to the clipboard. The files will no longer remain in the parent folder.


### Copying files to clipboard and Deleting a selection

{% include gallery_captions id="gallery5" caption="" %}

While grabbing the stack with one hand, grab the newly created Duplicate prompt with the other hand to create a copy of the stack. You can drop the copied stack onto the Clipboard and release the original stack.


WLook down to open the Delete Portal. If you hover a file or a stack directly above it and let go, it will get sucked into the portal and get deleted.


<br>

## Mitosis inspired Copy action

The interaction for creating a copy was inspired from Mitosis — the process of cell division. You would create an identical copy by ‘splitting’ the original file in two using both hands.

{% include flexgallery id="gallery2" %}

However, as this Interaction A wasn’t immediatly evident to users, we iteratively arrived at Interaction B which spawns a copy of the file when you grab the Copy prompt. This had the essence of the first interaction but gave a clear prompt and can also be implemented for other contextual menu options.

### Clipboard Semantics

A traditional clipboard works by referencing the location of files. When you press Paste, it either moves or duplicates the file depending on the initial action. The conceptual model we wanted to build was more like a temporary folder — the action of dropping a file onto the clipboard moves the actual file to it. The user can choose to duplicate the file before moving it to the clipboard.  We believe this will generate a clearer mental model and work with our interactions better.

### Delete Mechanism

Deleting files should require confirmation from the user such as a ‘Are you sure you want to delete?’ prompt. It should essentially be a two-step process to avoid accidental deletion of files. We added an extra step to the process — the Delete Portal doesn’t open unless it is in your view, unless you actively look down — so files won’t get deleted if you accidently let go of them above the portal.

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





