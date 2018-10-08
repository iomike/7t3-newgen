---
title: Home
layout: default
---
{% comment %}
	This layout is used to by posts.md to display all of documents in
	the _posts/ collection
{% endcomment %}

{% for post in site.posts %}
<div class="list-group">
  <a href="{{ post.remote_url }}" class="list-group-item list-group-item-action flex-column align-items-start">
    <div class="d-flex w-100 justify-content-between">
      <h5 class="mb-1">{{ post.title }}</h5>
      <small class="text-muted">{{ post.date | date_to_string }}</small>
    </div>
    <p class="mb-1">{{ post.remote_url }}</p>
{% if post.tags.size > 0 %}
  Tag{% if post.tags.size > 1 %}s{% endif %}:
  <small class="text-muted">{{ post.tags | sort | join: ", " }}</small>
{% endif %}
  </a>
</div>
{% endfor %}
