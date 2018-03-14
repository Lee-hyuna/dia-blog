---
title: Flexible Box Layout Module
date: 2018-03-08
tags: ['web', 'css', 'cssom', 'flexbox']
categories: ['Web']
layout: default 
---

### 개요
- css3의 새로운 layout 모드인 flex layout을 소개한다. (유동적 layout)
- 기존 4가지 레이아웃: block layout, inline-layout, table-layout, positioned-layout
- display 속성의 새로운 속성값 (진보된 block,inline 속성값) "display:flex"를 적용한 요소안의 포함된 자식요소들의 흐름과 배치되는 상대적인 크기 등을 유연하게 적용함으로 다양한 화면크기에 보다 최적화된 레이아웃을 제공
- flex layout에 관여된 새로운 속성들을 이용
- "display:flex" 속성을 적용하면 그 해당 요소와 지정된 요소 안에 포함되는 자식 요소가 Flexible Box의 특성을 갖게 된다.

### 특징
- 어떤 방향으로든 정렬(흐름)할 수 있다. (왼쪽정렬,오른쪽정렬,하단정렬,상단정렬)
- 순서를 뒤집거나 원하는 순서로 배치할 수 있다.
- 브라우저(스크린) 화면크기에 반응하여 유동적으로 크기를 변경할 수 있다.
- 형제요소나 부모요소에 영향을 주지 않고 정렬이 가능하다.

**properties**
margin, align-content, align-items, align-self, display, flex, flex-basis, flex-direction, flex-flow, flex-grow, flex-shrink, flex-wrap, justify-content, min-height, min-width, order

**Flex layout 구조**
![](/images/flex01.png)

**기본 최상위 속성(flex container)의 브라우져별 vendor prefixes.**
```$xslt
display: -webkit-box;     /* OLD - iOS 6-, Safari 3.1-6 */
display: -moz-box;        /* OLD - Firefox 19- (buggy but mostly works) */
display: -ms-flexbox;     /* TWEENER - IE 10 */
display: -webkit-flex;    /* NEW - Chrome */
display: flex;            /* NEW, Spec - Opera 12.1, Firefox 20+ */
```

**Flex container(flexbox 부모요소)**
```$xslt
display:flex          /* 블록 레벨 flex container */
display:inline-flex   /* 인라인 레벨 flex container */
```

**Flex container(flexbox 부모요소) 속성**
- flex-direction
    - "flex-direction:row" - 좌에서 우로 흐름(default)
    - "flex-direction:row-reverse" - 우에서 좌로 흐름
    - "flex-direction:column" - 위에서 아래로 흐름
    - "flex-direction:column-reverse" - 아래에서 위로 흐름
- flex-wrap
    - "flex-wrap:nowrap" - 줄바꿈이 되지 않고 한줄로 나열(default)
    - "flex-wrap:wrap" - 줄바꿈이 됨
    - "flex-wrap:wrap-reverse" - 줄바꿈이 거꾸로 됨
- flex-flow - flex-direction과 flex-wrap의 축약형
    - 예) "flex-flow:row wrap"
- justify-content - 가로정렬 속성
    - "justify-content:flex-start" - 왼쪽 정렬(default)
    - "justify-content:flex-end" - 오른쪽 정렬
    - "justify-content:center" - 가운데 정렬
    - "justify-content:space-between" - flex item들간의 공간을 동일하게 주며 정렬
    - "justify-content:space-around" - flex item의 좌우 여백을 동일하게 주며 정렬(여백 겹치지 않음)
- align-items - 세로정렬 속성
    - "align-items:stretch" - 꽉참 (default)
    - "align-items:flex-start" - 위로 정렬
    - "align-items:flex-end" - 아래로 정렬
    - "align-items:center" - 가운데 정렬
    - "align-items:baseline" - flex-item들의 inline요소들이(text) 같은 라인으로 정렬
- align-content - 라인이 두줄 이상일 경우 라인들의 세로정렬
    - "align-content:stretch" - 꽉참 (default)
    - "align-content:flex-start" - 위로 정렬
    - "align-content:flex-end" - 아래로 정렬
    - "align-content:center" - 가운데 정렬
    - "align-content:space-between" - 라인들간의 공간을 동일하게 주며 정렬
    - "align-content:space-around" - 라인들간의 상하 여백을 동일하게 주며 정렬(여백 겹치지 않음)
    
**Flex item(flexbox 자식요소) 속성**
- order - flex item들의 나열 순서를 지정
    - 논리적 순서는 마크업 순서대로 가고 비쥬얼적으로만 순서가 바뀐다.(초점 순서 바뀌지 않음)
    - default = 0
    - 예) "order:1" "order:2" "order:3" "order:-1"
- flex-grow - flex item의 여백처리
    - "flex-grow:0" - 여백 채우지 않음(default)
    - "flex-grow:1" - 남은 여백 채움(width:100%)
- flex-shrink - flex item의 길이가 container를 넘을 경우 처리
    - "flex-shrink:1" - container를 넘어가지 않음(default)
    - "flex-shrink:0" - flex item이 container의 크기를 넘어가도 크기를 유지
- flex-basis - width 속성
    - "flex-basis:auto" - flex item의 여백을 기준삼음(default)
    - "flex-basis:0" - flex item의 여백이 아닌 전체 크기를 기준삼음
    - 예) "flex-basis:100px" - 크기값을 넣을 경우 flex item의 max-width
- flex - flex-grow, flex-shrink, flex-basis의 축약형(flexible length)
    - "flex:0 auto","flex:initial" = "flex:0 1 auto" (default)
    - "flex:none" = "flex:0 0 auto"
    - "flex:auto" = "flex:1 1 auto" (fully flexible)
    - "flex:숫자" = "flex:숫자 1 0px" - flex item들의 상대값을 지정할 수 있음(%)
- margin - auto속성값이 적용이 된다
- align-self - flex item의 개별적 세로 정렬 : align-items참고




## 정리 결과!
- 블록요소와 비슷하다
- flex container,flex contents로 구분
- flex container와 flex contents는 마진이 겹치지 않음
- float,vertical-align는 flex contents에서 적용 안됨
- flex container는 그안의 flex contents를 적용하기 위해 존재하고 블록과 같지만 안의 요소들은 float적용 안됨




### 출처 및 참고
[Mozilla](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Basic_Concepts_of_Flexbox?redirectlocale=en-US&redirectslug=CSS%2FTutorials%2FUsing_CSS_flexible_boxes)
[Opera](https://dev.opera.com/articles/advanced-cross-browser-flexbox/)
