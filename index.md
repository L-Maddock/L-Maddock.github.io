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
        <img src="/assets/figures/pic1_homelessfunding.png" alt="Counts and funding for homeless programs in the US, 2015 -- 2019 (HUD)">
        <div class="carousel-caption">
          <div class="carousel-title">Counts and Funding for Homeless Programs in the US, 2015 -- 2019 (HUD)</div>
          <div class="carousel-sub">Maddock &amp; Pena (2026) · Southern Economic Journal</div>
          <a class="carousel-link" href="https://doi.org/10.1002/soej.70031">View paper &rarr;</a>
        </div>
      </div>

      <!-- ===== FIGURE 2 ===== -->
      <div class="carousel-slide">
        <img src="/assets/figures/pic3_did.png" alt="Event-study estimates of source-of-income protections on rental market outcomes">
        <div class="carousel-caption">
          <div class="carousel-title">Source-of-income protections and rental market outcomes</div>
          <div class="carousel-sub">Working paper · Source of Income Protections</div>
          <a class="carousel-link" href="/assets/Maddock_JMP_Draft.pdf">View paper &rarr;</a>
        </div>
      </div>

      <!-- ===== FIGURE 3 ===== -->
      <div class="carousel-slide">
        <img src="/assets/figures/pic2_cleveland.png" alt="Cleveland plot of 2021 imputed homeless counts by place">
        <div class="carousel-caption">
          <div class="carousel-title">Imputed COVID-19 homeless counts by place</div>
          <div class="carousel-sub">Working paper · Counting the Uncounted</div>
          <a class="carousel-link" href="/assets/HomelessImputation_Paper.pdf">View paper &rarr;</a>
        </div>
      </div>

      <!-- ===== FIGURE 4 ===== -->
      <div class="carousel-slide">
        <img src="/assets/figures/shap_heat_nice.png" alt="SHAP values of common predictive features">
        <div class="carousel-caption">
          <div class="carousel-title">Predictive features of ecosystem service values</div>
          <div class="carousel-sub">Maddock, Nelson, Altringer, &amp; McKee (2026) · Ecosystem Services</div>
          <a class="carousel-link" href="https://doi.org/10.1016/j.ecoser.2026.101849">View paper &rarr;</a>
        </div>
      </div>

      <!-- ===== FIGURE 5 ===== -->
      <div class="carousel-slide">
        <img src="/assets/figures/pic7_soimap.png" alt="Map of source of income protection policies, 2013 -- 2018">
        <div class="carousel-caption">
          <div class="carousel-title">Map of source of income protection policies, 2013 -- 2018</div>
          <div class="carousel-sub">Working paper · Source of Income Protections</div>
          <a class="carousel-link" href="/assets/Maddock_JMP_Draft.pdf">View paper &rarr;</a>
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
