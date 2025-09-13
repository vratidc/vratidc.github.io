---
layout: projectspage
title: "Activities Archive"
permalink: archive
---

<style>
/* gallery */
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
  object-fit: cover;
  display: block;
  transition: transform .15s ease;
}
.gallery img:focus,
.gallery img:hover { transform: translateY(-4px); outline: none; }

/* lightbox */
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
  padding: 1.5rem;
  box-sizing: border-box;
}
#lightbox.open { display: flex; }
#lightbox .inner {
  max-width: 94%;
  width: 100%;
  max-height: 90vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0.75rem;
  animation: fadeIn .12s ease;
}
#lightbox img {
  max-width: 100%;
  max-height: 75vh;
  margin-bottom: 0;
  border-radius: 6px;
  box-shadow: 0 10px 30px rgba(0,0,0,0.6);
}
#lightbox p {
  color: white;
  font-size: 16px;
  text-align: center;
  margin: 0;
  line-height: 1.3;
  max-width: 90ch;
}

/* nav & buttons */
.lightbox-nav {
  display: flex;
  justify-content: space-between;
  width: 100%;
  max-width: 700px;
  margin-top: 10px;
}
.lightbox-btn {
  color: white;
  font-size: 16px;
  cursor: pointer;
  padding: 8px 14px;
  user-select: none;
  border-radius: 6px;
  border: 1px solid rgba(255,255,255,0.07);
  background: rgba(255,255,255,0.03);
}
.lightbox-btn:hover,
.lightbox-btn:focus { background: rgba(255,255,255,0.08); outline: none; }

/* responsive */
@media (max-width: 520px) {
  .gallery img { width: calc(50% - 12px); height: 140px; }
  .lightbox-nav { max-width: 95%; }
}

/* small animation */
@keyframes fadeIn {
  from { opacity: 0; transform: translateY(6px); }
  to { opacity: 1; transform: translateY(0); }
}
</style>

<h2>Lab Activities</h2>
<h3>2025</h3>

<h4>July</h4>
<div class="gallery">
  <!-- Example thumbnail; data-full is optional (if you have a full-size image separate from thumbnail) -->
  <img src="/assets/img/gray.png" alt="12.07.2025 – Sony Research team visited to explore the collaboration potential" data-full="/assets/images/photos/sony-2025-07-12.jpg" data-caption="12.07.2025 – Sony Research team visited to explore collaboration potential">
  <img src="/assets/img/gray.png" alt="12.07.2025 – Sony Research team visited to explore the collaboration potential" data-full="/assets/images/photos/sony-2025-07-12-2.jpg" data-caption="12.07.2025 – Sony Research team visit — group photo">
  <img src="/assets/img/gray.png" alt="12.07.2025 – Sony Research team visited to explore the collaboration potential" data-full="/assets/images/photos/sony-2025-07-12-3.jpg" data-caption="12.07.2025 – Sony Research — demo session">
</div>
<p>12.07.2025 – Sony Research team visited to explore the collaboration potential</p>

<div class="gallery">
  <img src="/assets/img/gray.png" alt="04.07.2025 – Dolby visited for collaboration on new tech project" data-full="/assets/images/photos/dolby-2025-07-04.jpg" data-caption="04.07.2025 – Dolby visit for collaboration on new tech project">
  <img src="/assets/img/gray.png" alt="04.07.2025 – Dolby visited for collaboration on new tech project" data-full="/assets/images/photos/dolby-2025-07-04-2.jpg" data-caption="04.07.2025 – Dolby presentation with faculty">
</div>
<p>04.07.2025 – Dolby visited for collaboration on new tech project</p>

<h4>June</h4>
<div class="gallery">
  <img src="/assets/img/gray.png" alt="10.06.2025 – Earth Sciences Lonar Mission Project meeting" data-full="/assets/images/photos/lonar-2025-06-10.jpg" data-caption="10.06.2025 – Earth Sciences: Lonar Mission Project meeting">
  <img src="/assets/img/gray.png" alt="10.06.2025 – Earth Sciences Lonar Mission Project meeting" data-full="/assets/images/photos/lonar-2025-06-10-2.jpg" data-caption="10.06.2025 – Visit and lab tour">
  <img src="/assets/img/gray.png" alt="10.06.2025 – Earth Sciences Lonar Mission Project meeting" data-full="/assets/images/photos/lonar-2025-06-10-3.jpg" data-caption="10.06.2025 – Discussion with students">
</div>
<p>10.06.2025 – Earth Sciences Lonar Mission Project meeting</p>

<div class="gallery">
  <img src="/assets/img/gray.png" alt="02.06.2025 – Aerospace Engineering Mission Project meeting" data-full="/assets/images/photos/aero-2025-06-02.jpg" data-caption="02.06.2025 – Aerospace Engineering project meeting">
  <img src="/assets/img/gray.png" alt="02.06.2025 – Aerospace Engineering Mission Project meeting" data-full="/assets/images/photos/aero-2025-06-02-2.jpg" data-caption="02.06.2025 – Project whiteboard session">
</div>
<p>02.06.2025 – Aerospace Engineering Mission Project meeting</p>

<!-- Lightbox -->
<div id="lightbox" role="dialog" aria-modal="true" aria-label="Photo viewer" onclick="handleLightboxClick(event)">
  <div class="inner" id="lightbox-inner" tabindex="-1">
    <img id="lightbox-img" src="" alt="">
    <p id="lightbox-caption"></p>
    <div class="lightbox-nav">
      <button class="lightbox-btn" id="lightbox-prev" onclick="prevImage(event)" aria-label="Previous image">⟨ Prev</button>
      <button class="lightbox-btn" id="lightbox-close" onclick="closeLightbox(event)" aria-label="Close viewer">Close</button>
      <button class="lightbox-btn" id="lightbox-next" onclick="nextImage(event)" aria-label="Next image">Next ⟩</button>
    </div>
  </div>
</div>

<script>
/* improved lightbox script (supports data-full, keyboard, prevents scrolling) */

let images = [];            // {thumb, full, caption}
let currentIndex = 0;

function buildImageList() {
  images = [];
  const imgs = Array.from(document.querySelectorAll('.gallery img'));
  imgs.forEach((img, index) => {
    const thumb = img.src;
    const full = img.dataset.full || img.src;
    const caption = img.dataset.caption || img.alt || '';
    images.push({ thumb, full, caption, el: img });
    // attach handler (capture index at time of creation)
    img.setAttribute('data-index', index);
    img.addEventListener('click', () => {
      currentIndex = Number(img.getAttribute('data-index'));
      openLightbox();
    });
    // keyboard accessibility: allow Enter/Space to open
    img.setAttribute('tabindex', '0');
    img.addEventListener('keydown', (e) => {
      if (e.key === 'Enter' || e.key === ' ') {
        e.preventDefault();
        currentIndex = Number(img.getAttribute('data-index'));
        openLightbox();
      }
    });
  });
}

/* show/hide lightbox and update content */
function openLightbox() {
  updateLightbox();
  const lb = document.getElementById('lightbox');
  lb.classList.add('open');
  lb.style.display = 'flex';
  document.body.style.overflow = 'hidden'; // prevent background scroll
  // focus inner for keyboard capture
  document.getElementById('lightbox-inner').focus();
}

function closeLightbox(e) {
  if (e) e.stopPropagation();
  const lb = document.getElementById('lightbox');
  lb.classList.remove('open');
  lb.style.display = 'none';
  document.body.style.overflow = '';
}

function updateLightbox() {
  const image = images[currentIndex];
  if (!image) return;
  const imgEl = document.getElementById('lightbox-img');
  imgEl.src = image.full;
  imgEl.alt = image.caption || '';
  document.getElementById('lightbox-caption').textContent = image.caption || '';
}

/* navigation (keyboard-safe) */
function nextImage(e) {
  if (e) e.stopPropagation();
  if (images.length === 0) return;
  currentIndex = (currentIndex + 1) % images.length;
  updateLightbox();
}
function prevImage(e) {
  if (e) e.stopPropagation();
  if (images.length === 0) return;
  currentIndex = (currentIndex - 1 + images.length) % images.length;
  updateLightbox();
}

/* click outside inner closes lightbox */
function handleLightboxClick(e) {
  if (e.target.id === 'lightbox') closeLightbox();
}

/* keyboard navigation */
document.addEventListener('keydown', (e) => {
  const lb = document.getElementById('lightbox');
  const isOpen = lb && lb.classList.contains('open');
  if (!isOpen) return;
  if (e.key === 'Escape') closeLightbox();
  else if (e.key === 'ArrowRight') nextImage();
  else if (e.key === 'ArrowLeft') prevImage();
});

/* init */
document.addEventListener('DOMContentLoaded', () => {
  buildImageList();
});
</script>
