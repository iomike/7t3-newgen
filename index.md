---
title: Home
banner_image: "/img/banner.png"
layout: landing-page
heading: Belkirk College
menu:
  navigation:
    identifier: _index
    weight: 1
---
{% comment %}
	This layout is used to by posts.md to display all of documents in
	the _posts/ collection
{% endcomment %}

{% for post in site.posts %}
<div class="container pure-g">
  <div class="pure-u-1">
      <div class="content content-narrow">
        <div class="list-layout">
          <h2><a href="{{ post.remote_url }}">{{ post.title }}</a></h2>
          <small>{{ post.remote_url }}</small>
          <date>{{ post.date | date_to_string }}</date>
        </div>
      </div>
    </div>
  </div>
</div>
{% endfor %}
