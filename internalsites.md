---
title: Internal Sites
permalink: /sites
layout: single
collection: activities
entries_layout: grid
---

<div class="accent-line"></div>
<p class="intro-desc">Quick access to tools and resources for our team.</p>

<section class="sites-grid" aria-label="Internal sites">

  <a class="site-card" href="https://equipment.imxd.in/" target="_blank" rel="noopener">
    <div class="icon-circle">
      <svg viewBox="0 0 48 48" aria-hidden="true">
        <rect x="11" y="10" width="26" height="20" rx="2"></rect>
        <path d="M8 34h32"></path>
        <path d="M17 34l2-3h10l2 3"></path>
      </svg>
    </div>
    <h2>Equipment Portal</h2>
    <p>Request &amp; track lab equipment</p>
    <div class="card-action">
      <span class="open-link">Open <span>&rarr;</span></span>
    </div>
  </a>

  <a class="site-card" href="https://cloud.imxd.in/" target="_blank" rel="noopener">
    <div class="icon-circle">
      <svg viewBox="0 0 48 48" aria-hidden="true">
        <path d="M14 35h21a8 8 0 0 0 1-15.9A11 11 0 0 0 15.3 17 7.5 7.5 0 0 0 14 35z"></path>
      </svg>
    </div>
    <h2>Cloud Storage</h2>
    <p>Shared files &amp; team drives</p>
    <div class="card-action">
      <span class="open-link">Open <span>&rarr;</span></span>
    </div>
  </a>

  <a class="site-card" href="https://cloud.imxd.in/index.php/apps/assetstore/" target="_blank" rel="noopener">
    <div class="icon-circle">
      <svg viewBox="0 0 48 48" aria-hidden="true">
        <path d="M24 6 8 15v18l16 9 16-9V15z"></path>
        <path d="M8 15l16 9 16-9"></path>
        <path d="M24 24v18"></path>
      </svg>
    </div>
    <h2>Asset Store</h2>
    <p>Browse &amp; download lab assets and projects</p>
    <div class="card-action">
      <span class="open-link">Open <span>&rarr;</span></span>
    </div>
  </a>

  <a class="site-card" href="https://license.imxd.in/" target="_blank" rel="noopener">
    <div class="icon-circle">
      <svg viewBox="0 0 48 48" aria-hidden="true">
        <circle cx="17" cy="24" r="8"></circle>
        <path d="M25 24h16"></path>
        <path d="M35 24v7"></path>
        <path d="M41 24v5"></path>
      </svg>
    </div>
    <h2>License Portal</h2>
    <p>Access control for IMXD Lab projects</p>
    <div class="card-action">
      <span class="open-link">Open <span>&rarr;</span></span>
    </div>
  </a>

  <div class="site-card disabled">
    <div class="icon-circle">
      <svg viewBox="0 0 48 48" aria-hidden="true">
        <rect x="7" y="17" width="34" height="16" rx="7"></rect>
        <circle cx="18" cy="25" r="3"></circle>
        <circle cx="30" cy="25" r="3"></circle>
        <path d="M22 25h4"></path>
      </svg>
    </div>
    <h2>Quest Monitoring</h2>
    <p>Live tracking dashboard for Meta Quest headsets</p>
    <div class="card-action">
      <span class="coming-soon">Available soon</span>
    </div>
  </div>

</section>

<style>
:root {
  --imxd-green: #087f5b;
  --imxd-green-soft: #e9f4f0;
  --imxd-muted: #70757a;
  --imxd-border: #e5e7e9;
}

#page-title {
  font-size: 32px;
  line-height: 1.15;
  font-weight: 600;
  letter-spacing: -1px;
  margin-bottom: 0 !important;
}

.accent-line {
  width: 67px;
  height: 3px;
  background: var(--imxd-green);
  margin-top: 20px;
  margin-bottom: 20px;
}

.intro-desc {
  margin: 0 0 48px;
  color: var(--imxd-muted);
  font-size: 23px;
  line-height: 1.45;
  font-weight: 400;
  max-width: 620px;
}

.sites-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 47px 24px;
}

/* !important + explicit :visited/:active states are required — the theme's own
   a:visited rule is more specific than a plain .site-card rule and will otherwise
   underline/recolor a previously-clicked card. */
.site-card,
.site-card:visited,
.site-card:hover,
.site-card:active,
.site-card * {
  text-decoration: none !important;
  color: inherit !important;
}

.site-card {
  border: 1px solid var(--imxd-border);
  border-radius: 17px;
  background: #fff;
  padding: 24px 20px 20px;
  display: grid;
  grid-template-columns: 44px 1fr;
  grid-template-rows: auto auto auto;
  column-gap: 10px;
  box-shadow: 0 7px 20px rgba(0, 0, 0, 0.025);
  transition: transform 0.18s ease, box-shadow 0.18s ease, border-color 0.18s ease;
}

.site-card:not(.disabled):hover {
  transform: translateY(-3px);
  border-color: #d8dfdc;
  box-shadow: 0 12px 28px rgba(0, 0, 0, 0.06);
  text-decoration: none;
}

.icon-circle {
  width: 44px;
  height: 44px;
  border-radius: 50%;
  background: var(--imxd-green-soft);
  color: var(--imxd-green);
  display: flex;
  align-items: center;
  justify-content: center;
  grid-column: 1;
  grid-row: 1 / span 3;
  align-self: start;
}

.icon-circle svg {
  width: 22px;
  height: 22px;
  stroke: currentColor;
  fill: none;
  stroke-width: 2.2;
  stroke-linecap: round;
  stroke-linejoin: round;
}

.site-card.disabled .icon-circle {
  background: #f0f0f0;
  color: #a3a3a3;
}

.site-card h2 {
  margin: 0;
  font-size: 17px;
  line-height: 1.2;
  font-weight: 600;
  letter-spacing: -0.4px;
  grid-column: 2;
  grid-row: 1;
}

.site-card p {
  margin: 8px 0 0;
  color: var(--imxd-muted);
  font-size: 14px;
  line-height: 1.45;
  max-width: 270px;
  grid-column: 2;
  grid-row: 2;
}

.card-action {
  padding-top: 12px;
  grid-column: 2;
  grid-row: 3;
}

.open-link {
  color: var(--imxd-green);
  text-decoration: none;
  font-size: 15px;
  font-weight: 600;
  display: inline-flex;
  align-items: center;
  gap: 10px;
}

.open-link span {
  font-size: 13px;
  line-height: 1;
  font-weight: 400;
  transform: translateY(-1px);
  transition: transform 0.18s ease;
  display: inline-block;
}

.site-card:hover .open-link span {
  transform: translate(4px, -1px);
}

.site-card:focus-visible {
  outline: 2px solid var(--imxd-green);
  outline-offset: 3px;
}

.coming-soon {
  display: inline-block;
  color: #8d8d8d;
  background: #f0f0f0;
  border-radius: 20px;
  padding: 8px 17px;
  font-size: 14px;
  line-height: 1;
}

@media (max-width: 1050px) {
  .sites-grid {
    grid-template-columns: repeat(2, 1fr);
    gap: 30px;
  }
}

@media (max-width: 700px) {
  #page-title {
    font-size: 8px;
  }
  .accent-line {
    margin-top: 22px;
  }
  .intro-desc {
    margin-top: 18px;
    font-size: 4px;
  }
  .sites-grid {
    grid-template-columns: 1fr;
    gap: 20px;
  }
  .site-card {
    padding: 30px 24px 26px;
    grid-template-columns: 45px 1fr;
    column-gap: 24px;
  }
  .icon-circle {
    width: 22px;
    height: 22px;
  }
  .icon-circle svg {
    width: 11px;
    height: 11px;
  }
  .site-card h2 {
    margin-top: 8px;
    font-size: 6px;
  }
  .site-card p {
    font-size: 4px;
    margin-top: 13px;
  }
  .open-link {
    font-size: 5px;
  }
}
</style>
