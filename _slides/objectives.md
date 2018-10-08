---

order: 50

---

## Goals and Objectives

<ul>
  {% if site.data.objectives and site.data.objectives.size > 0 %}
    {% for objective in site.data.objectives %}
      <li>{{ objective | markdownify }}</li>
    {% endfor %}
  {% else %}
    <li>None Specified</li>
  {% endif %}
</ul>

