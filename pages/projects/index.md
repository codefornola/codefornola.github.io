---
  layout: code_for_new_orleans
  title: Current Projects
  menu_tag: Projects
  category: main_nav
---
Check out our current projects!

<nav>
  <ul>
    {% for page_item in site.pages | sort: 'title' %}
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
{% assign skills = skills | uniq | sort %}

Projects by skill needed:

<ul>
{% for skill in skills | sort %}
  {% assign skill_projects = site.pages | where:"category", "project" | where_exp:"page", "page.project.skills_needed contains skill" %} 
  <li class="bold mono brand-red">{{skill}}
    <nav><ul>
      {% for project_page in skill_projects %}
        <li class="mono brand-blue">
          <a href='{{project_page.url}}'>{{project_page.title}}</a>
        </li>
      {% endfor %}
    </ul></nav>
  </li>
{% endfor %}
</ul>
