---
  layout: code_for_new_orleans
  title: Current Projects
  menu_tag: Projects
  category: main_nav
---
Check out our current projects!

<ul>
  {% for page_item in site.pages %}
    {% if page_item.category == 'project' %}
      <li><a href='{{ page_item.url }}'>{{ page_item.title }}</a> {% if page_item.champion and page_item.champion.name %} (Champion: {{ page_item.champion.name }}) {% endif %}</li>
    {% endif %}
  {% endfor %}
</ul>