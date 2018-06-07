---
layout: post
published: true
title: Remove comments using IntelliJ
subtitle: Remove source file comments using IntelliJ
date: '2018-06-07'
tags:
  - code
  - dataType
gh-repo: sherafatian/sherafatian.github.io
gh-badge:
  - star
  - watch
  - follow
---

# Remove source file comments using IntelliJ
You can use the "Replace" (or "Replace in Path" if you want to remove comments in multiple files) in the regular expression mode and then use this regular expression in the "Text to find" field:
```
(/\*([^*]|[\r\n]|(\*+([^*/]|[\r\n])))*\*+/|[ \t]*//.*)
```
and replace it with an empty string. Then press "All" to apply this replacement to the entire file or all the selected files. This will remove all block comments and line comments from your file. If you want only block comments to be removed, use this regex instead:
```
(/\*([^*]|[\r\n]|(\*+([^*/]|[\r\n])))*\*+/)
```
And if you want to just remove line comments, you can use this regex:
```
([ \t]*//.*)
```
However, I should warn that this works only %99.99 of times.

Source: ["Remove source file comments using IntelliJ" in StackOverFlow](https://medium.com/r/?url=https%3A%2F%2Fstackoverflow.com%2Fquestions%2F2613432%2Fremove-source-file-comments-using-intellij)