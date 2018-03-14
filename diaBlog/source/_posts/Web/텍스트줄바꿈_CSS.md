---
title: CSS 텍스트 줄바꿈
date: 2018-03-09
tags: ['CSS']
categories: ['Web']
layout: default 
---

**white-space**
공백 줄바꿈 문자 처리 방법

- white-space: normal;
기본값 여러칸의 공백이나 줄바꿈을 공백 1칸으로 인식한다. 지정된 넓이의 끝에서 자동 줄바꿈 한다
![](/images/w1.jpg)


- white-space: pre;
띄워쓰기는 실제 입력한 칸대로, 줄바꿈도 엔터의 시점에서 그대로 노출이 된다 넘어가는 부분은 강제줄바꿈이 안됨
![](/images/w2.jpg)


- white-space: nowrap;
여러칸의 공백, 줄바꿈 모두 1칸으로 인식한다. 넓이를 지정하여도 자동으로 줄바꿈이 되지않게 강제로 개행을 막아준다
![](/images/w3.jpg)


<br>


**word-break**
텍스트가 들어가는 블럭요소의 너비에 맞춰 줄바꿈하는 스타일시트

- word-break: normal;
기본값. 단어 단위로 끊어서 줄바꿈 함 (우측의 여백이 생기게됨)
![](/images/w4.jpg)


- word-break: break-all;
글자단위로 줄바꿈을 함 (여백은 완벽하게 맞춰지지만, 단어의 중간에 블럭이됨)
![](/images/w5.jpg)


- word-break: keep-all;
한글일 경우 띄어쓰기 기준으로 줄바꿈 해줌 (아시아계열만 지원, ie/파폭.5이상)





<style>
.article-entry img {margin:0 !important}
</style>