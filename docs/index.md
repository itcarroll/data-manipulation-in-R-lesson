---
layout: default
style: /css/lesson.css
---

# {{ site.title }}
{:style="text-transform: none;"}

> Handouts for this lesson need to be saved on your computer. [Download]({{ site.github.releases_url }}/download/{{ site.tag }}/handouts.zip) and unzip this material into the directory (a.k.a. folder) where you plan to work.

## Contents

{% for sorted in site.slide_sorter %}{% capture id %}/slides/{{ sorted }}{% endcapture %}{% assign hslide = site.slides | where: "id", id | first %}
- [{{ hslide.excerpt | strip_html | strip }}](#{{ id }}){% endfor %}

---

{% for sorted in site.slide_sorter %}{% capture id %}/slides/{{ sorted }}{% endcapture %}{% assign hslide = site.slides | where: "id", id | first %}
<a name="{{ id }}"></a>
{% assign vslides = hslide.content | split: "===" %}
{% for vslide in vslides %}
{{ vslide }}
{% endfor %}
[Top of Section](#{{ id }})
{:.ToS}
  
---
{% endfor %}
