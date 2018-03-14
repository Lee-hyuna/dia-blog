---
title: CSSOM (CSS Object module)
date: 2017-12-20
tags: ['web', 'css', 'cssom']
categories: ['Web']
layout: default 
---

## CSSOM

*출처 : https://varvy.com/performance/cssom.html
해당 문서를 번역했습니다.

 
 
 
### What is CSSOM?
CSS object model이라는 뜻. 이는 기본적인 웹페이지에서의 CSS "map"이다
DOM과 비슷하지만, HTML보다는 CSS에 가까우며 DOM과 결합된 CSSOM은 브라우저에서 웹페이지를 표하는데 사용됨

CSSOM은 페이지 렌더링에 매우 중요한 요소이며, 중요한 렌더링 경로의 핵심부분이며 웹 성능(웹페이지 로딩속도) 최적화의 중요한 요소로 작용된다.

![](/images/cssom.png)



##### 규칙적인 페이지 맵핑
더 정확히 말하면, CSSOM은 토큰을 식별하고 트리 구조에 연결된 노드로 변환합니다. 관련된 페이지의 모든 노드에 대한 전체 맵의 전체 맵은 CSS객체 모델이 될 것이다.