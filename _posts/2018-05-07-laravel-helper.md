---
layout: post
published: true
title: Laravel Helper
subtitle: Create Helper in laravel
date: '2018-05-07'
tags:
  - laravel
  - helper
  - autoload
  - dump-autoload
gh-repo: sherafatian/sherafatian.github.io
gh-badge:
  - star
  - watch
  - follow
---

# Laravel Helper

Create helper file in **Laravel**:
1. Create helper file (e.g. helper.php) in `App` folder.
2. Add this sentences in `composer.json`
    ```json
    "autoload":{
    "files":[
        "app/helper.php"
    ]
    }
    ```
3. run this command in console
    ```
    composer dump-autoload
    ```