---
layout: archive
#title: "Publications"
permalink: /publications/
author_profile: true
---


{% include base_path %}

<h1><u>Conference</u></h1>

{% for post in site.publications reversed %}
  {% include archive-single.html %}
{% endfor %}

<h1><u>Journal</u></h1>

{% for post in site.journal reversed %}
  {% include archive-single.html %}
{% endfor %}
