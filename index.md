---
layout: single
author_profile: true
title: "Home"
permalink: /
---
I'm an incoming Assistant Professor in the Department of Data Analytics at [Denison University](https://denison.edu). My research uses causal inference and machine learning to study housing and homelessness policy, environmental and wildlife policy, and sports analytics.

<div class="carousel" markdown="0">
  <div class="carousel-viewport">
    <div class="carousel-track">

      <!-- ===== FIGURE 1 ===== -->
      <div class="carousel-slide">
        <img src="/assets/figures/wetlands.png" alt="Map of wetland ecosystem service values across the U.S.">
        <div class="carousel-caption">
          <div class="carousel-title">Wetland ecosystem service values across the U.S.</div>
          <div class="carousel-sub">Maddock, Nelson, Altringer &amp; McKee (2026) · Ecosystem Services</div>
          <a class="carousel-link" href="https://doi.org/10.1016/j.ecoser.2026.101849">View paper &rarr;</a>
        </div>
      </div>

      <!-- ===== FIGURE 2 ===== -->
      <div class="carousel-slide">
        <img src="/assets/figures/soi-rents.png" alt="Event-study estimates of source-of-income protections on rents.">
        <div class="carousel-caption">
          <div class="carousel-title">Source-of-income protections and lower-tier rents</div>
          <div class="carousel-sub">Working paper · event-study estimates</div>
          <a class="carousel-link" href="/assets/Maddock_JMP_Draft.pdf">View paper &rarr;</a>
        </div>
      </div>

      <!-- ===== FIGURE 3 ===== -->
      <div class="carousel-slide">
        <img src="/assets/figures/grants-homelessness.png" alt="Sheltered versus unsheltered counts after federal grant awards.">
        <div class="carousel-caption">
          <div class="carousel-title">Federal grants and sheltered vs. unsheltered counts</div>
          <div class="carousel-sub">Maddock &amp; Pena (2026) · Southern Economic Journal</div>
          <a class="carousel-link" href="https://doi.org/10.1002/soej.70031">View paper &rarr;</a>
        </div>
      </div>

      <!-- ===== FIGURE 4 ===== -->
      <div class="carousel-slide">
        <img src="/assets/figures/affordability.png" alt="Housing affordability and homelessness across commuting zones.">
        <div class="carousel-caption">
          <div class="carousel-title">Housing affordability and homelessness</div>
          <div class="carousel-sub">Petach, Maddock &amp; Pena (2026) · Economic Development Quarterly</div>
          <a class="carousel-link" href="#">View paper &rarr;</a>
        </div>
      </div>

      <!-- ===== FIGURE 5 ===== -->
      <div class="carousel-slide">
        <img src="/assets/figures/referees.png" alt="Controversial referee decisions in Brazilian football leagues.">
        <div class="carousel-caption">
          <div class="carousel-title">Controversial referee decisions in Brazilian football</div>
          <div class="carousel-sub">Maddock &amp; Cicero · work in progress</div>
          <a class="carousel-link" href="#">Learn more &rarr;</a>
        </div>
      </div>

    </div>
  </div>
  <div class="carousel-controls">
    <button class="carousel-btn" id="carousel-prev" aria-label="Previous figure"><i class="fas fa-chevron-left"></i></button>
    <div class="carousel-dots" id="carousel-dots"></div>
    <button class="carousel-btn" id="carousel-next" aria-label="Next figure"><i class="fas fa-chevron-right"></i></button>
  </div>
</div>

<script>
(function () {
  var root = document.querySelector('.carousel');
  if (!root) return;
  var track  = root.querySelector('.carousel-track');
  var slides = root.querySelectorAll('.carousel-slide');
  var dotsWrap = root.querySelector('#carousel-dots');
  var n = slides.length, i = 0, timer = null;

  for (var d = 0; d < n; d++) {
    var b = document.createElement('button');
    b.className = 'carousel-dot';
    b.setAttribute('aria-label', 'Go to figure ' + (d + 1));
    (function (idx) { b.addEventListener('click', function () { go(idx); restart(); }); })(d);
    dotsWrap.appendChild(b);
  }
  var dots = dotsWrap.querySelectorAll('.carousel-dot');

  function go(k) {
    i = (k + n) % n;
    track.style.transform = 'translateX(' + (-i * 100) + '%)';
    for (var j = 0; j < dots.length; j++) dots[j].classList.toggle('is-active', j === i);
  }
  function play()    { timer = setInterval(function () { go(i + 1); }, 5000); }
  function restart() { if (timer) clearInterval(timer); play(); }

  root.querySelector('#carousel-prev').addEventListener('click', function () { go(i - 1); restart(); });
  root.querySelector('#carousel-next').addEventListener('click', function () { go(i + 1); restart(); });
  root.addEventListener('mouseenter', function () { if (timer) clearInterval(timer); });
  root.addEventListener('mouseleave', restart);

  go(0); play();
})();
</script>

Browse my [research](/research/), see what I'm [teaching](/teaching/), or view my [CV](/cv/). I also maintain the [Continuum of Care Mapper](https://qa38vl-lmad1997.shinyapps.io/coc-explorer/), an R Shiny app for visualizing CoC boundaries and homelessness statistics.

**Email:** [maddockl@denison.edu](mailto:maddockl@denison.edu)
