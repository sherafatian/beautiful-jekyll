---
layout: post
published: true
title: Check Enable User
subtitle: Check user enable in laravel 5.4
date: '2017-11-09'
tags:
  - enable
  - user
  - laravel
gh-repo: sherafatian/sherafatian.github.io
gh-badge:
  - star
  - watch
  - follow
---
in `app/Http/Controllers/Auth/LoginController.php` over this method:

```php
protected function credentials(Request $request)
{
  return array_merge($request->only($this->username(), 'password')
  , ['status' => 1]);
}
```
