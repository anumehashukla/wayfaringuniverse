---
title: Confused where to head next?
subtitle:
description:
featured_image: /images/about.jpg
---

<section class="where-to-go">
  <h1 class="text-center">Confused where to head next?</h1>
  <!--<div class="dropdown text-center hide">
    <select data-placeholder="Choose when you want to travel">
      {% comment %}{% for value in site.data.settings.when_to_travel %}
      <option value="{{value[0]}}">
        {{value[1].text}}
      </option>
      {% endfor %}
      {% endcomment %}
    </select>
  </div>-->

    <section class="accordion">
      {% for month in site.data.settings.when_to_travel %}

        {% capture month_name %}{{month[0]}}{% endcapture %}

        <button class="snackbar">{{month_name}}</button>
        <div class="panel">
          {% for subsub in month[1].headings %}
            <h4>{{subsub.title}}</h4>
            {% for place in subsub.places %}
              <p>{{place}}</p>
            {% endfor %}
          {% endfor %}
        </div>
      {% endfor %}
    </section>

{% comment %}
  <section class="where-to-go-places" style="display:none;">
    <div>
      {% for value in site.data.settings.when_to_travel %}
      <div class="where-to-go-place {{value[0]}}" style="display: none;">
        Places you can travel in {{value[1].text}}
        <div class="places">
          {% for place in value[1].places %}
          <div>{{place}}</div>
          {% endfor %}
        </div>
      </div>
      {% endfor %}
    </div>
  </section>
  {% endcomment %}
</section>