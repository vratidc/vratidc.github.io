---
layout: projectspage
title: "Activities Archive"
permalink: archive
---


<style>
.gallery {
  display: flex;
  flex-wrap: wrap;
  gap: 12px;
  margin-bottom: 10px;
}
.gallery img {
  width: 275px;
  height: 180px;
  cursor: pointer;
  border-radius: 4px;
  box-shadow: 0 2px 6px rgba(0,0,0,0.15);
}
#lightbox {
  display: none;
  position: fixed;
  z-index: 1000;
  top: 0; left: 0;
  width: 100%; height: 100%;
  background: rgba(0,0,0,0.85);
  justify-content: center;
  align-items: center;
  flex-direction: column;
}
#lightbox img {
  max-width: 90%;
  max-height: 80vh;
  margin-bottom: 1rem;
}
#lightbox p {
  color: white;
  font-size: 16px;
  text-align: center;
}
.lightbox-nav {
  display: flex;
  justify-content: space-between;
  width: 100%;
  max-width: 700px;
  margin-top: 10px;
}
.lightbox-btn {
  color: white;
  font-size: 20px;
  cursor: pointer;
  padding: 10px 20px;
  user-select: none;
}
.lightbox-btn:hover {
  background: rgba(255,255,255,0.1);
}
</style>

<h2>Lab Activities</h2>
<h3>2025</h3>

<h4>July</h4>
<div class="gallery">
  <img src="/assets/img/gray.png" alt="12.07.2025 – Sony Research team visited to explore the collaboration potential">
  <img src="/assets/img/gray.png" alt="12.07.2025 – Sony Research team visited to explore the collaboration potential">
  <img src="/assets/img/gray.png" alt="12.07.2025 – Sony Research team visited to explore the collaboration potential">
</div>
<p>12.07.2025 – Sony Research team visited to explore the collaboration potential</p>

<div class="gallery">
  <img src="/assets/img/gray.png" alt="04.07.2025 – Dolby visited for collaboration on new tech project">
  <img src="/assets/img/gray.png" alt="04.07.2025 – Dolby visited for collaboration on new tech project">
</div>
<p>04.07.2025 – Dolby visited for collaboration on new tech project</p>

<h4>June</h4>
<div class="gallery">
  <img src="/assets/img/gray.png" alt="10.06.2025 – Earth Sciences Lonar Mission Project meeting">
  <img src="/assets/img/gray.png" alt="10.06.2025 – Earth Sciences Lonar Mission Project meeting">
  <img src="/assets/img/gray.png" alt="10.06.2025 – Earth Sciences Lonar Mission Project meeting">
</div>
<p>10.06.2025 – Earth Sciences Lonar Mission Project meeting</p>

<div class="gallery">
  <img src="/assets/img/gray.png" alt="02.06.2025 – Aerospace Engineering Mission Project meeting">
  <img src="/assets/img/gray.png" alt="02.06.2025 – Aerospace Engineering Mission Project meeting">
</div>
<p>02.06.2025 – Aerospace Engineering Mission Project meeting</p>

<!-- Lightbox -->
<div id="lightbox" onclick="closeLightbox(event)">
  <img id="lightbox-img" src="">
  <p id="lightbox-caption"></p>
  <div class="lightbox-nav">
    <span class="lightbox-btn" onclick="prevImage(event)">⟨ Prev</span>
    <span class="lightbox-btn" onclick="nextImage(event)">Next ⟩</span>
  </div>
</div>

<script>
let images = [];
let currentIndex = 0;

document.querySelectorAll('.gallery img').forEach((img, index) => {
  images.push({ src: img.src, caption: img.alt });
  img.addEventListener('click', () => {
    currentIndex = index;
    showImage();
  });
});

function showImage() {
  const image = images[currentIndex];
  document.getElementById('lightbox-img').src = image.src;
  document.getElementById('lightbox-caption').textContent = image.caption;
  document.getElementById('lightbox').style.display = 'flex';
}

function nextImage(e) {
  e.stopPropagation();
  currentIndex = (currentIndex + 1) % images.length;
  showImage();
}

function prevImage(e) {
  e.stopPropagation();
  currentIndex = (currentIndex - 1 + images.length) % images.length;
  showImage();
}

function closeLightbox(e) {
  // only close if clicking outside nav/buttons
  if (e.target.id === 'lightbox' || e.target === document.getElementById('lightbox-img')) {
    document.getElementById('lightbox').style.display = 'none';
  }
}
</script>
