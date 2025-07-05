---
layout: page
title: News
permalink: /news
order: 10
---

### Latest

<ul id="latest-posts">
  {% assign sortedposts = site.posts | sort: "date" | reverse %}
  {% for post in sortedposts limit:10 %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a><br/>
      <small>{{ post.date | date: "%B %d, %Y" }}</small>
    </li>
  {% endfor %}
</ul>

### Search by Year

{% assign years = "" | split: "" %}

{% for post in site.posts %}
  {% assign year = post.date | date: "%Y" %}
  {% unless years contains year %}
    {% assign years = years | push: year %}
  {% endunless %}
{% endfor %}

{% assign years = years | sort | reverse %}

<p>
<select id="year-filter">
  <option value="">Select Year</option>
  {% for year in years %}
    <option value="{{ year }}">{{ year }}</option>
  {% endfor %}
</select>
</p>

<div id="year-posts">
  {% for year in years %}
    <div class="year-group" data-year="{{ year }}" style="display: none;">
      <h3>{{ year }}</h3>
      <ul>
        {% for post in site.posts %}
          {% assign postyear = post.date | date: "%Y" %}
          {% if postyear == year %}
            <li>
              <a href="{{ post.url }}">{{ post.title }}</a><br/>
              <small>{{ post.date | date: "%B %d, %Y" }}</small>
            </li>
          {% endif %}
        {% endfor %}
      </ul>
    </div>
  {% endfor %}
</div>

<script>
  const filter = document.getElementById('year-filter');
  const yearGroups = document.querySelectorAll('.year-group');

  filter.addEventListener('change', function () {
    yearGroups.forEach(group => {
      group.style.display = 'none';
    });
    if (this.value) {
      document.querySelector(`[data-year="${this.value}"]`).style.display = 'block';
    }
  });
</script>

