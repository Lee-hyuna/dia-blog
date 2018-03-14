---
title: Pug (jade)
date: 2017-12-13
tags: ['web', 'pug', 'jade']
categories: ['Web']
layout: default 
---


## Pug?
제이드는 Haml로 부터 큰 영향을 받은 고성능 템플릿 엔진이며 node를 위해 자바스크립트로 구현되었다.
html태그 보다 상당히 심플한 형태의 마크업을 작성하면 자동으로 html을 생성해주는 역할을 하고 있다.
pug는 HTML을 심플하게 표현할 수 있는 마크업언어인 HAML 영향을 받아 대부분의 문법은 HAML의 것을 차용한 것으로 보인다.
![](/images/pug1.png)


## 왜 pug인가
- 클라이언트 사이드 지원
- 뛰어난 가독성 - 계층구조를 구성하기 위해 들여쓰기를 사용한다.
- 유연한 띄어쓰기
- 블럭확대 (block - expansion)
- 믹스인 (mixins, 섞어쓰는 것)
- 스태틱 인클루드 (static includes)
- 보안을 위해 코드는 기본적으로 이스케이프 처리가 된다.
- html5 모드 (!!! 5 doctype)
- 다이내믹과 스태틱 태그 클래스 조합
- 템플릿 상속 (extends 확장)
- 외부 모듈로 Express JS 지원
- 객체, 배열, 그리고 열거형이 아닌 것들에 대해서도 each를 이용하여 투명하게 이터레이션 지원 (반복문 실행)
- tag를 이용한 접두어 처리 없음.
- if 문과 else 문이 사용가능.



## 주요특징
- Basic Process
![](/images/pug2.png)
**도메인입력**
1) 브라우저가 html을 로드 (DOM을 파싱한다.)
2) Angular.js를 로드한다
3) DOM Content Loaded Event를 기다린다.
 

**AngularJS 영역 초기화 과정**
4) DOM이 모두 로드되면 ng-app 지시자를 찾는다.
5) ng-app에서는 dependency injection 을 위해 사용되는 $injector를 생성한다.
6) injector 지시어는 어플리케이션의 모델을 위한 컨텍스트가 되는 루트 스코프를 생성한다.

 
**변경된 DOM의 화면 출력**
7) 최종적으로 ng-app을 기준으로 하위DOM을 컴파일하고 rootScope와 링크시킨다.



![](/images/pug3.png)
pug는 블락단위를 들여쓰기(indent)를 기준으로 하고있다.
들여쓰기를 하면 상위태그에 소속되기 때문에 들여쓰기가 거꾸로 되거나,
잘못되면 제대로 파싱되지 않고 오류가 나게 된다.
들여쓰기로 구분을 하기 때문에 소스도 명확하고 HTML에 비해 가독성이 상당히 좋다.
태그 다음에 문자역을 적으면 태그의 컨텐츠로 들어가게 되고, 속성은 괄호를 이용해 정의하게 된다.
 
태그를 정의할 때 CSS셀렉터 형태의 #, .을 이용해 id나 class값을 지정해줄 수 있다.
텍스트가 길어질 경우 | 를 이용해서 적어주면, 멀티라인으로 내용을 작성해 줄 수 있으며,
태그명 없이 .footer #footer와 같이 적으면 자동적으로 div가 적용이 된다.



## 문법
공식문서 : https://pugjs.org/language/attributes.html
참고문서 : https://naltatis.github.io/jade-syntax-docs/#variables

**반복문**
```html
items = ["one", "two", "three"]
each item, i in items
  li #{item}: #{i}

// 결과
<li>one: 0</li>
<li>two: 1</li>
<li>three: 2</li>
```


**조건절 (Conditionals)**
접두어 붙은 코드를 사용하는 방법과 같음
```html
for user in users
  if user.role == 'admin'
    p #{user.name} is an admin
  else
    p= user.name
```


**템플릿 상속(Template inheritance)**
block과 extends 키워드를 이용해 템플릿 상속을 지원한다. 자식 템플릿으로 교체되며, 재귀적으로 적용된다.
원한다면 기본내용을 갖고 있을 수도 있다, 하지만 선택사항이고 block scripts, block content, block footer옵션으로 사용할 수 있다.
```$xslt
html
  head
    h1 My Site - #{title}
    block scripts
      script(src='/jquery.js')
  body
    block content
    block foot
      #footer
        p some footer content
```
레이아웃을 확장하고 싶다면, 새로운 파일을 만들어서 extends지시어를 아래 코드처럼 사용한다. 지시어 옆에는 경로를 쓸 수 있으며, 확장자를 붙이는건 선택사항이다.
하나 혹은 그 이상의 블럭도 정의할 수 있는데, 해당 블럭은 부모 블럭 컨텐츠를 덮게된다. 

```$xslt
extends extend-layout

block scripts
  script(src='/jquery.js')
  script(src='/pets.js')

block content
  h1= title
  each pet in pets
    include pet
```
또한, 추가적인 블럭을 제공하기 위해 어떤 블럭을 덮어쓰는 것도 가능하다. 다음 예제를 보면 content가 sidebar와 primary를 덮어쓰기용 블럭으로 표현해 놓았다.
자식 템플릿은 필요에 따라서 content를 통으로 덮어쓸 수도 있다.
```$xslt
extends regular-layout

block content
  .sidebar
    block sidebar
      p nothing
  .primary
    block primary
      p nothing
```


**인클루드(Includes)**
정적으로 덩어리들 css, html같이 별도로 분리되어 있는 파일들을 포함할 수 있다. 예제는 헤더와 풋터를 인클루딩 하는 것이다.
```$xslt
  html
    include includes/head  
    body
      h1 My Site
      p Welcome to my super amazing site.
      include includes/foot
```
includes head와 includes foot둘다 layout.pug의 filename옵션에 맞춰 상대경로로 포함한다. 물론 절대경로도 가능
하지만, Express가 해당 일을 처리한다. 퐇마한다음 해당 파일들을 파싱해서 기대한대로 AST에 끼워넣는다. (AST : Abstract syntax tree)
```html
<html>
  <head>
    <title>My Site</title>
    <script src="/javascripts/jquery.js">
    </script><script src="/javascripts/app.js"></script>
  </head>
  <body>
    <h1>My Site</h1>
    <p>Welcome to my super lame site.</p>
    <div id="footer">
      <p>Copyright>(c) foobar</p>
    </div>
  </body>
</html>
```

**믹스인(Mixins)**
컴파일된 템플릿 내에 일반적인 자바스크립트로 변환된다.
```$xslt
  mixin list
    ul
      li foo
      li bar
      li baz
```
믹스인을 인자없이 쓰면 블럭이랑 비슷하게 보임.
```$xslt
  h2 Groceries
  mixin list
```
하나 이상의 인자를 가질 수 있다. 인자는 일반적인 자바스크립트 표현식처럼 씀.
```html
  mixin pets(pets)
    ul.pets
      - each pet in pets
        li= pet

  mixin profile(user)
    .user
      h2= user.name
      mixin pets(user.pets)

//결과
<div class="user">
  <h2>tj</h2>
  <ul class="pets">
    <li>tobi</li>
    <li>loki</li>
    <li>jane</li>
    <li>manny</li>
  </ul>
</div>
```



## 결론
- express Framework 을 이용한 퍼그라는 템플릿엔진이 있다.
- 퍼그는 Node.js 기반으로 만들어진 템플릿엔진이다.
- 템플릿엔진에 따라 차이가 있겠지만, 퍼그를 이용하면 html코드 작성 시 빠르게 타이핑할 수 있으며, 태그를 닫지 않아서 생기는 오류 등 실수를 줄일 수 있다.
- 축약형 문법 (프리프로세서)이 강점이고, 적은량의 코드이기때문에 가독성이 좋다.
- 또한, 뷰는 성격상 중복코드가 상당히 많이 발생하게 되는데 mixin이나 템플릿상속을 통해 중복코드를 많이 줄일 수 있다. (사실 템플릿엔진에서 대부분 제공하는 기능) 
- 단점이라면, 엔진이 설치되어있지 않다면 다시 html을  pug로 변환작성해야하는 번거로움이 있어 처음부터 pug로 만들어주지 않으면 효과를 보기 어려워 해결방안에 대한 부분은 고민해보아야 할 것 같다. 
- 짧은 코드와 쉽고 따라하기 좋은 명시적인 언어의 특성이 초보자들이 쉽게 접근가능함에 장점이 큰 템플릿엔진이라고 생각된다.





## 변환 사이트
https://naltatis.github.io/jade-syntax-docs/
http://html2jade.aaron-powell.com/

## 참고사이트
공식문서 : https://pugjs.org/api/getting-started.html
https://gist.github.com/japboy/5402844
https://github.com/pugjs/pug
http://blog.naver.com/oksk0302/220809954647
http://haml.info/about.html
http://uiandwe.tistory.com/964
http://dev-yt.tistory.com/17
http://uiandwe.tistory.com/964
http://blog.doortts.com/223

 