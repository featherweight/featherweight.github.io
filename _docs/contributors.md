---
layout: docs
title: Contributors
permalink: /contributors/
authors:
  - Jack R. Dunaway
editors:
  - placeholder
---

The following individuals have contributed to Featherweight (order randomized on reload):

Jack R. Dunaway <jack@wirebirdlabs.com>

{{ page }}

{% for author in site.github.contributors %}
  * [{{ author.login }}]({{ author.url }})
{% endfor %}

{{ site.github }}


<ul>
{% for contributor in site.github.contributors %}
  <li>
    <img src="{{ contributor.avatar_url }}" width="32" height="32" /> {{ contributor.login }}
  </li>
{% endfor %}
</ul>