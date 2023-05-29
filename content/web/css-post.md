+++
title = "CSS"
date = "2023-05-28T21:29:20+02:00"
tags = ["golang", "programming", "theme", "hugo"]
categories = ["web", "css"]
banner = "https://velog.velcdn.com/images/untiring_dev/post/9bb80049-c314-4962-afc7-6099d6340168/image.png"
authors = ["최수빈"]
+++

## CSS란?
* * *
CSS는 Cascading Style Sheets의 약자로 기본적인 스타일이 이미 지정된 HTML 요소를 개발자가 직접 다양한 스타일로 디자인할 수 있는 언어입니다.

CSS는 HTML과 함께 웹을 구성하는 기본 프로그래밍 요소 입니다. HTML이 텍스트나 이미지, 표와 같은 구성 요소를 웹 문서에 넣어 뼈대를 만드는 것이라면 CSS는 색상이나 크기, 이미지 크기나 위치, 배치 방법 등 웹 문서의 디자인 요소를 담당 합니다.



![css적용예시](https://dinfree.com/assets/img/css1.png)

* CSS는 Cascading Style Sheet의 약어.
* CSS는 HTML로 부터 디자인적인 요소를 분리해 정의할 수 있음.
* 잘 정의된 css 는 서로 다른 여러 웹페이지에 적용할 수 있음. -> 템플릿/테마
* 자바스크립트와 연계해 동적인 콘텐츠 표현이나 디자인 적용 가능.


### CSS를 사용해야만 하는 이유

* 웹 문서의 내용과 상관없이 디자인만 바꾸거나 디자인은 그대로 두고 웹 문서의 내용 변경이 용이.
* 다양한 기기(PC, 스마트폰, 태블릿 등)에 맞게 탄력적으로 바뀌는 콘텐츠 -> 반응형 디자인(Responsive Design)
* 동일한 문서구조를 가지고 서로 다른 CSS 테마 적용이 가능 함.



## CSS 기본 문법
* * *
CSS는 선택자와 선언부로 구성됩니다. 선택자는 스타일을 지정할 HTML 요소(태그,아이디 등)를 가리킵니다. 선언부에는 CSS 속성 이름과 값이 포함됩니다. 속성이 여러 개일 경우, 한 줄로 나열해도 상관없지만 여러 줄에 걸쳐 작성하는 것이 좋습니다.

선택자  {속성:값; 속성:값....}

예)

\/* h1태그의 색상을 빨간색으로 크기는 15px로 지정합니다.*/

\h1 {color:red; font-size:15px;}

* CSS 구문은 선택자(selector)와 선언부(declaration)로 구성.
* 선택자는 디자인을 적용하고자 하는 HTML요소. -> 선택자 정의가 중요
* 선언부는 콜론(:)으로 구분 되어진 다수의 항목을 포함.
* 각 선언은 항상 세미콜론(;)으로 끝나며, 선언블록은 중괄호({ })로 묶음.
* /* comment */은 코드를 설명하는 데 사용됨.


### CSS 적용 방법

HTML 문서에 CSS를 적용하는 방법에는 내부 스타일시트, 외부 스타일시트, 인라인 스타일 등 총 3가지 방법이 있습니다.



![css적용방법](https://dinfree.com/assets/img/css2.jpg)

### 내부 스타일 시트

html 파일에 스타일을 기술하는 방법으로 <head></head> 태그 사이에 <style></style> 태그 부분에 작성합니다. html 과 css 가 한 파일에 있으므로 작업이 쉽고 간편하지만 css의 재활용이 안되는 문제가 있어 특별한 경우가 아니면 외부 스타일시트가 권장 됩니다.


    <head>

    <style>

    body {
        background-color: red;
    }


    h1 {
        color: maroon;
        margin-left: 40px;
    } 

    </style>

    </head>

    <body>

        ...

    </body>


### 외부 스타일 시트

css 를 작성하는 가장 기본적인 방법 입니다. 별도의 파일에 CSS 문서를 작성하고 해당 CSS를 필요로 하는 html 문서에서 불러와 사용하는 형식 입니다. 이때 css는 동일한 서버에 있어도 되고 url을 통해 다른 서버의 css를 불러오는 것도 가능 합니다.

    <link rel="stylesheet" type="text/css" href="mystyle.css">
    <link rel="stylesheet" type="text/css" href="http://cdn.site.com/css/mystyle.css">


### 인라인 스타일

html 태그에 필요한 디자인 속성을 직접 작성하는 형식 입니다. 그때 그때 필요한 디자인을 바로 적용할 수 있다는 편리함이 있지만 일관된 디자인 체계를 유지하는 데에는 방해가 되기 때문에 꼭 필요한 경우가 아니라면 사용하지 않도록 합니다.

    <h1 style="color:blue; margin-left:30px;">This is a heading</h1>
