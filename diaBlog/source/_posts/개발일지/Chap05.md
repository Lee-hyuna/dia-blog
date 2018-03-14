---
title: Chap05. 개발일지 - 클로저 기초예제
date: 2018-01-25
tags: ['개발일지']
categories: ['개발일지']
layout: default 
---

오랜만에 스터디 하는 겸 개발일지를 적어본다 :^)
나한테 주어진 2주차 과제는 **for문을 돌려서 alert로 버튼안의 숫자들 (1,2,3,4,5)찍기**였다.
innerHTML, innerText 등등 태그안의 값을 가져오지 않고 index로만 가져오는 문제

즈엉답 :::

```
<script>
  // for문 돌려서 alert로 해당 숫자찍기
      var btn = document.querySelectorAll('.button-test');

      function btnEvt(idx) {
          var btnElement = btn[idx];
          btnElement.addEventListener('click', function() {
              alert(idx);
          })
      }

      for(var i = 0; i < btn.length; i++) {
          btnEvt(i)
      }
</script>
```

**codepen**
<p data-height="265" data-theme-id="0" data-slug-hash="wpLzWg" data-default-tab="js,result" data-user="lee-hyuna" data-embed-version="2" data-pen-title="wpLzWg" class="codepen">See the Pen <a href="https://codepen.io/lee-hyuna/pen/wpLzWg/">wpLzWg</a> by lee-hyuna (<a href="https://codepen.io/lee-hyuna">@lee-hyuna</a>) on <a href="https://codepen.io">CodePen</a>.</p>
<script async src="https://production-assets.codepen.io/assets/embed/ei.js"></script>


쿵칫따칫
-
끝