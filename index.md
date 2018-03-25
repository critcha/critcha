---
layout: page
title: All posts
image: /assets/images/cropped-andrew-critch-sand-cliff-jumping-header.jpg
permalink: /
---

<style>
h3.post-title {
  margin-bottom: 5px
}
.post-details {
  margin-bottom: 10px
}
</style>

{% for post in site.posts %}
  <h3 class="post-title"><a href="{{ post.url }}">{{ post.title }}</a></h3>
  <div class="post-details"><span class="post-date">{{ post.date | date_to_long_string }}</span>{% if post.categories.size > 0 %} | <span class="post-categories">{{ post.categories }}</span>{% endif %}</div>
  {{ post.excerpt }}
  {% capture content_words %} 
    {{ post.content | number_of_words }} 
  {% endcapture %} 
  {% capture excerpt_words %} 
    {{ post.excerpt | number_of_words }} 
  {% endcapture %} 
  {% if excerpt_words != content_words %}
[Read more]({{ post.url }})
  {% endif %}
  <hr class="blog-separator" />
{% endfor %}