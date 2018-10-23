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
                                {% comment %}
                               {% if post.tags.size > 0 %}
  Tag{% if post.tags.size > 1 %}{% endif %}: <div class="cat-links">
                                    <ul>
                                        <li>
                                            <a href="{{ tagname }}">{{ post.tags | sort | join: ", " }}</a>
                                        </li>
                                    </ul>
                                </div>{% endif %}
                                {% endcomment %}
                    <div class="cat-links"><ul>
  {% for tag in post.tags %}
    {% capture tag_name %}{{ tag }}{% endcapture %}
    <li><a href="/tag/{{ tag_name | slugify: 'pretty' }}/">{{ post.tags | sort | join: ", " }}</a></li>
  {% endfor %}</ul>
</div>

                                <div class="entry-date published">{{ post.date | date_to_string }}</div>
                                <div class="clear"></div>
                            </div>
                        </div>
                    </article>

                    {% endfor %}
                    
                    <!--- paginatiom -->
                    {% if paginator.total_pages > 1 %}
<div class="pagination">
  {% if paginator.previous_page %}
    <a  class="ml-1 mr-1" href="{{ paginator.previous_page_path | prepend: site.baseurl | replace: '//', '/' }}">&laquo; Prev</a>
  {% else %}
    <span>&laquo; Prev</span>
  {% endif %}

  {% for page in (1..paginator.total_pages) %}
    {% if page == paginator.page %}
      <span class="ml-1 mr-1">{{ page }}</span>
    {% elsif page == 1 %}
      <a  class="ml-1 mr-1" href="{{ paginator.previous_page_path | prepend: site.baseurl | replace: '//', '/' }}">{{ page }}</a>
    {% else %}
      <a  class="ml-1 mr-1" href="{{ site.paginate_path | prepend: site.baseurl | replace: '//', '/' | replace: ':num', page }}">{{ page }}</a>
    {% endif %}
  {% endfor %}

  {% if paginator.next_page %}
    <a  class="ml-1 mr-1" href="{{ paginator.next_page_path | prepend: site.baseurl | replace: '//', '/' }}">Next &raquo;</a>
  {% else %}
    <span>Next &raquo;</span>
  {% endif %}
</div>
{% endif %}