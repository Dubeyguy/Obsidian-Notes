# Obsidian-Notes

### My Notes & Folders

{% for page in site.pages %}
  {% if page.url != "/" %}
* [{{ page.title | default: page.name }}]({{ page.url | relative_url }})
  {% endif %}
{% endfor %}
