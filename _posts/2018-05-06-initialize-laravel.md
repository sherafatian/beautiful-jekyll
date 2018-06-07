---
layout: post
published: true
title: Initialize laravel
subtitle: Start in laravel
date: '2018-05-06'
tags:
  - laravel
  - start
  - initialize
gh-repo: sherafatian/sherafatian.github.io
gh-badge:
  - star
  - watch
  - follow
---

# Initialize laravel

1. Install Laravel via composer
    ```
    composer create-project --prefer-dist laravel/laravel blog
    ```

2. Config all about localization.
    * Create Message folder for your language and set locale to name of your language folder (e.g fa)
    * Set Timezone to `Asia/Tehran` in *config/app.php*

3. Set database Config parameters
    * set server parameters in *.env* file
    * set engine to `InnoDB`

4. correct database connect for *Mysql*. you should change your `AppServiceProvider.php` file to this:
    ```php
    use Illuminate\Support\Facades\Schema;

    function boot(){
      Schema::defaultStringLength(191);
    }
    ```

5. [Implement Annotation Collective]

6. Config project for *xampp* or *wamp*
   * cut (or copy) all files in *public* directory to *root* directory
   * set *APP_URL*
   * set directories in `index.php`

7. Impliment **Auth** module
    ```
    php artisan make:auth
    php artisan migrate
    ```

8. Implement *Laravel mix*
    ```bash
    npm install
    ```
    sample in *mixer*
    ```javascript
    mix.js([
      'resources/assets/jquery3.2.1/jquery-3.2.1.js',
      'resources/assets/jquery3.2.1/jquery-migrate-1.4.1.js',
      'resources/assets/jquery3.2.1/jquery-migrate-3.0.0.js',
    ], 'public/js/all.js');
    mix.styles([
      'resources/assets/bootstrap-3.3.7/css/bootstrap.css',
      'resources/assets/bootstrap-jalali-datepicker-master/bootstrap-datepicker.css'
    ], 'public/css/all.css');
    mix.copy(
      'resources/assets/bootstrap-3.3.7/fonts/glyphicons-halflings-regular.eot',
      'public/fonts/glyphicons-halflings-regular.eot'
    );
    ```