---
title:  "Test Page"
excerpt: Testing few things here
layout: projects
selected: "false"
homepage: "false"
fullpage: "no"
header:
    teaser: /assets/img/projects/Cinevoque/icon.png
tags: VR-Film Storytelling Research

banner_image1:
banner_image1_caption:

team_members: "Amarnath Murugan | Amal Dev | Jayesh Pillai"
team_members_align: "text-left"

permalink: projects/testpage

gallery1:
  - url: /assets/images/unsplash-gallery-image-1.jpg
    image_path: /assets/img/projects/Cinevoque/icon.png
    alt: "Image 1"
    title: "Image 1 title caption"
  - url: /assets/images/unsplash-gallery-image-2.jpg
    image_path: /assets/img/projects/Cinevoque/icon.png
    alt: "Image 2"
    title: "Image 2 title caption"
  - url: /assets/images/unsplash-gallery-image-3.jpg
    image_path: /assets/img/projects/Cinevoque/icon.png
    alt: "Image 3"
    title: "Image 3 title caption"

feature_row:
  - image_path: /assets/img/projects/Cinevoque/banner.png
    alt: "Image 1"
    title: "Image 1"
    excerpt: "This is some sample content that goes here with **Markdown** formatting."
  - image_path: /assets/img/projects/Cinevoque/banner.png
    alt: "Image 2"
    title: "Image 2"
    excerpt: "This is some sample content that goes here with **Markdown** formatting."
  - image_path: /assets/img/projects/Cinevoque/banner.png
    alt: "Image 3"
    title: "Image 3"
    excerpt: "This is some sample content that goes here with **Markdown** formatting."

---

<figure class="align-center" style="width:100%;">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/img/projects/Cinevoque/banner.png" alt="">
</figure> 

This is an ongoing work that started out as Amarnath and Amal's summer internship project in 2018. The framework and the experiences built with it has been presented at multiple national and international conferences, which are listed below.


## Abstract

The grammar of storytelling in Cinematic Virtual Reality (CVR) is still evolving and is not as established as traditional movies due to its immersive nature. Unlike traditional films where the director decides the framing of the visuals shown, in CVR, the viewers have control over the point of view (POV). As a result, they are likely to miss important events in the narrative by focusing elsewhere in the virtual environment. In our framework, Cinévoqué,  we take advantage of this feature to present an experience that tries to maintain consistency in the narrative seen by the viewer. It achieves this by following the viewer's gaze and the events in the film that it intersects with; if they miss an event that's pertinent to the rest of the storyline, the framework shifts to an alternate storyline that does not have said event as a presupposition. The transition takes place unbeknownst to the viewer so as not to interrupt the flow of the experience.

![Narrative Structure]({{ site.baseurl }}/assets/img/projects/Cinevoque/storyline.jpg)

Cinévoqué is built for live-action CVR since real-time 3D experiences have the affordance of the framework implicitly. The novelty of this work lies in its intent to bring passive interactivity to an experience composed of live-action videos that are mostly immutable in real-time. Furthermore, adding a layer of real-time changes to live-action VR films allows for new use cases that were not previously possible.  For example, the experiences "Schrödinger's Vada-Pav" and  "Till We Meet Again" that was built with Cinévoqué have a virtual body that rotates to align with the user's physical body using 6DOF controller data.  Similarly, other data can be used to influence the visuals and audio in the experience. 

<iframe width="560" height="315" src="https://drive.google.com/file/d/16j7A_M15lY0TIRJ0muV34p5XB7YugqVP/preview" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>



## Outcomes
This project yielded three films and publications. We also presented our work at five conferences in total. 

### ***Films***

![Film Titles]({{ site.baseurl }}/assets/img/projects/Cinevoque/titles.jpg)

{% include gallery id="gallery1" caption="This is a sample gallery with **Markdown support**." %}

{% include feature_row %}

**Schrödinger's Vada-Pav** was the first film made with Cinévoqué. It had the simplest narrative structure for a multi-storyline film, with two possible endings. The story goes as follows: Schrödinger(viewer) is in his office watching a video on Schrödinger's cat, and he orders a Vada-Pav (a local Indian snack), when the waiter brings the order he knocks on the office door and peeks in. Depending on the viewer turning back to look at him, the Vada-pav is delivered or isn't. This exploration made the challenges involved in shooting such a film apparent and also helped us think of improvements and changes to the initial framework.

**Shapeshifter** is a relatively complex film built to test the limitations of the framework post Schrödinger's Vada-Pav. The experience had four possible storylines. The film's setting was that three people (including the viewer) were stuck in an office during an invasion by a shape-shifting alien species. Depending on the details the viewer sees, the ending could reveal one of the three as an alien or show an alien entering the office. The framework version used for this had many limitations; it did not support stereo video and spatial audio, and it also needed improvements in handling transitions. 

[**Till We Meet Again**]({{ site.baseurl }}/projects/twma) was our first attempt at creating a film meant for public viewing. It is a stereoscopic 3D film that has eight possible storylines with different genres.  It incorporated the learnings from the previous films and built with improvements to the frameworks. This film was presented as a demo at VRCAI 2019 in Brisbane, Australia. 

### ***Publications***

- Pillai, Jayesh S., Amal Dev, and Amarnath Murugan. "Till We Meet Again: A Cinévoqué Experience." The 17th International Conference on Virtual-Reality Continuum and its Applications in Industry. ACM, 2019.

- Murugan, Amarnath, Jayesh S. Pillai, and Amal Dev. "Cinévoqué: Development of a Passively Responsive Framework for Seamless Evolution of Experiences in Immersive Live-Action Movies." 25th ACM Symposium on Virtual Reality Software and Technology. ACM, 2019.

- Pillai, Jayesh S., Amarnath Murugan, and Amal Dev. "Cinévoqué: Design of a Passively Responsive Framework for Seamless Evolution of Experiences in Immersive Live-Action Movies." IFIP Conference on Human-Computer Interaction. Springer, Cham, 2019.

### ***Talks***

We were invited to speak about Cinévoqué at Unite India 2018, third ACM SIGCHI Asian Symposium and IndiaHCI 2019.

![Conference Talks]({{ site.baseurl }}/assets/img/projects/Cinevoque/talks.jpg)



