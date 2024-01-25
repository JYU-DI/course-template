```{settings=""}
preamble: preamble
globalmacros:
  CHAPTER: |!!
{% macro section(name, url, p) -%}
<a {% if url %}href="%%url%%"{% endif %} class="ch-sec-url {% if not url %}disabled{% endif %}"><span class="ch-sec-title">%%name%%</span> {% if p != None %}%%progress(p|round|int)%%{% endif %}</a>
{%- endmacro %}

{% macro ch_title(ch_num) -%}
## [%%ch_num%%]{.ch-num} %%courseChapters[ch_num].title%%
{% if courseChapters[ch_num].points != False %}%%progress(("ch_prog"~ch_num)|local(0)|round|int)%%{% endif %}
{%- endmacro %}

{% macro ch_sections(ch_num) -%}
{%- for sec in courseChapters[ch_num].sections -%}
%%section(sec.title, ("/view/" ~ homePath ~ "/" ~ chapterDir ~ "/" ~ ch_num ~ "/" ~ sec.path) if sec.path else None, (sec.points|local(0)))%%
{%- endfor -%}
{%- endmacro %}
!!
themes:
  - {{ site.base_path }}/styles/front_page
```

#- {area="title-banner"}

```{.title-content .nonumber atom="true"}
:::tim-jumbotron

:::jumbotron-title
[]{}

{$ block title $}{$ endblock title $}

:::

:::jumbotron-icons
{$ block icons $}{$ endblock icons $}
:::

:::
```

#- {area_end="title-banner" .title-bottom}

#- {.section-container visible="%%'Anonymous' in username %%"}
:::Warning
Et ole kirjautunut sisään! Kirjaudu sisään sivun ylälaidassa olevasta "Kirjaudu sisään" -painikkeesta.

Valitse "Kirjaudu sisään kohteella: Jyväskylän yliopisto" ja käytä sinun JYU-tunnuksiasi.
:::

#- {area="info-banner" .task-area-inverted}

{$ block info $} {$ endblock info $}

#- {area_end="info-banner"}

```{.sec-head .section-container #chapters atom="true"}
***

# Course chapters
```

#- {area="course-sections" .course-sections}

{$ for ch_index, ch_data in site.course_chapters $}

#- {area="progress-section{{ch_index}}" collapse="true" .progress-section nocache="true"}
%%CHAPTER%%
%%ch_title("{{ch_index}}")%%

#- {.ch-section-list}
%%CHAPTER%%
%%ch_sections("{{ch_index}}")%%

#- {area_end="progress-section{{ch_index}}"}

{$ endfor $}

#- {area_end="course-sections"}
