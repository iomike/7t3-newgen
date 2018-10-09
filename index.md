---
title: Home
layout: default
---
{% comment %}
	This layout is used to by posts.md to display all of documents in
	the _posts/ collection
{% endcomment %}

{% for post in site.posts %}
<article id="{{ post.url | strip_html | replace:'/','' }}" class="blog-item-holder">
                        <div class="entry-content relative">
                            <div class="content-1170 center-relative">
                                <h2 class="entry-title">
                                    <a href="{{ post.remote_url }}" target="_blank">{{ post.title }}</a>
                                </h2>
                               {% if post.tags.size > 0 %}
  Tag{% if post.tags.size > 1 %}s{% endif %}: <div class="cat-links">
                                    <ul>
                                        <li>
                                            <a href="{{ post.tag.url | pretty }}">{{ post.tags | sort | join: ", " }}</a>
                                        </li>
                                    </ul>
                                    {% endif %}
                                </div>
                                <div class="entry-date published">{{ post.date | date_to_string }}</div>
                                <div class="clear"></div>
                            </div>
                        </div>
                    </article>
                    {% endfor %}