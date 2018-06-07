---
layout: post
published: true
title: sample of jqueryTmpl
subtitle: simple sample of jquery template
date: '2018-05-03'
tags:
  - jquery
  - tmpl
  - javascript
gh-repo: sherafatian/sherafatian.github.io
gh-badge:
  - star
  - watch
  - follow
---

# simple sample of jquery template
```javascript
var markup =
            "<li><b>44 ${id}</b>" +
            "@{{if id==1 }}s@{{/if}} (${title})</li>";

$.template("doFill", markup);

$.ajax({
      dataType: "json",
      url: '{{url('/user_group/0')}}',
      success: function (data) {
            $.tmpl("doFill", data).appendTo("#test");
      }
});
```
and 
```javascript
<script id="fillTemplate" type="text/x-jquery-tmpl">
      <li>
            <b>${id}</b> (${title})
      </li>
</script>
<script type="application/javascript" language="JavaScript">
      fillTable = function () {
            $.ajax({

                  dataType: "json",

                  url: '{{url('/user_group/0')}}',

                  success: function (data) {
                        $("#test").empty();
                        $("#fillTemplate").tmpl(data).appendTo("#test");
                  }
            });
      };
</script>
```