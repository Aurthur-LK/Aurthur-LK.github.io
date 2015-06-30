---
layout: post
title: Generating HTML using HTML methods
category: Technical
tags: Html
description: Generating HTML using HTML methods
---
Did you know that Laravel comes with a great amount of helpers to generate HTML in your Blade templates, like UL and OL lists, obfuscating email links, links to javascript and style assets? Check out the code below to see the HTML helpers in action

``` xml
# Generating a link to external Javascript
{{ HTML::script('js/app.min.js'); }}

// Generates :
<script src="http://path-to-your-app/js/app.min.js"></script>

# Generating a link to external stylesheet
{{ HTML::style('css/style.css'); }}

// Generates :
<link media="all" type="text/css" rel="stylesheet" href="http://path-to-your-app/css/style.css">

# Generating image tag
{{ HTML::image('img/img1.jpg'); }}

// Generates :
<img src="http://path-to-your-app/img/img1.jpg">

# Generating link tag
{{ HTML::link('http://laravel-tricks.com','Website for Laravel tricks', ['id'=>'myLink']); }}

// Generates :
<a href="http://laravel-tricks.com" id="myLink">Website for Laravel tricks</a>

# Generating obsufscated mailto tag
{{ HTML::mailto('myemail@mail.com','Some person', ['id'=>'myEmail']); }}

// Generates :
<a href="mailto:myemail@mail.com" id="myEmail">Some person</a>

# Generating HTML ordered list
{{ HTML::ol(['list item', 'list item', 'list item']); }}

// Generates :
<ol>
    <li>list item</li>
  <li>list item</li>
  <li>list item</li>
</ol>

# Generating HTML unordered list
{{ HTML::ul(['list item', 'list item', 'list item']); }}

// Generates :
<ul>
    <li>list item</li>
    <li>list item</li>
    <li>list item</li>
</ul>

# Generating HTML unordered list with nested elements
{{ HTML::ul(['list item', 'list item' => ['list item','list item'], 'list item']); }}

// Generates :
<ul>
    <li>list item</li>
  <li>list item
    <ul>
      <li>list item</li>
      <li>list item</li>
    </ul>
  </li>
  <li>list item</li>
</ul>
```
