---
layout: single-column-wide
title: Education
enable-banner: true
enable-header: true
permalink: "/education/"
page-sections:
- _page-sections/education.md
image: assets/img/istock-975086022.jpg

---
{% assign items = site.courses | sort: 'date-added' | reverse %}
{% for item in items %}
<div class="row head-spacing foot-spacing">
    

    {% if item.enable-image == true and item.image != empty and item.image != null and item.image != '' %}
    
    
    <div class="column small-12 medium-4 center">
        <img class="center-align"  src="{{site.baseurl}}/{{ item.image }}" width="200" />
    </div>
    <div class="column small-12 medium-8">
        <div class="show-for-medium">
            <h3 >{{ item.course-number }}</h3>
            <h2>{{ item.title }}</h2>
            <p>{{ item.title }}</h2>
        </div>
        <div class="show-for-small-only">
            <h3 class="center-align">{{ item.course-number }}</h3>
            <h2 class="center-align">{{ item.title }}</h2>
        </div>
        
        <p> <a href="{{ item.bulletin-link }}">Course Bulletin</a></p>
        {% assign instructors = item.instructors %}
        <p><strong>Instructor(s):</strong></p>
        {% for instructor in instructors %}
            <p class="instructor-name">{{ instructor }}</p>
        {% endfor %}
        <p><strong>Course Description:</strong> {{ item.description  }}</p>
        {% if item.enable-button-link == true %}
            <a href="{{ item.button-url }}">{{ item.button-text }}</a>
        {% endif%}
    </div>
    

    
    {% else %}

    <div class="column small-12 medium-12">
        <div class="show-for-medium">
            <h3 >{{ item.course-number }}</h3>
            <h2>{{ item.title }}</h2>
        </div>
        <div class="show-for-small-only">
            <h3 class="center-align">{{ item.course-number }}</h3>
            <h2 class="center-align">{{ item.title }}</h2>
        </div>
        
        <p> <a href="{{ item.bulletin-link }}">Course Bulletin</a></p>
        {% assign instructors = item.instructors %}
        <p><strong>Instructor(s):</strong></p>
        {% for instructor in instructors %}
            <p class="instructor-name">{{ instructor }}</p>
        {% endfor %}
        <p><strong>Course Description:</strong> {{ item.description  }}</p>
        {% if item.enable-button-link == true %}
            <a href="{{ item.button-url }}">{{ item.button-text }}</a>
        {% endif%}
    </div>

    {% endif %}


</div>
<hr>
{% endfor %}