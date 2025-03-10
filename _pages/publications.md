
---


permalink: /
title: "Publications"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

{% if site.author.googlescholar %}
  <div class="wordwrap">You can also find my articles on <a href="{{site.author.googlescholar}}">my Google Scholar profile</a>.</div>
{% endif %}


I am Yin Huang, I am currently pursuing my Master's degree in Intelligent Systems Engineering at Southwest Jiaotong University (2022.9-2025.6), where I serve as a research fellow in the National Engineering Laboratory of Integrated Transportation Big Data Application Technology. My academic trajectory focuses on developing novel AI architectures for spatiotemporal pattern discovery, particularly in urban mobility systems.

I am seeking research assistant positions (2025-2026) followed by PhD opportunities (Spring/Fall 2026 intake) to advance these directions. Specifically interested in: • Cross-modal spatiotemporal representation learning • Physics-informed neural operators for urban systems • Decentralized learning architectures for IoT sensor networks


{% include base_path %}

<!-- New style rendering if publication categories are defined -->
{% if site.publication_category %}
  {% for category in site.publication_category  %}
    {% assign title_shown = false %}
    {% for post in site.publications reversed %}
      {% if post.category != category[0] %}
        {% continue %}
      {% endif %}
      {% unless title_shown %}
        <h2>{{ category[1].title }}</h2><hr />
        {% assign title_shown = true %}
      {% endunless %}
      {% include archive-single.html %}
    {% endfor %}
  {% endfor %}
{% else %}
  {% for post in site.publications reversed %}
    {% include archive-single.html %}
  {% endfor %}
{% endif %}
