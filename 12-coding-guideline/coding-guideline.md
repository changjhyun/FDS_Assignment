##Style Guide
###폴더 네이밍 규칙
#### 공통규칙
* 첫 시작에 숫자, 특수문자, 대문자는 지양
* '형태-의미-상태' 순서로 조합하며, 3단계를 넘어가지 않도록 한다.
* 정의 시 prefix, subfix, suffix를 최대한 활용한다.
####ID/CLASS 규칙
*ID는 camelcase방식으로 하며, CLASS는 하이픈(-) 방식으로 사용한다.
* ID는 화면에서의 고유 기능을 명시하도록 한다.
* CLASS는 요소의 기능을 표현하도록 한다.
* ID는 문서 내 한번만 사용된다는 점을 유의해야 한다.
####HTML
* 서비스의 대분류에 따라 폴더를 생성하고 해당 폴더 안에 HTML 파일을 생성한다.
```
ex) /대분류명/notice.html
 /대분류명/notice_view.html
```

####CSS
* 서비스별 공통요소는 common.css 에 정리하며, 서비스별 대분류에 따라 '서비스명_대분류명'으로 만들어 사용한다.

---
###HTML Convention
####HTML5 DOCTYPE
```
<!doctype html>
```

####문서 제목의 규칙
```
컨텐츠 제목(공백) - (공백)하위 섹션명(공백)
```
#####컨텐츠 제목
* 서비스에서 제공하는 컨텐츠의 제목
* 컨텐츠 제목과 서비스명 간의 구분자는 반드시 '&ndash;'(`&ndash;`) 기호를 사용한다. (검색엔진 크롤링 시 minus 기호가 들어간 컨텐츠 제목을 정확히 뽑아내기 어렵기 때문이라고 함)

#####하위 섹션명
* 하위 섹션명은 서비스명 앞에 표기한다.
* 하위 섹션명의 구분자는 '|'(vertical bar / pipe 기호)를 사용한다.
* 하위 섹션명은 필수 요소는 아니다.

#####Meta title 요소
* 검색 엔진 최적화를 위하여 meta 요소를 이용하여 문서 제목을 추가 명시한다.
* 컨텐츠 상세 페이지에서는 컨텐츠 제목 만을 표기한다.
```
<meta name="title" content="FAST CAMPUS" />
<meta name="title" content="About | Portfolio" />
```

####Layout Guide
#####HTML5 기본 레이아웃
* HTML5 레이아웃 가이드
* article : 태그 자체로 완전한 하나의 개별 컨텐츠 article은 그 안에 section을 가질 수 있음
* section : 제목 태그(Heading Tag)를 지닌 영역 구분

#####주석표기
######수정 작업 시 주석 처리
* 마크업 수정 시, 수정 부분을 표기하는 주석은 다음과 같이 날짜를 기입하여 사용한다.
```
<!-- 2016/7/21 주석내용 -->
```
* 주의 사항
1. 너무 많은 주석은 유령문자버그를 생성하므로 되도록 자제한다.
2. 시작하는 구분자(`<!`)와 주석을 시작하는 구분자(`--`) 사이에는 공백 문자(white space)가 올 수 없다.
```
<! -- comments (X) -->
<!-- comments (△) -- > 내용을 종료하는 "--"와 코멘트을 종료하는 ">" 사이에는 공백 문자(white space)가 올 수 있다.
<!--- comments (X) ---> 코멘트 내용에서 두개 이상의 하이픈('-')을 연속해서 사용하면 안된다.
```

####들여쓰기
* 코드의 가독성을 높이기 위하여 들여쓰기를 사용하며 탭 1개의 크기는 공백 2칸으로 설정한다. 또한 마크업의 깊이가 깊어질 때마다 탭 1개만큼 들여쓰지만 다음의 경우 들여쓰지 않을 수도 있다.
```
- HTML Element의 자식 Element인 head, body
- thead Element의 자식 Element인 tr
```

####Attribute
#####Attribute 작성
* Attribute 값은 큰따옴표("")로 묶는다.

#####Attribute 우선순위
* Attribute의 우선순위는 다음 순위를 따른다.

|    순서   |   속성   |
| :------: |:-------:|
| 1   | rel  |
| 2   | type  |
| 3   | href, src  |
| 4   | width, height  |
| 5   | target  |
| 6   | id  |
| 7   | name  |
| 8   | class  |
| 9   | style  |
| 10   | title, alt  |
| 11   | 기타  |


---

###HTML 문법
####일반
#####HTML5
```
<!DOCTYPE html>
<html lang="ko-kr">
<head>
  <meta http-equiv="X-UA-Compatible" content="IE=Edge">
  <meta charset="utf-8">
  <title>타이틀</title>
</head>
<body>
...
</body>
</html>
```

####DTD 및 인코딩
#####HTML5
```
<!DOCTYPE html>
```

#####엄격(Strict) DTD 금기 사항

|    엘리먼트    |   금기사항|
| :-------: | :-------|
|  a   | 다른 a 엘리먼트들을 포함할 수 없다.  |
|  pre   | img, object, big, small, sub 또는 sup 엘리먼트들을 포함 할 수 없다.   |
|  button   | input, select, textarea, label, button, form, fieldset, iframe 또는 isindex 엘리먼트들을 포함할 수 없다.   |
|  label   | 다른 label 엘리먼트들을 포함할 수 없다.   |
|  form   | 다른 form 엘리먼트들을 포함할 수 없고, input 엘리먼트를 직접 사용할 수 없으며, 반드시 div, p 엘리먼트와 같은 블록 레벨 요소로 감싸주어야 한다.   |
|  body   | text/img를 직접 사용할 수 없고, 반드시 div, p 엘리먼트와 같은 블록 레벨 요소로 감싸주어야 한다.   |
|  blockquote   | text는 div, p 엘리먼트와 같은 블록 레벨 요소로 감싸주어야 한다.   |

#####엄격(Strict) DTD 필수 속성
```
<map name="CDATA" >
<area alt="%Text;">
<img src="%URI;" alt="%Text;" >
<param name="CDATA">
<form action="%URI;">
<optgroup label="%Text;">
<textarea rows="NUMBER" cols="NUMBER" >
<base href="%URI;">
<meta contect="CDATA" >
<style type="%ContentType;">
<script type="%ContentType;">
```

####블록요소, 인라인요소
#####블록요소(Block Element)
* 줄을 바꿔 각각 독립된 줄에 표시된다.
* 별도의 CSS 컨트롤이 없다면 해당 문서 크기 만큼의 너비를 가지며, 문서의 위에서부터 차곡차곡 쌓이는 형태로 표시된다.
* 인라인 요소와 텍스트 혹은 또 다른 블록요소를 포함할 수 있다.

#####인라인요소(Inline Element)
* 다른 인라인 요소와 같은 줄에 표시된다.
* 별도의 CSS 컨트롤이 없다면 해당 문서의 좌측부터 우측으로 나열되는 형태로 표시된다.
* 또 다른 인라인 요소와 텍스트를 포함 할 수 있으나, 블록요소를 포함할 수는 없다.

---


###HTML5 Elements
####HTML5 Element

HTML5의 요소는 0개 이상의 카테고리에 속하며, 각 카테고리는 서로 특성이 비슷한 요소끼리 묶어둔 분류이다. HTML5는 다음과 같은 카테고리들을 사용한다.
>**Metadata**
메타데이터는 나머지 내용의 표현이나 행동을 설정하거나, 또는 현재 문서와 다른 문서의 관계를 설정하거나, 혹은 미분류 정보들을 포함한다.
`base, command, link, meta, noscript, script, style, title`

>**Flow Content**
문서 바디와 응용프로그램에서 사용되는 요소 대부분은 플로우 컨텐츠로 분류 된다.
`a, abbr, address, area (map 요소의 자식 요소인 경우), article, aside, audio, b, bdi, bdo, blockquote, br, button, canvas, 
cite, code, command, datalist, del, details, dfn, div, dl, em, embed, fieldset, figure, footer, form, h1, h2, h3, h4, h5,
h6, header, hgroup, hr, i, iframe, img, input, ins, kbd, keygen, label, map, mark, math, menu, meter, nav, noscript,
object, ol, output, p, pre, progress, q, ruby, s, samp, script, section, select, small, span, strong,
style (scoped 속성이 있으면), sub, sup, svg, table, textarea, time, ul, var, video, wbr, text`

>**Section Content**
섹션 컨텐츠는 헤딩과 푸터의 유효범위를 정의한다. 제목과 그 내용을 포함하는 범위를 지정한다.
`article, aside, nav, section`
섹션 컨텐츠 요소에는 헤딩과 아웃라인을 포함할 수 있다.

>**Heading Content**
섹션(섹션 컨텐츠를 이용해 명시적으로 마크업 했거나, 또는 제목 컨텐츠에 의해 암시적으로 마크업 된)의 헤더를 정의한다.
`h1, h2, h3, h4, h5, h6, hgroup`

>**Phrasing Content**
문서의 텍스트이고, 또한 그 텍스트를 문단 내부 레벨로 마크업하는 요소들이다. 프레이징 컨텐츠가 모야 문단을 구성한다.
`a (프레이징 콘텐츠만을 포함하는 경우), abbr, area (map 요소의 자식요소인 경우), audio, b, bdi, bdo, br, button, canvas,
cite, code, command, datalist, del (프레이징 콘텐츠을 포함하는 경우), dfn, em, embed, i, iframe, img, input,
ins (프레이징 콘텐츠만을 포함하는 경우), kbd, keygen, label, map (프레이징 콘텐츠만을 포함하는 경우), mark, math, meter,
noscript, object, output, progress, q, ruby, s, samp, script, select, small, span, strong, sub, sup, svg, textarea, time,
var, video, wbr, text`
일반적으로 프레이징 콘텐츠 모델 요소를 포함할 수 있는 요소들은 최소 하나의 공백이 아닌 텍스트를 포함하거나 또는 최소 하나의 임베디드 콘텐츠를 포함하여야 한다.

>**Embedded Content**
임베디드 콘텐츠는 다른 리소스(음악, 영상 등)를 문서에 삽입하는 콘텐츠나, 문서에 삽입된 다른 형태에서 유래한 콘텐츠를 말한다.
`audio, canvas, embed, iframe, img, math, object, svg, video`
HTML 네임스페이스에 속하지 않으면서, 내용을 포함하고 있지만, 메타데이터가 아닌 것들을 이 명세의 내용 모델 정의에서는 임베디드 컨텐츠라 한다. (MathML, SVG 등입니다)

>**Interactive Content**
사용자와의 상호작용을 위해 사용되는 컨텐츠이다.
`a, audio (controls 속성이 있으면), button, details, embed, iframe, img (usemap 속성이 있으면),
input (type 속성이 hidden 상태가 아니면), keygen, label, menu (type 속성이 toolbar 상태면),
object (usemap 속성이 있으면), select, textarea, video (controls 속성이 있으면)`

또한, 특정요소는 폼관련 요소로 따로 분류하여 다양한 폼 관련 처리 모델에서 세부적으로 분류한다.
몇몇 요소들은 특정 요소만의 독특한 요구사항을 가지고 있으며, 어느 카테고리에도 속하지 않는다.

####HTML5 New Element
#####섹션, 헤딩 관련 요소
######Section

- Category : Flow Content, Section Content
- 의미 : 일반적인 문서의 섹션을 의미함
- 사용 : 내용이 문서의 개요에 명시적으로 나타날때 사용하는것이 적합하며, 의미 부여 없이 스타일 적용만을 위한 범용 컨테이너가 아님. 장이나 절 단위로 사용하며 Heading 요소를 사용하여 제목을 넣어 사용

######Article
- Category : Flow Content, Section Content
- 의미 : HTML5의 명세에 의하면 article은 독립적으로 구성 할 수 있는 콘텐츠로 별도로 배포하거나 재사용하기 위한 구조임.
- 사용 : article 요소끼리 중첩이 가능하나 원칙적으로 외부 article 요소의 내용과 관련이 있어야 함. 웹표준개발팀 내부 가이드로는 article은 자체로 완전한 하나의 개별 콘텐츠로 그 내부에 Section을 포함할 수 있다.

```
<article id="mArticle">
    <h2>미디어다음 정치뉴스 목록</h2>
    <section>
        <h3>복지시장 '박원순호' 본격적인 닻 올랐다</h3>
        <p>16일 16일 35대 서울특별시장의 공식 취임식을 계기로 '복지시장'을 표방하는 박원순호의 닻이 본격적으로 올랐다</p>
        <ul>
            <li>박원순 파격 행보의 절정 '온라인 취임식'</li>
            <li>박원순 서울시장 취임식 어떻게 진행됐나</li>
            <li>검은머리 대머리 될 때까지 충성</li>
        </ul>
    </section>
</article>
```

######Nav
- Category : Flow Content, Section Content
- 의미 : 네비게이션 사이트 내에 다른 페이지로 링크되거나, 한 페이지 내부에서 이동하는 링크에 사용
- 사용 : 링크 모두를 nav에 둘 필요는 없으며, 의미상 네비게이션에 해당할때 사용. footer나 그 외의 section등에서 사용되는 링크는 그 자체의 요소를 사용
```
<nav>
    <menu>
        <li><a href="#">홈</a></li>
        <li><a href="#">뉴스</a></li>
        <li><a href="#">블로그</a></li>
        <li><a href="#">카페</a></li>
    <menu>
</nav>
<article id="mArticle">
    <h2>'미디어다음 정치뉴스 목록</h2>
    <section>
        <h3>복지시장 '박원순호' 본격적인 닻 올랐다</h3>
        <p>16일 16일 35대 서울특별시장의 공식 취임식을 계기로 '복지시장'을 표방하는 박원순호의 닻이 본격적으로 올랐다</p>
        <ul>
            <li><a href="#">박원순 파격 행보의 절정 '온라인 취임식'</a></li>
            <li>박원순 서울시장 취임식 어떻게 진행됐나</li>
            <li>검은머리 대머리 될 때까지 충성</li>
        </ul>
    </section>
    <footer>
        <a href="#">회사소개</a>
    </footer>
</article>
```

######Main
- Category : Flow Content
- 의미 : 문서나 애플리케이션의 body 영역의 주요 콘텐츠 영역. 접근성을 향상시키며, 검색엔진에서의 콘텐츠 가중치를 향상시킨다.
- 사용 : 문서의 고유한 내용으로 페이지 내에서 단일 적용한다. (사이트 네비게이션 링크, 저작권 정보, 사이트의 로고 및 배너 등은 제외)
article, aside, footer, header, nav 의 하위 요소로 사용할 수 없다.

######Aside
- Category : Flow Content, Section Content
- 의미 : 주 콘텐츠와 간접적인 관계인 콘텐츠를 표현
- 사용 : 블로그의 사이드바 형태로 표현되는것이 일반적임
######Header
- Category : Flow Content
- 의미 : 페이지의 헤더를 나타냄
- 사용 : 콘텐츠 목차, 검색 폼, 관련 로고 등을 포함하는 래퍼 요소로 사용 가능. 섹션 콘텐츠가 아니므로 섹션을 설정하진 않음. 그룹화를 위한 요소임.

######Footer
- Category : Flow Content
- 의미 : 페이지의 풋터를 나타냄
- 사용 : 문서 작성자, 관련 문서의 링크, 저작권자 등과 같은 콘텐츠를 작성. header와 마찬가지로 섹션 콘텐츠가 아니므로, 섹션을 설정하지 않음. 그룹화를 위한 요소이다.