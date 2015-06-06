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

{% for author in site.github.contributors %}
  * [{{ author.login }}]({{ author.url }})
{% endfor %}