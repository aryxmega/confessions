---
layout: default
permalink: /confessed/
---

<div class="container">
  <section class="author" data-aos="fade-up" data-aos-easing="ease-out-quad" data-aos-duration="700">
    <div class="author__inner">
      <h1 class="author__job">{{ site.author.job }}</h1>
      <p class="author__bio">{{ site.author.bio }}</p>
      <div class="confessed__submitted">
        <p>Your confession has been submitted to be randomly chosen. New confession posted daily. Keep an eye out for yours.</p>
      </div>     
    </div>
  </section>
</div>

<div class="container">
  {% if site.posts.size > 0 %}
    {% for post in site.posts %}
    <div class="article" data-aos="fade-up" data-aos-easing="ease-out-quad" data-aos-duration="800">
      {% if post.image %}
      <div class="article__image-box">
        <a href="{{post.url | prepend: site.baseurl}}" class="article__image" style="background-image: url({{site.baseurl}}{{post.image}})"></a>
      </div>
      {% endif %}
      <div class="article__content">
        <div class="article__meta">
          <span class="article__date"><time datetime="{{ post.date | date_to_xmlschema }}">{% assign date_format = site.minima.date_format | default: "%B %-d, %Y" %}{{ post.date | date: date_format }}</time></span>
        </div>
        <h2 class="article__title">{{post.title}}</h2>
      </div>
    </div>
    {% endfor %}
  {% endif %}
</div>
