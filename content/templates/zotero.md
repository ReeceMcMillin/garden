---
title: "{{ title | safe }}"
cssclass: literature-note
alias: [{% if shortTitle %}"{{shortTitle | safe}}"{% else %}"{{title | safe}}"{% endif %}]
published: {{ date | format("YYYY-MM-DD") }}
tags: paper
{% if DOI %}doi: {{ DOI }}{% endif %}
{% if url %}link: {{ url }}{% endif %}
{%- if authors %}
authors:
{%- for creator in creators %}
- {{ creator.firstName }} {{ creator.lastName }}{% endfor %}{% endif %}
{% if publication %}publication: {{ publicationTitle }}{% endif %}
{% if publisher %}publisher: {{ publisher }} {% endif %}
---

{%- if abstractNote %}

> [!ABSTRACT] Abstract
> 
> {{ abstractNote }}

{%- endif %}
