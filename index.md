---
title: Home
layout: landing-page
---
{% comment %}
	This layout is used to by posts.md to display all of documents in
	the _posts/ collection
{% endcomment %}

{% for post in site.posts %}

      <div class="content content-narrow">
        <div class="list-layout">
          <h2><a href="{{ post.remote_url }}">{{ post.title }}</a></h2>
          <h4>{{ post.remote_url }}</h4>
          <date>{{ post.date | date_to_string }}</date>
        </div>
      </div>

{% endfor %}
