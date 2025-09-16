---
layout: projectspage
title: "Lab Visits Archive"
permalink: /archive/
---

<link rel="stylesheet" href="{{ 'minimal-mistakes.css' | relative_url }}">

<div class="archive-container">
  {% assign groups = site.data.archive | sort: 'date' %}
  {% assign prev_month = nil %}
  {% assign global_index = 0 %}
  {% for group in groups %}
    {% assign this_month = group.date | date: "%Y-%m" %}

    {% if prev_month != this_month %}
      <!-- print month header only when month changes -->
      <h2 class="archive-month">{{ group.date | date: "%B %Y" }}</h2>
    {% endif %}

    <div class="archive-block" data-group-caption="{{ group.group_caption | escape }}">
      <!-- thumbnails grid -->
      <div class="archive-grid">
        {% for img in group.images %}
          {% assign raw_path = img.image %}
          {% if raw_path contains "http://" or raw_path contains "https://" %}
            {% assign final_src = raw_path %}
          {% else %}
            {% assign final_src = raw_path | relative_url %}
          {% endif %}

          {% assign global_index = global_index | plus: 1 %}
          <figure class="archive-thumb-figure">
            <button
              class="archive-thumb"
              data-image="{{ final_src }}"
              data-full-caption="{{ img.full_caption | escape }}"
              data-group-caption="{{ group.group_caption | escape }}"
              data-index="{{ global_index | minus: 1 }}"
              aria-label="Open image">
              <img src="{{ final_src }}" alt="{{ group.group_caption }}" data-src-debug="{{ final_src }}">
            </button>
          </figure>
        {% endfor %}
      </div>

      <!-- group caption line (date + caption) -->
      <p class="archive-group-line">
        {{ group.date | date: "%d.%m.%Y" }} - {{ group.group_caption }}
      </p>
    </div>

    {% assign prev_month = this_month %}
  {% endfor %}
</div>


<div id="archive-modal" class="archive-modal" aria-hidden="true" role="dialog" aria-modal="true" aria-label="Image viewer">
  <button id="archive-modal-close" class="archive-modal-close" aria-label="Close">✕</button>

  <div class="archive-modal-stage">
    <button id="archive-modal-prev" class="archive-modal-side archive-modal-prev" aria-label="Previous image">◀</button>

    <div class="archive-modal-mediawrap">
      <img id="archive-modal-img" src="" alt="" data-src-debug="">
      <div id="archive-modal-caption" class="archive-modal-caption" role="document"></div>
    </div>

    <button id="archive-modal-next" class="archive-modal-side archive-modal-next" aria-label="Next image">▶</button>
  </div>
</div>

{% raw %}
<script>
(function () {
  document.addEventListener('DOMContentLoaded', function () {
    console.log('[archive] modal script loaded');

    const modal = document.getElementById('archive-modal');
    const modalImg = document.getElementById('archive-modal-img');
    const modalCaption = document.getElementById('archive-modal-caption');
    const modalClose = document.getElementById('archive-modal-close');
    const modalPrev = document.getElementById('archive-modal-prev');
    const modalNext = document.getElementById('archive-modal-next');

    // collect thumbs; ensure they exist
    const thumbs = Array.from(document.querySelectorAll('.archive-thumb'));
    const total = thumbs.length;
    console.log('[archive] total thumbs =', total);

    // OPEN modal by index (clamped, no wrap)
    function openByIndex(idx) {
      if (total === 0) return;
      // clamp
      if (idx < 0) idx = 0;
      if (idx > total - 1) idx = total - 1;

      console.log('[archive] openByIndex', idx);

      const btn = thumbs[idx];
      if (!btn) return;
      const url = btn.getAttribute('data-image');
      let fullCaption = (btn.getAttribute('data-full-caption') || '').trim();
      const groupCaption = (btn.getAttribute('data-group-caption') || '').trim();
      const date = (btn.getAttribute('data-date') || '').trim();

      if (!fullCaption) fullCaption = groupCaption || '';

      // final caption "DATE - CAPTION"
      let finalCaption = '';
      if (date) {
        finalCaption = date + ' - ' + (fullCaption || '');
      } else {
        finalCaption = fullCaption || '';
      }

      modalImg.src = url;
      modalImg.alt = btn.querySelector('img')?.alt || '';
      modalImg.setAttribute('data-src-debug', url);
      modalCaption.textContent = finalCaption;

      modal.setAttribute('aria-hidden', 'false');
      document.body.classList.add('no-scroll');
      modal.dataset.currentIndex = idx;
      modalClose.focus();

      // set disabled state on arrows
      if (modalPrev) {
        const prevDisabled = idx === 0;
        modalPrev.disabled = prevDisabled;
        modalPrev.setAttribute('aria-disabled', prevDisabled ? 'true' : 'false');
      }
      if (modalNext) {
        const nextDisabled = idx === total - 1;
        modalNext.disabled = nextDisabled;
        modalNext.setAttribute('aria-disabled', nextDisabled ? 'true' : 'false');
      }
    }

    // navigate
    function gotoNext() {
      const cur = parseInt(modal.dataset.currentIndex || -1, 10);
      if (isNaN(cur)) return;
      if (cur >= total - 1) { console.log('[archive] at last, cannot next'); return; }
      openByIndex(cur + 1);
    }
    function gotoPrev() {
      const cur = parseInt(modal.dataset.currentIndex || -1, 10);
      if (isNaN(cur)) return;
      if (cur <= 0) { console.log('[archive] at first, cannot prev'); return; }
      openByIndex(cur - 1);
    }

    // attach click handlers to thumbs
    thumbs.forEach(btn => {
      btn.addEventListener('click', () => {
        const idx = parseInt(btn.getAttribute('data-index'), 10);
        console.log('[archive] thumb click index', idx);
        openByIndex(idx);
      });
    });

    // attach controls
    if (modalClose) modalClose.addEventListener('click', closeModal);
    if (modalPrev) modalPrev.addEventListener('click', gotoPrev);
    if (modalNext) modalNext.addEventListener('click', gotoNext);

    // close function
    function closeModal() {
      modal.setAttribute('aria-hidden', 'true');
      modalImg.src = '';
      modalCaption.textContent = '';
      document.body.classList.remove('no-scroll');
      delete modal.dataset.currentIndex;
      console.log('[archive] modal closed');
    }

    // click outside to close
    modal.addEventListener('click', (e) => { if (e.target === modal) closeModal(); });

    // key handling
    document.addEventListener('keydown', (e) => {
      if (modal.getAttribute('aria-hidden') === 'false') {
        if (e.key === 'Escape') { closeModal(); return; }
        if (e.key === 'ArrowRight') { e.preventDefault(); gotoNext(); return; }
        if (e.key === 'ArrowLeft')  { e.preventDefault(); gotoPrev(); return; }
      }
    });

    // preload near images when open (optional)
    function preload(url) { if (!url) return; const i = new Image(); i.src = url; }
    const observer = new MutationObserver(() => {
      if (modal.getAttribute('aria-hidden') === 'false') {
        const cur = parseInt(modal.dataset.currentIndex || -1, 10);
        if (!isNaN(cur)) {
          const nextBtn = thumbs[cur + 1];
          const prevBtn = thumbs[cur - 1];
          if (nextBtn) preload(nextBtn.getAttribute('data-image'));
          if (prevBtn) preload(prevBtn.getAttribute('data-image'));
        }
      }
    });
    observer.observe(modal, { attributes: true, attributeFilter: ['aria-hidden'], subtree: false });
  });
})();
</script>
{% endraw %}
