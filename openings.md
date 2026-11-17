---
description: "Current Openings - IMXD Lab, IDC School of Design, IIT Bombay"
title: Current Openings
permalink: /openings
layout: single
author_profile: false
classes: openings-index
---

<!--
  ==========================================================================
  OPENINGS LIST
  ==========================================================================

  Every card on this page is built from the files in openings/ (each uses
  layout: opening). Nothing here is written by hand: to add, edit or close
  an opening, edit its file in openings/ (see openings/_HOW-TO.md).

    Current Openings = open: true, and the apply_by date hasn't passed
    Past Openings    = everything else

  The lines in curly-brace-percent tags below are Liquid. They run once
  when the site is built; visitors only see the HTML they produce.
-->


<!--
  Step 1: Sort the openings by deadline (earliest first, then by title).

  apply_by is written DD-MM-YYYY, which doesn't sort correctly as text, so:
    a. collect every opening page
    b. give each one a sortable key: "YYYYMMDD|title|url"
    c. sort the keys
    d. turn each key back into its page, using the url at the end
-->
{% assign opening_pages = site.pages | where: "layout", "opening" %}

{% assign opening_keys = "" | split: "" %}
{% for o in opening_pages %}
  {% capture k %}{{ o.facts.apply_by | date: "%Y%m%d" }}|{{ o.title }}|{{ o.url }}{% endcapture %}
  {% assign opening_keys = opening_keys | push: k %}
{% endfor %}

{% assign opening_keys = opening_keys | sort %}

{% assign all_openings = "" | split: "" %}
{% for k in opening_keys %}
  {% assign k_url = k | split: "|" | last %}
  {% assign o = opening_pages | where: "url", k_url | first %}
  {% assign all_openings = all_openings | push: o %}
{% endfor %}


<!--
  Step 2: Current Openings.

  opening-state.html sets opening_closed for each opening; the open ones get
  a link card. current_count decides whether the "no open positions" line
  below is shown.
-->
{% assign current_count = 0 %}
<div class="openings-list" id="openings-current">
{%- for o in all_openings -%}
  {%- include opening-state.html opening=o -%}
  {%- unless opening_closed -%}
    {%- assign current_count = current_count | plus: 1 %}
{% include opening-card.html opening=o %}
  {%- endunless -%}
{%- endfor %}
</div>

<p class="openings-none" id="openings-none"{% if current_count > 0 %} hidden{% endif %}>There are no open positions right now. Past openings are listed below.</p>


<!--
  ==========================================================================
  INFO BLOCKS (always shown)
  ==========================================================================
-->

<div class="openings-closing">
  <h3>Internship at IMXD Lab</h3>
  <p>Each year, we accept a select number of student interns based on the lab's ongoing projects. Prospective interns may reach out to us by email.</p>
  <p>One of the options to apply is through the <a href="https://www.ircc.iitb.ac.in/IRCC-Webpage/IITBInternship/" target="_blank">IIT Bombay Research Internship Awards</a> program. Interns get the opportunity to work with us during the Spring Semester (January to June). Applications for this program typically open in August and close by September.</p>
  <p>To know more about the formal application process for summer internship or semester-long internship at IIT Bombay, please check this link: <a href="https://acad.iitb.ac.in/admissions/internship" target="_blank">Internship Programmes at IITB</a>.</p>
</div>

<div class="openings-closing">
  <h3>No Suitable Opening?</h3>
  <p>Students and researchers interested in the lab's work are welcome to <a href="/contact">contact us directly</a>, even in the absence of a listed opening.</p>
</div>

<!--
  ==========================================================================
  PAST OPENINGS
  ==========================================================================

  Closed openings (open: false, or deadline passed), as collapsible cards.
  The whole section is hidden by the script below if there are none.
-->
<div id="openings-past">
<h3 class="openings-past-title">Past Openings</h3>
<div class="openings-list">
{%- for o in all_openings -%}
  {%- include opening-state.html opening=o -%}
  {%- if opening_closed %}
{% include opening-card.html opening=o closed=true %}
  {%- endif -%}
{%- endfor %}
</div>
</div>


<!--
  ==========================================================================
  SCRIPTS
  ==========================================================================
-->

<script>
// Moves current cards whose apply-by date has passed (end of day, IST) into
// Past Openings, so deadlines apply even if the site isn't rebuilt that day.
// Runs before the animation script below so moved cards animate too.
(function () {
  var current = document.getElementById("openings-current");
  var pastList = document.querySelector("#openings-past .openings-list");
  if (!current || !pastList) return;
  Array.prototype.forEach.call(current.querySelectorAll("a.opening-card[data-apply-by]"), function (card) {
    if (new Date() <= new Date(card.getAttribute("data-apply-by") + "T23:59:59+05:30")) return;
    var details = document.createElement("details");
    details.className = "opening-card opening-card--closed";
    var summary = document.createElement("summary");
    var text = card.querySelector(".opening-summary-text");
    var meta = text.querySelector(".opening-meta");
    var pill = document.createElement("span");
    pill.className = "opening-closed-tag";
    pill.textContent = "Applications closed";
    text.querySelector(".opening-type-tag").after(pill);
    summary.appendChild(card.querySelector(".opening-icon"));
    summary.appendChild(text);
    details.appendChild(summary);
    if (meta) details.appendChild(meta);
    pastList.insertBefore(details, pastList.firstChild);
    card.remove();
  });
  if (!current.querySelector(".opening-card")) document.getElementById("openings-none").hidden = false;
  if (!pastList.querySelector(".opening-card")) document.getElementById("openings-past").hidden = true;
})();
</script>

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
