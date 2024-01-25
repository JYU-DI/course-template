```{settings=""}
override_user_themes: true
comments: private
sidemenu_initial_state: closed
displayViewInitialState: false
hide_readmarks: true
globalmacros:
  ADDFOREVERY: |!!
{% macro progress(p) -%}
<div class="ch-progress-container"><div class="ch-progress"><div class="ch-progress-bar" style="--prog: %%p%%%"></div></div> [%%p%%%]{.ch-progress-num}</div>
{%- endmacro %}
!!
themes:
  - dia-mini
  - {{ site.base_path }}/styles/course

macros:
  courseChapters: {{ site.course_chapters | json_encode }}
  homePath: {{ site.base_path }}
  chapterDir: chapters
```
