---
layout: page
title: Dive Logs
permalink: /dive-logs/
---

<div id="site">
    <div class="home-postex" id="postex">
      <div class="dive-map">
        {% google_map src="_diveLogs" width="100%" height="300" %}
      </div>

      <ul class="animated fadeInUp list-none" id="post-grid">
        {% assign years = site.diveLogs | group_by_exp:"diveLog", "diveLog.date | date: '%Y'" %}
        {% for year in years %}
            <h3>{{ year.name }}</h3>
            <ul>
              {% assign diveLogs = year.items | sort: "diveNumber" %}
              {% for diveLog in diveLogs %}
                <li><a href="{{ diveLog.url | relative_url }}" title="{{ diveLog.location.name | escape }}">
                #{{ diveLog.diveNumber }}
                - {{ diveLog.date | date: '%B %-d' }}{{ diveLog.date | date: '%d' | ordinal }}
                - {{ diveLog.location.name | escape }}</a></li>
              {%endfor%}
            </ul>
        {%endfor%}
      </ul>
  </div>
</div>
