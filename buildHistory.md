---
layout: default
title: Build History
permalink: /builds/
---

<div class="home">

    {%- if site.posts.size > 0 -%}
        <h2 class="post-list-heading">Build history</h2>
        <ul class="post-list">
            {% assign builds = site.posts | where: "layout", "build" %}
            {%- for post in builds -%}
                <li>
                    <a class="post-link" href="{{ post.url | relative_url }}">
                        {{ post.title | escape }}
                    </a>
                    
                    {%- if post.summary -%}
						{% assign summaryParts = post.summary | split: "<br>" %}
                        {{ summaryParts.first }}
                        <br>
                    {%- endif -%}

                    {%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%}
                    <span class="post-meta">{{ post.date | date: date_format }}</span>


                </li>
            {%- endfor -%}
        </ul>
    {%- endif -%}

</div>