---
permalink: /lego/
title: ""
excerpt: ""
author_profile: true
---

<style>
  .lego-page {
    max-width: 100%;
  }

  .lego-hero {
    margin: 0.5rem 0 1.4rem;
    padding: 1.1rem 1.25rem;
    border: 1px solid #e6e8eb;
    border-radius: 18px;
    background: linear-gradient(135deg, #fffdf7 0%, #f7f9ff 100%);
    box-shadow: 0 8px 24px rgba(0, 0, 0, 0.04);
  }

  .lego-hero h1 {
    margin-top: 0;
    margin-bottom: 0.35rem;
  }

  .lego-hero p {
    margin-bottom: 0;
    color: #6f777d;
  }

  .lego-index {
    display: flex;
    gap: 0.55rem;
    overflow-x: auto;
    padding: 0.2rem 0 1rem;
    margin-bottom: 0.5rem;
    scroll-snap-type: x proximity;
    -webkit-overflow-scrolling: touch;
  }

  .lego-index a {
    flex: 0 0 auto;
    scroll-snap-align: start;
    text-decoration: none !important;
    border: 1px solid #d9dee4;
    color: #4b5560;
    background: #ffffff;
    border-radius: 999px;
    padding: 0.35rem 0.75rem;
    font-size: 0.82rem;
    white-space: nowrap;
  }

  .lego-index a:hover {
    border-color: #8a96a3;
    color: #2f3a45;
  }

  .lego-set {
    margin: 1.8rem 0 2.35rem;
  }

  .lego-set-head {
    display: flex;
    align-items: flex-end;
    justify-content: space-between;
    gap: 1rem;
    margin-bottom: 0.8rem;
    border-bottom: 1px solid #f0f1f2;
    padding-bottom: 0.45rem;
  }

  .lego-set-title h2 {
    margin: 0;
    font-size: 1.18rem;
  }

  .lego-subtitle {
    margin: 0.25rem 0 0;
    color: #8a9299;
    font-size: 0.82rem;
    line-height: 1.4;
  }

  .lego-count {
    color: #8a9299;
    font-size: 0.82rem;
    white-space: nowrap;
  }

  .lego-scroll {
    display: flex;
    gap: 1rem;
    overflow-x: auto;
    padding: 0.2rem 0.1rem 0.9rem;
    scroll-snap-type: x mandatory;
    -webkit-overflow-scrolling: touch;
  }

  .lego-card {
    position: relative;
    flex: 0 0 250px;
    height: 185px;
    display: block;
    border-radius: 16px;
    overflow: hidden;
    background: #f4f5f6;
    border: 1px solid #eceff2;
    box-shadow: 0 7px 18px rgba(0, 0, 0, 0.06);
    scroll-snap-align: start;
  }

  .lego-card:first-child {
    flex-basis: 330px;
    height: 220px;
  }

  .lego-card img {
    width: 100%;
    height: 100%;
    display: block;
    object-fit: cover;
    transition: transform 0.25s ease;
  }

  .lego-card:hover img {
    transform: scale(1.035);
  }

  .lego-card-label {
    position: absolute;
    left: 0.65rem;
    bottom: 0.65rem;
    padding: 0.18rem 0.48rem;
    border-radius: 999px;
    background: rgba(255, 255, 255, 0.86);
    color: #444b52;
    font-size: 0.72rem;
    font-weight: 600;
    line-height: 1.3;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.08);
  }

  .lego-set.is-featured {
    margin-top: 1.2rem;
  }

  .lego-set.is-featured .lego-set-head {
    margin-bottom: 0.9rem;
  }

  .lego-set.is-featured .lego-scroll {
    overflow-x: visible;
    padding-bottom: 0.3rem;
  }

  .lego-set.is-featured .lego-card,
  .lego-set.is-featured .lego-card:first-child {
    flex: 1 1 100%;
    width: 100%;
    height: auto;
    min-height: 0;
    border-radius: 20px;
  }

  .lego-set.is-featured .lego-card img {
    width: 100%;
    height: auto;
    max-height: 540px;
    object-fit: contain;
    background: #f4f5f6;
  }

  .lego-set.is-featured .lego-card-label {
    display: none;
  }

  .lego-scroll::-webkit-scrollbar,
  .lego-index::-webkit-scrollbar {
    height: 8px;
  }

  .lego-scroll::-webkit-scrollbar-thumb,
  .lego-index::-webkit-scrollbar-thumb {
    background: #d6dbe0;
    border-radius: 999px;
  }

  @media (max-width: 700px) {
    .lego-hero {
      padding: 1rem;
    }

    .lego-set-head {
      align-items: flex-start;
      flex-direction: column;
      gap: 0.25rem;
    }

    .lego-card,
    .lego-card:first-child {
      flex-basis: 74vw;
      height: 52vw;
      max-height: 260px;
    }

    .lego-set.is-featured .lego-card,
    .lego-set.is-featured .lego-card:first-child {
      flex-basis: 100%;
      max-height: none;
    }
  }
</style>

<div class="lego-page">
  <div class="lego-hero">
    <h1>🧱 LEGO! </h1>
    <p>I'm a LEGO fan for about 14 years, especially for LEGO® CREATORS(Icons) and Ideas. Here is part of my Lego gallery, grouped by series. Scroll sideways in each section to enjoy photos. To know more, welcome to contact with me!</p>
  </div>

  <div class="lego-index" aria-label="Lego collection index">
    {% for set in site.data.lego_sets %}
      <a href="#lego-{{ set.id }}" target="_self">{{ set.title }}</a>
    {% endfor %}
  </div>

  {% for set in site.data.lego_sets %}
    {% assign photo_count = set.images | size %}
    <section class="lego-set{% if set.featured %} is-featured{% endif %}" id="lego-{{ set.id }}">
      <div class="lego-set-head">
        <div class="lego-set-title">
          <h2>{{ set.title }}</h2>
          {% if set.subtitle %}<p class="lego-subtitle">{{ set.subtitle }}</p>{% endif %}
        </div>
        <span class="lego-count">{{ photo_count }} photo{% if photo_count != 1 %}s{% endif %}</span>
      </div>

      <div class="lego-scroll" aria-label="{{ set.title }} gallery">
        {% for image in set.images %}
          <a class="lego-card" href="{{ image.src }}" target="_blank" rel="noopener">
            <img src="{{ image.src }}" alt="{{ set.title }}{% if image.label %} {{ image.label }}{% endif %} photo {{ forloop.index }}" loading="lazy">
            {% unless set.featured %}
              {% if image.label %}<span class="lego-card-label">{{ image.label }}</span>{% endif %}
            {% endunless %}
          </a>
        {% endfor %}
      </div>
    </section>
  {% endfor %}
</div>
