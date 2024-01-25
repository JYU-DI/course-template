# TIM Course Template


This is the base course template for TIM courses.
The template was initially made for DI courses at the University of Jyväskylä.

## Basic usage

> ![WARNING]  
> This guide is a work in progress!

0. Download [git](https://git-scm.com/) and [timsync](https://github.com/JYU-DI/timsync/releases) and install them. 

1. Fork and clone this template.

2. Initialize TIMSync repository in the cloned template.

    ```bash
    timsync init
    ```

    **Note:** You will need to specify TIM folder to upload your course to and TIM account to use for uploading.
    If you don't have a TIM account, create one (don't use your personal account).

3. Edit this template to fit your needs.

4. When you want to view the page on TIM, you can sync it using the following command:


    ```bash
    timsync sync
    ```


## Folder structure and files

- `_templates` - Folder for templates and partial includes
  - Any files put here are usable as templates
- `_config.yml` - Global configurations. Any values defined here are available globally via the `site` variable
- Any `.md` files are uploaded to TIM
- Any files and folders starting with `_` or `.` are skipped from being uploaded.

## Basic document structure

```md
---
title: Document title
---

This is a document.

You can access variables, use functions and evaluate expressions as follows:

{{ 1 + 1 }}

You can include partials from _template folder as follows:

{$ include "template.md" $}

The above templating values are evaluted staticall during sync.
You can also use TIM dynamic templating. To access values:

#- {nocache="true"}

%%username%%

To evaluate blocks:

{% if username == "Anonymous user" %}

You are not logged in

{% endif %}

#-

The above mark can be used to split text into blocks.
```
