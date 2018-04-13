---
  layout: code_for_new_orleans
  title: Current Projects
  menu_tag: Projects
  category: main_nav
---
Check out our current projects!

<nav>
  <ul>
    {% for page_item in site.pages %}
      {% if page_item.category == 'project' %}
        <li class="mono red"><a href='{{ page_item.url }}'>{{ page_item.title }}{% if page_item.project.champion and page_item.project.champion.name %}<br/>(Champion: {{ page_item.project.champion.name }}) {% endif %}</a></li>
      {% endif %}
    {% endfor %}
  </ul>
</nav>

{% for page_item in site.pages %}
  {% if page_item.project.skills_needed %}
    {% unless skills %}
      {% assign skills = page_item.project.skills_needed %}
    {% else %}
      {% assign skills = skills | concat: page_item.project.skills_needed %}
    {% endunless %}
  {% endif %}
{% endfor %}
{% assign skills = skills | uniq %}


<ul>
  {% for skill in skills %}
    <li class="mono red">{{skill}}</li>
  {% endfor %}
</ul>

<ul>
{% for skill in skills %}
  {% assign skill_projects = "" %}
  {% for page_item in site.pages %}
    {% if page_item.project.skills_needed contains skill %}
      {% if skill_projects == "" %}
        {% capture skill_projects %}{{skill_projects | append: page_item.title}}{% endcapture %}
      {% else %}
        {% capture skill_projects %}{{skill_projects | append: "|" | append: page_item.title}}{% endcapture %}
      {% endif %}
    {% endif %}
  {% endfor %}

  {{skill_projects}}

  <li class="bold mono brand-red">{{skill}}
    <ul>
      {% for project in projects_by_skill %}
        <li class="mono blue">{{project}}</li>
      {% endfor %}
    </ul>
  </li>

{% endfor %}
</ul>
