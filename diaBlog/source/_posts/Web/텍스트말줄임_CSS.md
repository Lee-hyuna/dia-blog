---
title: CSS 텍스트 말줄임
date: 2018-03-13
tags: ['CSS']
categories: ['Web']
layout: default 
---

일반 말줄임은 `text-overflow`나 `line-clamp`속성을 이용한다는 것은 
마크업공부를 한 사람들이라면 모두 다 알만한 내용들!
하지만 이번 포스트에는 제목+아이콘 (예를들면 New)
말줄임 + 아이콘이 유동적이게 우측에 붙어있어야 함에 대한 대응방법을 소개합니다 :>

**inline-block 이용하기**
<p data-height="265" data-theme-id="dark" data-slug-hash="GxRBOa" data-default-tab="css,result" data-user="lee-hyuna" data-embed-version="2" data-pen-title="GxRBOa" class="codepen">See the Pen <a href="https://codepen.io/lee-hyuna/pen/GxRBOa/">GxRBOa</a> by lee-hyuna (<a href="https://codepen.io/lee-hyuna">@lee-hyuna</a>) on <a href="https://codepen.io">CodePen</a>.</p>
<script async src="https://static.codepen.io/assets/embed/ei.js"></script>




**float:right 이용하기**
이 경우는 HTML에서 아이콘을 먼저 작성해야한다
<p data-height="265" data-theme-id="dark" data-slug-hash="QmWBBK" data-default-tab="html,result" data-user="lee-hyuna" data-embed-version="2" data-pen-title="float:right 이용하기" class="codepen">See the Pen <a href="https://codepen.io/lee-hyuna/pen/QmWBBK/">float:right 이용하기</a> by lee-hyuna (<a href="https://codepen.io/lee-hyuna">@lee-hyuna</a>) on <a href="https://codepen.io">CodePen</a>.</p>
<script async src="https://static.codepen.io/assets/embed/ei.js"></script>




**table-cell / line-clamp 이용하기**
<p data-height="265" data-theme-id="dark" data-slug-hash="PRoBdo" data-default-tab="css,result" data-user="lee-hyuna" data-embed-version="2" data-pen-title="table-cell / line-clamp 이용하기" class="codepen">See the Pen <a href="https://codepen.io/lee-hyuna/pen/PRoBdo/">table-cell / line-clamp 이용하기</a> by lee-hyuna (<a href="https://codepen.io/lee-hyuna">@lee-hyuna</a>) on <a href="https://codepen.io">CodePen</a>.</p>
<script async src="https://static.codepen.io/assets/embed/ei.js"></script>



**inline-block / line-clamp / absolute 이용하기**
<p data-height="265" data-theme-id="dark" data-slug-hash="PRoBdo" data-default-tab="css,result" data-user="lee-hyuna" data-embed-version="2" data-pen-title="table-cell / line-clamp 이용하기" class="codepen">See the Pen <a href="https://codepen.io/lee-hyuna/pen/PRoBdo/">table-cell / line-clamp 이용하기</a> by lee-hyuna (<a href="https://codepen.io/lee-hyuna">@lee-hyuna</a>) on <a href="https://codepen.io">CodePen</a>.</p>
<script async src="https://static.codepen.io/assets/embed/ei.js"></script>



**display:flex / -webkit-line-clamp 이용하기**
<p data-height="265" data-theme-id="dark" data-slug-hash="yKLqGX" data-default-tab="css,result" data-user="lee-hyuna" data-embed-version="2" data-pen-title="display:flex와 -webkit-line-clamp 이용하기" class="codepen">See the Pen <a href="https://codepen.io/lee-hyuna/pen/yKLqGX/">display:flex와 -webkit-line-clamp 이용하기</a> by lee-hyuna (<a href="https://codepen.io/lee-hyuna">@lee-hyuna</a>) on <a href="https://codepen.io">CodePen</a>.</p>
<script async src="https://static.codepen.io/assets/embed/ei.js"></script>