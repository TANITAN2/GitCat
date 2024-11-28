# **jQuery │ 기본 사용법 및 개념**

> **jQuery**는 자바스크립트 라이브러리로, HTML 문서의 조작, 이벤트 처리, 애니메이션, Ajax 요청 등을 쉽게 처리할 수 있도록 도와줍니다.<br>
> jQuery는 **간결하고 직관적인 문법**을 제공하여 자바스크립트의 복잡한 작업을 간단하게 처리할 수 있으며, 2006년에 출시되어 웹 개발에서 매우 널리 사용되었습니다.

* * *

## ❓ **jQuery 기본 개념**
<br>

* **DOM 조작**: HTML 요소를 선택하고 변경할 수 있는 기능을 제공합니다.
<br>

* **이벤트 처리**: 사용자의 클릭, 입력 등 이벤트를 쉽게 처리할 수 있습니다.
<br>

* **애니메이션**: 간단한 애니메이션 효과를 추가할 수 있습니다.
<br>

* **Ajax**: 서버와 비동기적으로 데이터를 주고받을 수 있습니다.
<br>

* **크로스 브라우저 호환성**: jQuery는 다양한 브라우저에서 동일한 방식으로 동작하도록 돕습니다.

<br>

* * *

## ❓ **jQuery 사용법**
<br>

#### 1️⃣ **jQuery 포함하기**
 
> jQuery를 사용하려면 먼저 HTML 문서에 jQuery 라이브러리를 포함해야 하며, 두 가지 방법이 있습니다.
<br>

1. **CDN 방식**(추천👍)

> jQuery 파일을 외부 서버에서 불러오는 방법으로 네트워크가 연결되어 있는 경우 빠르고, 최신 버전을 사용할 수 있습니다.

```html
<script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
```
<br>

2. **로컬 파일 사용**

> 다운로드한 jQuery 파일을 서버에 저장하고, 이를 문서에 포함하는 방법입니다.

```html
<script src="path/to/jquery-3.6.0.min.js"></script>
```
<br><br>

#### 2️⃣ **jQuery 선택자(Selector)**

> jQuery에서 가장 중요한 부분은 **선택자**입니다. 선택자를 사용하여 HTML 요소를 선택하고, 그 요소에 스타일, 이벤트 처리 등을 적용할 수 있습니다.
<br>

* **ID 선택자**: `#` 기호를 사용하여 ID로 선택.
```javascript
$('#myElement')
```
<br>

* **클래스 선택자**: `.` 기호를 사용하여 클래스명으로 선택.
```javascript
$('.myClass')
```
<br>

* **태그 선택자**: 태그명을 사용하여 선택.
```javascript
$('div')
```
<br>

* **자식 요소 선택**: 특정 요소의 자식 요소를 선택.
```javascript
$('ul > li')  // <ul>의 직속 <li> 자식 요소들
```
<br>

* **속성 선택자**: 특정 속성 값을 가진 요소 선택.
```javascript
$('[type="text"]')  // type 속성이 "text"인 요소들
```
<br><br>

#### 3️⃣ **DOM 조작(Manipulating DOM)**

> 선택한 HTML 요소에 대한 조작을 통해 내용을 변경하거나 스타일을 수정할 수 있습니다.
<br>

* **내용 변경**: `text()`, `html()` 메서드를 사용하여 요소의 텍스트나 HTML을 변경합니다.
```javascript
$('#myElement').text('새로운 텍스트');  // 텍스트 변경
$('#myElement').html('<strong>HTML</strong> 내용 변경');  // HTML 변경
```
<br>

* **스타일 변경**: `css()` 메서드를 사용하여 CSS 스타일을 동적으로 변경합니다.
```javascript
$('#myElement').css('color', 'red');  // 색상을 빨간색으로 변경
```
<br>

* **클래스 추가/제거**: `addClass()`, `removeClass()`, `toggleClass()` 메서드를 사용하여 요소에 클래스를 추가하거나 제거할 수 있습니다.
```javascript
$('#myElement').addClass('active');  // 클래스 추가
$('#myElement').removeClass('active');  // 클래스 제거
$('#myElement').toggleClass('active');  // 클래스 토글
```
<br>

* **요소 숨기기/보이기**: `hide()`, `show()`, `toggle()` 메서드를 사용하여 요소를 숨기거나 보일 수 있습니다.
```javascript
$('#myElement').hide();  // 숨기기
$('#myElement').show();  // 보이기
$('#myElement').toggle();  // 보이기/숨기기 토글
```
<br><br>

#### 4️⃣ **이벤트 처리(Event Handling)**

> jQuery는 다양한 이벤트를 처리할 수 있는 메서드를 제공합니다. `click()`, `hover()`, `keypress()` 등 여러 이벤트를 간편하게 처리할 수 있습니다.
<br>

* **클릭 이벤트**:
```javascript
$('#myButton').click(function() {
    alert('버튼이 클릭되었습니다!');
});
```
<br>

* **마우스 오버/아웃 이벤트**:
```javascript
$('#myElement').hover(function() {
    $(this).css('background-color', 'yellow');  // 마우스 오버 시 배경색 변경
}, function() {
    $(this).css('background-color', '');  // 마우스 아웃 시 원래대로 복원
});
```
<br>

* **폼 제출 이벤트**:
```javascript
$('form').submit(function(event) {
    event.preventDefault();  // 기본 제출 동작을 막음
    alert('폼이 제출되었습니다!');
});
```
<br><br>

#### 5️⃣ **애니메이션(Animation)**

> jQuery는 다양한 애니메이션 효과를 제공하여 동적인 사용자 인터페이스를 만들 수 있습니다.
<br>

* **슬라이드 업/다운**:
```javascript
$('#myElement').slideUp();  // 위로 숨기기
$('#myElement').slideDown();  // 아래로 펼치기
```
<br>

* **페이드 인/아웃**:
```javascript
$('#myElement').fadeIn();  // 서서히 보이게
$('#myElement').fadeOut();  // 서서히 숨기기
```
<br>

* **애니메이션 효과**:
```javascript
$('#myElement').animate({
    width: '300px',
    height: '200px'
}, 1000);  // 1000ms 동안 크기를 변경
```
<br>

* * *


## ❓ **Ajax 요청(AJAX Requests)**
<br>

> jQuery는 `$.ajax()` 메서드를 사용하여 서버와 비동기적으로 데이터를 주고받을 수 있게 합니다. 이를 통해 페이지를 새로 고침하지 않고도 데이터를 동적으로 가져오거나 보낼 수 있습니다.
<br>

#### 1️⃣ **GET 요청**:
```javascript
$.get('data.json', function(data) {
    console.log(data);  // 데이터를 받아서 처리
});
```
<br>

#### 2️⃣ **POST 요청**:
```javascript
$.post('submit.php', { name: 'John', age: 30 }, function(response) {
    console.log(response);  // 서버의 응답 처리
});
```
<br>

* * *


<br><br>
## 💡 **결론**

> jQuery는 자바스크립트의 복잡한 문법을 간소화하여 개발자가 빠르고 효율적으로 웹 페이지를 만들 수 있도록 도와주는 라이브러리입니다.<br>
다양한 기능을 제공하여 DOM 조작, 이벤트 처리, 애니메이션 효과, Ajax 요청 등을 쉽게 구현할 수 있습니다. 그러나 **모던 웹 개발**에서는 자바스크립트의 최신 기능들이 많이 사용되고 있으며, **React**, **Vue.js**와 같은 **프론트엔드 프레임워크**들이 주로 사용되고 있습니다. 그럼에도 불구하고, 기존의 프로젝트나 간단한 웹 개발에서는 여전히 jQuery가 유용하게 사용될 수 있습니다.
<br>

