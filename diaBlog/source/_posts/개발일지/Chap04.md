---
title: Chap04. 개발일지 - preload
date: 2017-12-22
tags: ['개발일지']
categories: ['개발일지']
layout: default 
---

관련문서 : http://zuu.kr/jank

웹폰트 관련 문서를 보다 **preload**에 대한 정리가 있으면 좋을 것 같아서 남긴다 :^)


## Function API

```
<head>
...
<script id="loadcss">
  // load a CSS file just before the script element containing this code
  loadCSS( "path/to/mystylesheet.css", document.getElementById("loadcss") );
</script>
...
</head>
```

```
<link rel="preload" href="path/to/mystylesheet.css" as="style" onload="this.onload=null;this.rel='stylesheet'">
<noscript><link rel="stylesheet" href="path/to/mystylesheet.css"></noscript>
```
