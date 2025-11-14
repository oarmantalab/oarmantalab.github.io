---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

{% if site.author.googlescholar %}
<div class="wordwrap">You can also find my articles on <a href="{{ site.author.googlescholar }}">my Google Scholar profile</a>.</div>
{% endif %}

{% include base_path %}

<!-- Publications by category if defined -->
{% if site.publication_category %}
  {% for category in site.publication_category %}
    {% assign title_shown = false %}
    {% for post in site.publications reversed %}
      {% if post.category != category[0] %}
        {% continue %}
      {% endif %}
      {% unless title_shown %}
        <h2>{{ category[1].title }}</h2>
        <hr />
        {% assign title_shown = true %}
      {% endunless %}

      <!-- Example single publication -->
      <div class="publication-item">
        <p>
          <strong><a href="{{ post.paperurl }}">{{ post.title }}</a></strong><br>
          {{ post.authors }}<br>
          <em>{{ post.venue }}</em>, {{ post.date | date: "%Y" }}
        </p>
      </div>

    {% endfor %}
  {% endfor %}
{% else %}
  {% for post in site.publications reversed %}
    <div class="publication-item">
      <p>
        <strong><a href="{{ post.paperurl }}">{{ post.title }}</a></strong><br>
        {{ post.authors }}<br>
        <em>{{ post.venue }}</em>, {{ post.date | date: "%Y" }}
      </p>
    </div>
  {% endfor %}
{% endif %}

<!-- Example publications if you want to hardcode some -->
<div class="publication-item">
  <p>
    <strong><a href="https://example.com/paper1.pdf">Modeling Human Mobility Patterns Using Machine Learning</a></strong><br>
    Omid Arman, John Doe<br>
    <em>Transportation Research Part C</em>, 2024
  </p>
</div>

<div class="publication-item">
  <p>
    <strong><a href="https://example.com/paper2.pdf">Spatial Econometrics of Electric Ve
