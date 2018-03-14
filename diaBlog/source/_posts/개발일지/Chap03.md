---
title: Chap03. 개발일지 - backface-visibility
date: 2017-12-15
tags: ['개발일지']
categories: ['개발일지']
layout: default 
---

예전에 모웹 마크업작업에서 버튼을 2개 겹쳐놓고 애니메이션으로 전환하는 작업을 진행하다,
특정 디바이스에서 버벅 거리는 현상이 있었다.

구글링한 결과 **이변가시성**에 대한 글이 있었는데, 참고하고자 남긴다 :^)

## backface-visibility 속성
3D transform과 연관되어 있으며, 겹쳐졌을 경우 뒷면의 가시성을 결정하는 속성이다
변형이 가해져 요소의 뒷면이 보여지게 될 때 번쩍거리는 효과를 숨기는 속성이다.

```css
div {
  -webkit-backface-visibility: hidden; /* Chrome, Safari, Opera */ 
  backface-visibility: hidden;
}
```

```javascript
object.style.backfaceVisibility="hidden"
```


`backface-visibility`
`hidden` : 이면을 숨김
`visible` : 기본값, 이면을 보여줌

---
**codepen**
<p data-height="265" data-theme-id="0" data-slug-hash="qpdLqz" data-default-tab="css,result" data-user="lee-hyuna" data-embed-version="2" data-pen-title="qpdLqz" class="codepen">See the Pen <a href="https://codepen.io/lee-hyuna/pen/qpdLqz/">qpdLqz</a> by lee-hyuna (<a href="https://codepen.io/lee-hyuna">@lee-hyuna</a>) on <a href="https://codepen.io">CodePen</a>.</p>
<script async src="https://production-assets.codepen.io/assets/embed/ei.js"></script>



## 지원현황
| IE    | Firefox | Safari | Chrome | Opera |
| :---- | :-----: | :----: | :----: | ----: |
| IE10+ | 지원     | 지원    | 지원    | 지원   |


참고 : https://www.w3schools.com/cssref/css3_pr_backface-visibility.asp