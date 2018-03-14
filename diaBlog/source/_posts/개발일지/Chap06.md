---
title: Chap06. 개발일지 - CSS/Clip
date: 2018-03-09
tags: ['개발일지']
categories: ['개발일지']
layout: default 
---

### Clip을 이용하여 원그래프 만들기
- clip 속성을 이용하여 도형을 그리고 border-radius로 원형을 표현하여 원그래프를 css로 표현
- css animation을 이용하여 액션을 표현할 수도 있음
- 부모, 자식 요소를 부모로 왼쪽을 가리고 자식으로 반대도형을 오른쪽에 표현하여 반원을 점점 채우는걸 표현
- clip:rect(top, right, bottom, left) 를 이용하여 부모와 자식이 정반대의 수치로 도형을 표현


**codepen**
<p data-height="265" data-theme-id="light" data-slug-hash="wmwNvx" data-default-tab="css,result" data-user="lee-hyuna" data-embed-version="2" data-pen-title="Clip" class="codepen">See the Pen <a href="https://codepen.io/lee-hyuna/pen/wmwNvx/">Clip</a> by lee-hyuna (<a href="https://codepen.io/lee-hyuna">@lee-hyuna</a>) on <a href="https://codepen.io">CodePen</a>.</p>
<script async src="https://static.codepen.io/assets/embed/ei.js"></script>