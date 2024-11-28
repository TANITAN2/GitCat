## 📘 **CSS │ 기본 사용법 및 개념**

> **CSS**(Cascading Style Sheets)는 HTML **문서의 스타일을 정의**하는 데 사용되는 스타일 시트 언어입니다.<br>HTML은 웹 페이지의 구조를 정의하고, CSS는 그 **구조를 어떻게 보여줄지(디자인)를 정의**하며, CSS는 색상, 글꼴, 레이아웃, 간격, 크기 등 다양한 시각적 요소를 제어할 수 있습니다.

* * *
<br>

### ❓ **CSS의 기본 개념**
<br><br>
#### 1️⃣ **선택자(Selector)**

> CSS는 HTML 요소에 스타일을 적용하기 위해 선택자를 사용합니다. 선택자는 스타일을 적용할 HTML 요소를 지정하는 방법입니다.
   
* **태그 선택자**: HTML 태그 이름을 사용하여 모든 해당 태그에 스타일을 적용.
* **클래스 선택자**: 특정 클래스를 가진 요소에 스타일을 적용. `.`으로 시작.
* **아이디 선택자**: 특정 아이디를 가진 요소에 스타일을 적용. `#`으로 시작.
* **속성 선택자**: 특정 속성 값에 따라 스타일을 적용.<br>　
<br><br>
#### 2️⃣ **속성(Property)**

> 스타일을 적용하려면 속성을 정의해야 합니다. 각 속성은 값이 필요하며, 그 값에 따라 스타일이 적용됩니다.<br>예를 들어, `color`, `font-size`, `margin`, `padding`, `background-color` 등이 있습니다.

<br><br>
#### 3️⃣ **값(Value)**

> 속성에 대한 실제 값입니다.<br>예를 들어, `color: red;`에서 `color`는 속성이고, `red`는 값입니다.

<br><br>
#### 4️⃣ **구문(Syntax)**

> CSS는 `{}`로 둘러싸인 규칙의 집합으로 구성됩니다. 각 규칙은 `선택자 { 속성: 값; }` 형식을 따릅니다.
　
###### ex)
```html
h1 {
   color: blue;
   font-size: 30px;
}
```
위의 예시는 `h1` 태그에 파란색 글꼴과 30px 크기를 적용한 CSS 규칙입니다.

* * *
<br>

### ❓ **CSS 적용 방법**
<br><br>

#### 1️⃣ **내부 스타일(Internal CSS)**
HTML 문서 내에서 `<style>` 태그를 사용하여 CSS를 정의합니다. `<style>` 태그는 `<head>` 태그 안에 위치합니다.

###### ex)
```html
<html>
<head>
  <style>
    body {
      background-color: lightgray;
    }
    h1 {
      color: blue;
    }
  </style>
</head>
<body>
  <h1>안녕하세요, CSS!</h1>
</body>
```
<br><br>
#### 2️⃣ **외부 스타일(External CSS)**
CSS 코드를 별도의 `.css` 파일로 작성하고, HTML 문서에서 링크를 통해 연결합니다. 이 방법은 여러 HTML 파일에서 동일한 스타일을 공유할 때 유용합니다.

###### ex)
* **style.css**(외부 CSS 파일)
```css
body {
  background-color: lightgray;
}
h1 {
   color: blue;
}
```
* **HTML 파일**
```html
<html>
<head>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <h1>안녕하세요, CSS!</h1>
</body>
</html>
```
<br><br>
#### 3️⃣ **인라인 스타일(Inline CSS)**

HTML 태그에 직접 `style` 속성을 사용하여 CSS를 적용하는 방법입니다. 이 방법은 한 요소에만 스타일을 적용할 때 사용됩니다.

###### ex)
```html
<h1 style="color: blue; font-size: 30px;">안녕하세요, CSS!</h1>
```

* * *
<br>

### ❓ **CSS 예시**
<br><br>
#### 1️⃣ **텍스트 스타일링**

###### ex)
```css
h1 {
  color: red;          /* 텍스트 색상 */
  font-family: Arial;  /* 글꼴 */
  font-size: 36px;     /* 글꼴 크기 */
  text-align: center;  /* 텍스트 정렬 */
}
```
<br><br>
#### 2️⃣ **배경 스타일링**

###### ex)
```css
body {
  background-color: lightblue;             /* 배경 색상 */
  background-image: url('background.jpg'); /* 배경 이미지 */
  background-size: cover;                  /* 배경 이미지 크기 */
}
```
<br><br>
#### 3️⃣ **박스 모델 속성**

박스 모델(Box Model)은 HTML 요소가 웹 페이지에서 차지하는 공간을 정의합니다. 이 모델은 마진(`margin`), 경계(`border`), 패딩(`padding`), 콘텐츠(`content`)로 구성됩니다.

```css
div {
  margin: 20px;            /* 요소와 다른 요소 사이의 간격 */
  padding: 10px;           /* 요소 내의 콘텐츠와 경계 사이의 간격 */
  border: 2px solid black; /* 요소의 경계선 */
  width: 300px;            /* 요소의 너비 */
  height: 200px;           /* 요소의 높이 */
}
```
<br><br>
#### 4️⃣ **플렉스박스(Flexbox) 레이아웃**

플렉스박스는 요소들을 간단하게 정렬하고 배치하는 데 유용한 CSS 레이아웃 모듈입니다.

```css
.container {
  display: flex;                   /* 플렉스 컨테이너로 설정 */
  justify-content: space-between;  /* 아이템 간의 간격을 고르게 분배 */
  align-items: center;             /* 아이템을 수직 가운데 정렬 */
}

.item {
  background-color: lightgreen;
  width: 100px;
  height: 100px;
}
```

* * *
<br>

### ❓ **CSS의 주요 속성**
<br><br>
#### 1️⃣ **텍스트 관련 속성**

* `color`: 텍스트 색상 지정
* `font-size`: 텍스트 크기 지정
* `font-family`: 글꼴 지정
* `font-weight`: 텍스트 두께(굵기) 지정
* `line-height`: 텍스트 줄 간격 지정
* `text-align`: 텍스트 정렬(예: left, center, right)
<br><br>
#### 2️⃣ **배경 관련 속성**

* `background-color`: 배경 색상
* `background-image`: 배경 이미지
* `background-position`: 배경 이미지의 위치
* `background-size`: 배경 이미지의 크기 조정
<br><br>
#### 3️⃣ **박스 모델 관련 속성**

* `margin`: 요소의 외부 여백
* `padding`: 요소의 내부 여백
* `border`: 요소의 테두리
* `width`, `height`: 요소의 너비와 높이
<br><br>
#### 4️⃣ **레이아웃 관련 속성**

* `display`: 요소의 표시 방식(예: block, inline, flex)
* `position`: 요소의 위치 지정(예: static, relative, absolute)
* `float`: 요소를 왼쪽 또는 오른쪽으로 띄우는 데 사용
* `clear`: 플로팅된 요소 주위의 공간을 조정
<br>

#### 5️⃣ **변환 및 애니메이션 관련 속성**

* `transform`: 요소를 이동, 회전, 크기 조정 등
* `transition`: 속성 변화의 애니메이션 효과
* `animation`: 복잡한 애니메이션 효과
　
* * *
<br>

<br><br>
### 💡 **결론**

> CSS는 웹 페이지의 시각적 스타일을 지정하는 데 필수적인 언어입니다. HTML로 구조를 만들고, CSS로 디자인을 정의하며,<br>
> 다양한 레이아웃 및 스타일 속성으로 웹 페이지를 더욱 매력적이고 기능적으로 만들 수 있습니다.<br>
> CSS의 기본 문법을 잘 이해하고, 이를 사용해 다양한 디자인을 구현할 수 있습니다.
