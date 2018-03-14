---
title: Chap02. 개발일지 - OpenType Variable Fonts
date: 2017-12-15
tags: ['개발일지']
categories: ['개발일지']
layout: default 
---

## 오픈타입 가변 폰트
기존에는 폰트파일 하나당 하나의 스타일만 적용 가능 했다. 예를 들어 폰트 하나에 Bold, Italic, Light 등의 스타일을 클라이언트에서 로드하려면 각각의 스타일에 해당하는 총 3개의 폰트 파일이 필요했다.
이번에 제공되는 오픈타입 가변 폰트를 사용하면 하나의 파일만으로도 수많은 폰트 스타일을 적용할 수 있다.


```css
.heading {
  font-family: "Avenir Next Variable";
  font-size: 48px;
  font-variation-settings: 'wght' 700, 'wdth' 75;
}
.content {
  font-family: "Avenir Next Variable";
  font-size: 24px;
  font-variation-settings: 'wght' 400;
}
```

오픈타입 가변 폰트를 이용하면 반응형 타이포그래피를 적용하기 더 쉬워질 뿐 아니라 페이지 로드 속도도 개선할 수 있다.

## 노트 끄적
antivativerenderisation,
`<rvrn>`,
TrueType....

 
관련 링크: 
https://jayjnu.github.io/
[Introducing OpenType Variable Fonts](https://medium.com/@tiro/https-medium-com-tiro-introducing-opentype-variable-fonts-12ba6cd2369)