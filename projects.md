---
title: "Projects"
author: Derek Gutheil
layout: archive
permalink: /projects/
---

<div class="tiles">
{% for post in site.posts %}
	{% include post-grid.html %}
{% endfor %}
</div><!-- /.tiles -->