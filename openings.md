---
title: Current Openings
permalink: /openings
layout: single
author_profile: false
classes: openings-index
---

<!-- Each opening is a single <a> card linking to its own detail page under /openings/.
     To add a new opening: copy one card block below, update the href, icon, title, and
     meta pills, then create the matching detail page in the openings/ directory. -->
<div class="openings-list">

  <a class="opening-card" href="/openings/3d-environment-artist">
    <div class="opening-icon">
      <svg viewBox="0 0 48 48" aria-hidden="true">
        <path d="M24 6 8 15v18l16 9 16-9V15z"></path>
        <path d="M8 15l16 9 16-9"></path>
        <path d="M24 24v18"></path>
      </svg>
    </div>
    <div class="opening-summary-text">
      <span class="opening-type-tag">Internship</span>
      <h2>3D Environment Artist (VR)</h2>
      <!-- Duration / compensation / location / apply-by, in that fixed order -->
      <div class="opening-meta">
        <span>Jan – Jun 2027</span>
        <span>Paid internship</span>
        <span>In-person</span>
        <span>Apply by Nov 10, 2026</span>
      </div>
    </div>
    <span class="opening-chevron" aria-hidden="true">&rarr;</span>
  </a>

  <a class="opening-card" href="/openings/vr-developer">
    <div class="opening-icon">
      <svg viewBox="0 0 48 48" aria-hidden="true">
        <rect x="7" y="17" width="34" height="16" rx="7"></rect>
        <circle cx="18" cy="25" r="3"></circle>
        <circle cx="30" cy="25" r="3"></circle>
        <path d="M22 25h4"></path>
      </svg>
    </div>
    <div class="opening-summary-text">
      <span class="opening-type-tag">Internship</span>
      <h2>VR Developer</h2>
      <div class="opening-meta">
        <span>Jan – Jun 2027</span>
        <span>Paid internship</span>
        <span>In-person</span>
        <span>Apply by Nov 10, 2026</span>
      </div>
    </div>
    <span class="opening-chevron" aria-hidden="true">&rarr;</span>
  </a>

</div>

<div class="openings-closing">
  <h3>Internship at IMXD Lab</h3>
  <p>Each year, we accept a select number of student interns based on the lab's ongoing projects. Prospective interns may reach out to us by email.</p>
  <p>One of the options to apply is through the <a href="https://www.ircc.iitb.ac.in/IRCC-Webpage/IITBInternship/" target="_blank">IIT Bombay Research Internship Awards</a> program. Interns get the opportunity to work with us during the Spring Semester (January to June). Applications for this program typically open around August to September.</p>
  <p>To know more about the formal application process for summer internship or semester-long internship at IIT Bombay, please check this link: <a href="https://acad.iitb.ac.in/admissions/internship#:~:text=Projects/%20Summer%20Training%20for%20External%20Students" target="_blank">Internship Programmes at IITB</a>.</p>
</div>

<!-- Shown regardless of whether any openings are listed above -->
<div class="openings-closing">
  <h3>No Suitable Opening?</h3>
  <p>Students and researchers interested in the lab's work are welcome to <a href="/contact">contact us directly</a>, even in the absence of a listed opening.</p>
</div>

<!-- Each opening is a single card linking to its own detail page under /openings/.
     To add a new opening: copy one card block below, make it a clickable <a class="opening-card">
     (drop opening-card--closed), update the href, icon, title, and meta pills, then create the
     matching detail page in the openings/ directory. -->
<h3 class="openings-past-title">Past Openings</h3>
<div class="openings-list">

  <details class="opening-card opening-card--closed">
    <summary>
      <div class="opening-icon">
        <svg viewBox="0 0 48 48" aria-hidden="true">
          <path d="M24 6 8 15v18l16 9 16-9V15z"></path>
          <path d="M8 15l16 9 16-9"></path>
          <path d="M24 24v18"></path>
        </svg>
      </div>
      <div class="opening-summary-text">
        <span class="opening-type-tag">IIT Bombay Research Internship Awards 2026-27</span>
        <h2>3D Environment Design and Assets Creation for Real-time Virtual Reality Experience</h2>
      </div>
    </summary>
    <!-- Stipend / duration / apply-by, in that fixed order -->
    <div class="opening-meta">
      <span>₹15,000/month</span>
      <span>Jan – Jun 2027</span>
      <span>Apply by Sep 29, 2026</span>
      <span class="opening-closed-tag">Applications closed</span>
    </div>
  </details>

  <details class="opening-card opening-card--closed">
    <summary>
      <div class="opening-icon">
        <svg viewBox="0 0 48 48" aria-hidden="true">
          <rect x="7" y="17" width="34" height="16" rx="7"></rect>
          <circle cx="18" cy="25" r="3"></circle>
          <circle cx="30" cy="25" r="3"></circle>
          <path d="M22 25h4"></path>
        </svg>
      </div>
      <div class="opening-summary-text">
        <span class="opening-type-tag">IIT Bombay Research Internship Awards 2026-27</span>
        <h2>Developing a Real-Time Virtual Reality 6DoF Narrative</h2>
      </div>
    </summary>
    <div class="opening-meta">
      <span>₹15,000/month</span>
      <span>Jan – Jun 2027</span>
      <span>Apply by Sep 29, 2026</span>
      <span class="opening-closed-tag">Applications closed</span>
    </div>
  </details>

</div>

<script>
(function () {
  // Animates each past-opening <details> open/closed by resizing the
  // element itself with the Web Animations API — a plain CSS transition
  // can't do this because the browser hides closed <details> content the
  // same frame it removes the `open` attribute, before any transition
  // could run.
  var reduceMotion = window.matchMedia && window.matchMedia("(prefers-reduced-motion: reduce)").matches;
  var items = Array.prototype.slice.call(document.querySelectorAll(".opening-card--closed"));

  items.forEach(function (details) {
    var summary = details.querySelector(":scope > summary");
    var meta = details.querySelector(":scope > .opening-meta");
    if (!summary) return;

    var currentAnimation = null;
    var currentMetaAnimation = null;

    function clearInlineStyles() {
      details.style.height = "";
      details.style.overflow = "";
    }

    function clearMetaStyles() {
      if (meta) meta.style.opacity = "";
    }

    summary.addEventListener("click", function (e) {
      if (reduceMotion) return;
      e.preventDefault();

      if (details.hasAttribute("open")) {
        var startHeight = details.offsetHeight;
        var endHeight = summary.offsetHeight;
        details.style.overflow = "hidden";
        if (currentAnimation) currentAnimation.cancel();
        currentAnimation = details.animate(
          { height: [startHeight + "px", endHeight + "px"] },
          { duration: 200, easing: "ease" }
        );
        currentAnimation.onfinish = function () {
          details.removeAttribute("open");
          clearInlineStyles();
          clearMetaStyles();
        };
        currentAnimation.oncancel = clearInlineStyles;

        // Fade the tags out in step with the collapse, instead of letting
        // them hang at full opacity and then pop away once the height
        // animation finishes clipping them.
        if (meta) {
          if (currentMetaAnimation) currentMetaAnimation.cancel();
          currentMetaAnimation = meta.animate(
            { opacity: [1, 0] },
            { duration: 120, easing: "ease", fill: "forwards" }
          );
        }
      } else {
        var startH = details.offsetHeight;
        details.setAttribute("open", "");
        var endH = details.offsetHeight;
        details.style.overflow = "hidden";
        details.style.height = startH + "px";
        if (currentAnimation) currentAnimation.cancel();
        currentAnimation = details.animate(
          { height: [startH + "px", endH + "px"] },
          { duration: 250, easing: "ease" }
        );
        currentAnimation.onfinish = clearInlineStyles;
        currentAnimation.oncancel = clearInlineStyles;

        // Fade the tags in only once the card has mostly opened, rather
        // than all at once — reads as content settling into place.
        if (meta) {
          meta.style.opacity = "0";
          if (currentMetaAnimation) currentMetaAnimation.cancel();
          currentMetaAnimation = meta.animate(
            { opacity: [0, 1] },
            { duration: 200, delay: 80, easing: "ease", fill: "forwards" }
          );
          currentMetaAnimation.onfinish = clearMetaStyles;
        }
      }
    });
  });
})();
</script>
