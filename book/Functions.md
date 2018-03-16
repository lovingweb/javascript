# Functions

<p class="sub-title">함수</p>

함수는 한 번 정의하면 몇 번이든 실행할 수 있고 호출할 수 있는 코드 블록이다.


코드의 목적을 좀 더 알기 쉽게 하고 필요할 때 마다 재 사용할 수 있다.
프로그램의 동작을 작은 조각들로 분리하고 그 조각들이 명료하게 한 가지 일만 하게끔 한다.
유지 관리하는 것이 쉬워진다.

자바스크립트의 함수는 일급 객체로 코드 재용, 정보의 구성 및 은닉 등에 사용하는 모듈화의 근간이다.


## 함수 정의하기

함수는 `function` 키워드로 시작하며, 정의하는 방법은 다음의 방법들이 있다.

함수의 구성 요소

* 함수 이름(함수를 구분하는 식별자 <sup>Identifier</sup>) 
* 쉼표`,`로 구분된 함수의 매개변수 <sup>Parameter</sup> 목록을 괄호`()`로 묶는다.
* 0개 이상의 자바스크립트 문을 포함한 중괄호`{}`

함수를 정의하는 방법

* 함수 선언문 (Function Declarations)
* 함수 표현식 (Function Expressions)

### 함수 선언문

Function Statement라고도 하며 말 그대로 함수의 정의를 나타내는 '문'이다. Statement의 개념을 알고 있다면 이 함수 선언문의 코드 블록 자체는 실행 가능 코드가 아니라서 어떠한 결과도 `return` 되지 않는다는 것을 예상할 수 있다. (이러한 이유로 함수 선언문을 Class와 동일한 개념으로 이해해도 무방하다.)

<pre class="syntax">
function 함수명() {
    // 자바스크립트 코드
}
</pre>

![Function Declarations|test](images/function-declarations.png#test2)


### 함수 표현식

<pre class="syntax">
var 함수명 = function() {
    // 자바스크립트 코드
}
</pre>




