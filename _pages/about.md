---
permalink: /
title: "Xiaoge Zhang"
layout: homepage
author_profile: false
redirect_from:
  - /about/
  - /about.html
---

{% include academic-homepage-style.html %}

<div class="xp-home">

<div class="xp-homepage-hero">
  <div class="xp-homepage-photo">
    <img src="{{ '/images/profile.jpg' | relative_url }}" alt="Xiaoge Zhang">
  </div>
  <div>
    <h1 class="xp-homepage-name">Xiaoge Zhang</h1>

    <p>I am currently a Ph.D. student in Computer Science at The University of Western Australia. Previously, I received my master's degree in 2022 from the Institute of Computing, Chinese Academy of Sciences. Before that, I received my bachelor's degree in 2019 from Wuhan University. Before starting my Ph.D., I worked as a Machine Learning Engineer at ByteDance.</p>

    <p>My research focuses on 3D computer vision, with particular interests in efficient neural representations for 3D scenes and objects. Recent topics in my work include 3D Gaussian Splatting compression, Neural Radiance Field compression, LiDAR and point cloud compression, and multi-view stereo.</p>

    <p>I am currently collaborating with <a href="https://ajmalsaeed.net/">Prof. Ajmal Mian</a>, <a href="https://saeed-anwar.github.io/">Dr. Saeed Anwar</a>, <a href="https://research-repository.uwa.edu.au/en/persons/mehwish-nasim/">Dr. Mehwish Nasim</a>, and <a href="https://scholar.google.com/citations?user=0JTE5YAAAAAJ&hl=en">A/Prof. Mingtao Feng</a>.</p>

    <div class="xp-homepage-links">
      <a href="mailto:{{ site.author.email }}">Email</a>
      {% if site.author.googlescholar %} / <a href="{{ site.author.googlescholar }}">Google Scholar</a>{% endif %}
      {% if site.author.github %} / <a href="https://github.com/{{ site.author.github }}">Github</a>{% endif %}
    </div>
  </div>
</div>

<h2 id="publications" class="xp-section-title">Publications</h2>

{% include publications-list.html %}

<h2 id="teaching" class="xp-section-title">Teaching</h2>

<ul class="xp-teaching-list">
  <li class="xp-teaching-item">
    <strong>Teaching Assistant</strong>, Semester 2, 2025<br>
    CITS4012 Natural Language Processing, The University of Western Australia
  </li>
  <li class="xp-teaching-item">
    <strong>Teaching Assistant</strong>, Semester 1, 2026<br>
    CITS4404 Artificial Intelligence and Adaptive Systems, The University of Western Australia
  </li>
</ul>

</div>
