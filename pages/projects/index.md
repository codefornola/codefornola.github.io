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
        <li class="center"><a href='{{ page_item.url }}'>{{ page_item.title }}{% if page_item.project.champion and page_item.project.champion.name %}<br/>(Champion: {{ page_item.project.champion.name }}) {% endif %}</a></li>
      {% endif %}
    {% endfor %}
  </ul>
</nav>