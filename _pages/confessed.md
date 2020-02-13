---
layout: default
permalink: /confessed/
---

<div class="container">
  <section class="siteheader" data-aos="fade-up" data-aos-easing="ease-out-quad" data-aos-duration="700">
    <div class="siteheader__inner">
      <h1 class="siteheader__title"><a href="{{ site.url }}" title="Home">{{ site.siteheader.title }}</a></h1>
      <p class="siteheader__slogan">{{ site.siteheader.slogan }}</p>
      <div class="confessed__submitted">
        <p>Your confession has been submitted and queued to be published within 24 hours.</p>
      </div>     
    </div>
  </section>
</div>

<div class="container">
  {% if site.posts.size > 0 %}
    {% for post in site.posts %}
    <div class="confession" data-aos="fade-up" data-aos-easing="ease-out-quad" data-aos-duration="800">
      {% if post.image %}
      <div class="confession__image-box">
        <a href="{{post.url | prepend: site.baseurl}}" class="confession__image" style="background-image: url({{site.baseurl}}{{post.image}})"></a>
      </div>
      {% endif %}
      <div class="confession__content">
        <div class="confession__meta">
          <span class="confession__date"><time datetime="{{ post.date | date_to_xmlschema }}">{% assign date_format = site.minima.date_format | default: "%B %-d, %Y" %}{{ post.date | date: date_format }}</time></span>
        </div>
        <h2 class="confession__title">{{post.title}}</h2>
      </div>
    </div>
    {% endfor %}
  {% endif %}
</div>
