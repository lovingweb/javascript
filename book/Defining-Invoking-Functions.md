# Defining & invoking functions

<p class="sub-title">함수 정의 및 호출하기</p>

## 함수 정의하기

함수를 생성하는 방법은 다음의 3가지가 있다.

* 함수 선언문 (Function Declarations)
* 함수 표현식 (Function Expressions)
* Function() 생성자 함수

### 함수 리터럴

자바스크립트에서는 **함수도 값으로 취급**된다. 때문에 함수 리터럴을 이용해 함수를 생성할 수 있다. 실제로 함수 선언문이나 함수 표현식 모두 이런 함수 리터럴 방식을 이용한 것이다.

> 리터럴 <sup>Literal</sup>은 값을 만드는 방법이다. 자바스크립트는 사용자가 제공한 리터럴 값을 받아 데이터를 만든다.

<pre class="syntax">
function functionName(arg1, arg2, ... argN) {
    functionBody
}
</pre>

<dl>
    <dt><u>function 키워드</u></dt>
    <dd>자바스크립트 함수 리터럴은 <code>function</code>키워드로 시작한다.</dd>
    <dt><u>함수명</u></dt>
    <dd>함수를 구분하는 식별자 <sup>Identifier</sup>이다.<br>함수 이름은 곧 변수의 이름이며, 새로 정의된 함수 객체는 그 변수에 할당된다. 함수 표현식에서는 생략 가능하다.</dd>
    <dt><u>매개변수 목록</u></dt>
    <dd>0개 이상의 목록으로 쉼표<code>,</code>로 구분하며 괄호<code>()</code>로 묶는다.  자바스크립트는 매개변수 <sup>Parameter</sup>의 데이터 타입을 기술하지 않으므로 함수 몸체 내에서 타입 체크가 필요할 수 있다.</dd>
    <dt><u>함수 몸체</u></dt>
    <dd>자바스크립트 코드 블록. 함수가 호출될 때마다 실행되는 0개 이상의 구문들의 집합이며 중괄호<code>{}</code>로 묶는다.</dd>
</dl>

### 함수 선언문

함수 선언문 방식으로 선언된 함수는 반드시 함수명이 정의되어 있어야 한다.
<!-- 함수 선언문 <sup>Function Statement</sup>은 말 그대로 함수의 정의를 나타내는 '문'이다.  일반적인 프로그래밍 언어에서의 함수 선언과 비슷한 형식이다. Statement의 개념을 알고 있다면 이 함수 선언문의 코드 블록 자체는 실행 가능 코드가 아니라서 어떠한 결과도 `return` 되지 않는다는 것을 예상할 수 있다. (이러한 이유로 함수 선언문을 Class와 동일한 개념으로 이해해도 무방하다.) -->

```js
// add라는 이름의 함수를 선언
function add(x, y) { // x, y는 이 함수의 매개변수
    return x + y;
}
add(3, 11); // add() 함수에 인자로 3, 11을 전달하여 호출
```

위의 코드에서 함수 선언문으로 정의한 `add()`함수가 함수 이름으로 외부에서 호출이 가능한 이유는 자바스크립트 엔진에 의해 다음과 같은 함수 표현식 형태로 변경되기 때문이다. 함수 이름과 함수 변수의 이름이 같아서 함수 이름으로 함수가 호출되는 것처럼 보이지만, 실제로는 함수 변수로 함수 외부에서 호출이 가능하게 된 것이다.

```js
var add = function add(x, y) {
    return x + y;
};
```

### 함수 표현식

자바스크립트에서는 함수도 하나의 값처럼 취급된다고 했다. 이 말은 함수도 숫자나 문자열처럼 변수에 할당하는 것이 가능하다는 이야기다. 

함수 표현식은 함수 리터럴로 하나의 함수를 만들고, 여기서 생성된 함수를 변수에 할당하여 함수를 생성하는 방식이다. 이 때, 이 변수는 함수 리터럴로 생성한 함수를 참조하는 변수이지, 함수 이름은 아니다. 그러므로 함수 호출시 함수 이름이 아니라 함수를 가리키는 함수 변수를 사용해야 한다. 

함수 표현식으로 생성하는 함수는 함수 이름을 생략할 수 있는데, 이를 '익명 함수 <sup>Anonymous function</sup>'라고 한다.

다음의 코드에서 `add`와 `plus`함수 변수는 두 개의 인자를 더하는 동일한 익명 함수를 참조한다.

```js
// add() 함수 표현식
var add = function(x, y) { // add 
    return x + y;
};

// 함수 변수 add는 함수의 참조 값을 가지므로 또 다른 변수 plus에도 그 값을 그대로 할당 할 수 있다.
var plus = add;
add(3, 11); // 14
plus(3, 11); // 14
```

함수 이름이 포함된 함수 표현식을 '기명 함수 <sup>Named function</sup>' 표현식이라고 한다. 이 함수 표현식에서 사용된 함수 이름은 정의된 함수 내부에서 해당 함수를 재귀적으로 호출하거나, 디버거 등에서 함수를 구분할 때 사용된다. 따라서 아래의 코드와 같이 함수 외부에서 해당 함수를 호출하면 에러가 발생한다.

```js
var add = function sum(x, y) { // add 
    return x + y;
};

add(3, 11); // 14
sum(3, 11); // ReferenceError: sum is not defined 에러 발생
```
<!--
다음은 익명 함수를 정의하면서 그 함수의 주소값을 바로 인자로 전달하는 형태이다.
```js
o.func(function(x, y) {
    return x + y;
});
```

`()`를 이용하여 해석과 동시에 실행되는 함수를 만들수가 있는데 이를 자기호출함수 <sup>Self invoking function</sup>이라고 한다.
```js
var add = (function(x, y) {
    return x + y;
})(3, 11);
```
-->

### Function() 생성자 함수

자바스크립트의 함수도 `Function()`이라는 기본 내장 생성자 함수로부터 생성된 객체라고 볼 수 있다. 함수 선언문이나 함수 표현식 방식은 함수 리터럴 방식으로 함수를 생성하지만, 내부적으로는 `Function()`생성자 함수로 함수가 생성된다고 볼 수 있다.

<pre class="syntax">
new Function(arg1, arg2, ... argN, functionBody)
</pre>

* `arg1, arg2, ... argN` : 함수의 매개변수
* `functionBody` : 함수가 호출될 때 실행될 코드를 포함한 문자열

```js
var add = new Function('x', 'y', 'return x + y');
add(3, 11); // 14
```

`Function()`생성자 함수를 사용한 함수 생성 방법은 자주 사용되지 않는다.

### 함수 호이스팅

> 호이스팅 <sup>Hoisting</sup>이란 인터프리터가 자바스크립트 코드를 해석함에 있어서 글로벌 영역의 선언된 코드 블록을 최상의 스코프 <sup>Scope</sup>로 끌어올리는 것을 말한다.

글로벌 영역에 선언된 변수나 함수는 자바스크립트 엔진이 가장 최우선으로 해석한다. 즉 인터프리터가 코드를 해석하면서 코드 작성 순서에 상관없이 글로벌 영역에 선언된 문들을 먼저 수집하여 전역객체의 속성으로 등록시켜 두기 때문에 전역변수와 전역함수는 코드의 어떠한 위치에서도 실행이 가능하다. (단, 할당구문은 런타임 과정에 이루어지기 때문에 호이스팅되지 않는다.)

함수 선언문의 경우, 함수 선언의 위치와는 상관없이 함수 선언문 형태로 정의한 함수의 유효 범위는 코드의 맨 처음부터 시작하게 되는데, 이것을 함수 호이스팅 <sup>Function hoisting</sup>이라고 한다.

아래의 코드를 보면 함수 선언문의 경우 함수가 선언되기 전에 함수 호출이 가능하다는 것을 알 수 있다.

```js
var res = square(5); // 25

function square(number) {
  return number * number;
}
```

하지만, 함수 표현식의 경우는 변수에 함수 리터럴을 할당하는 구조이기 때문에 함수 호이스팅이 일어나지 않는다. 그래서 아래의 코드는 에러를 발생시킨다.

```js
var res = square(5); // TypeError: square is not a function

var square = function(number) {
  return number * number;
}
```

즉, 함수 선언문은 호이스팅에 영향을 받지만, 함수 표현식은 호이스팅에 영향을 받지 않는다.  
아래의 문제를 풀어보자.

<p data-height="260" data-theme-id="32424" data-slug-hash="YaGGjr" data-default-tab="js,result" data-user="aroree" data-embed-version="2" data-pen-title="YaGGjr" class="codepen">See the Pen <a href="https://codepen.io/aroree/pen/YaGGjr/">YaGGjr</a> by aroree (<a href="https://codepen.io/aroree">@aroree</a>) on <a href="https://codepen.io">CodePen</a>.</p>
<script async src="https://static.codepen.io/assets/embed/ei.js"></script>

<p data-height="260" data-theme-id="32424" data-slug-hash="qoaaQr" data-default-tab="js,result" data-user="aroree" data-embed-version="2" data-pen-title="qoaaQr" class="codepen">See the Pen <a href="https://codepen.io/aroree/pen/qoaaQr/">qoaaQr</a> by aroree (<a href="https://codepen.io/aroree">@aroree</a>) on <a href="https://codepen.io">CodePen</a>.</p>
<script async src="https://static.codepen.io/assets/embed/ei.js"></script>



## 함수 호출하기

함수를 정의했더라도 함수 몸체의 코드는 함수를 호출하지 않으면 실행되지 않는다. 자바스크립트 함수는 다음의 네 가지 방법으러 호출할 수 있다.

* 일반적인 함수 형태
* 메서드 형태
* 생성자
* `call()`과 `apply()`메서드를 통한 간접 호출