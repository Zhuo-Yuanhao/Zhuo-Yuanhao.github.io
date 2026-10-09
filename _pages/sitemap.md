---
layout: archive
title: "Sitemap"
permalink: /sitemap/
author_profile: true
---

{% include base_path %}

A list of the published pages and content on this site. An [XML version]({{ base_path }}/sitemap.xml) is also available for search engines.

<h2>Pages</h2>
{% for post in site.pages %}
  {% assign url_ending = post.url | slice: -1, 1 %}
  {% assign extension = post.url | split: '.' | last %}
  {% if post.sitemap != false %}
    {% if url_ending == '/' or extension == 'html' %}
      {% include archive-single.html %}
    {% endif %}
  {% endif %}
{% endfor %}

{% assign visible_posts = site.posts | where_exp: "post", "post.sitemap != false" %}
{% if visible_posts.size > 0 %}
<h2>Posts</h2>
{% for post in visible_posts %}
  {% include archive-single.html %}
{% endfor %}
{% endif %}

{% for collection in site.collections %}
  {% unless collection.output == false or collection.label == "posts" %}
    {% assign visible_docs = collection.docs | where_exp: "doc", "doc.sitemap != false" %}
    {% if visible_docs.size > 0 %}
<h2>{{ collection.label }}</h2>
      {% for post in visible_docs %}
        {% include archive-single.html %}
      {% endfor %}
    {% endif %}
  {% endunless %}
{% endfor %}
