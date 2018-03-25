---
layout: page
title: All Critch's Posts (2018-present)
image: /assets/images/cropped-andrew-critch-sand-cliff-jumping-header.jpg
permalink: /
---

<style>
h3.post-title {
  margin-bottom: 5px
}
.post-details {
  margin-bottom: 1em
}
</style>

I expect to be making any new blog posts here at [http://blog.acritch.com/](blog.acritch.com) for the foreseeable future.  For posts made between 2014 and 2018, visit [http://acritch.com/blog](acritch.com/blog).  For even older posts, made between 2010 and 2012 under the username “Academian”, visit [https://www.lesswrong.com/users/academian?view=frontpage](lesswrong.com).

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