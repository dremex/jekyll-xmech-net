---
layout: page
title: Posts
permalink: /posts/
pagination: 
  enabled: true
---

<div id="site">
    <div class="home-postex" id="postex">

      <ul class="animated fadeInUp list-none" id="post-grid">

          {% for post in paginator.posts %}
             <li>
                  <header class="entry-title">
                      <a href="{{ post.url | relative_url }}" title="{{ post.title | escape }}">
                        <div class="content">
                            <h2>{{ post.title | escape }}</h2>
                            <p class="post-date">{{ post.date | date: "%A %B %e, %Y" }}</p>
                            <p class="oneliner">{{ post.excerpt }}</p>
                        </div>
                      </a>
                  </header>
              </li>
          {% endfor %}

      </ul>
  </div>

<div class="animated fadeInUp pagerContainer">
  <ul class="pagination">
    {% if paginator.previous_page %}
      <li class="previous" rel="noindex, follow">
          <a href="{{ paginator.previous_page_path | prepend: site.baseurl | replace: '//', '/' }}">&larr; Newer Posts</a>
      </li>
      {% endif %}
      {% if paginator.next_page %}
      <li class="next">
          <a href="{{ paginator.next_page_path | prepend: site.baseurl | replace: '//', '/' }}">Older Posts &rarr;</a>
      </li>
      {% endif %}
    </ul>
</div>