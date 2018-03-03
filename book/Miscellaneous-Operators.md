# Miscellaneous operators

<p class="sub-title">기타 연산자들</p>

## 1. 삼항 조건부 연산자 (?: ) <sup>Conditional (ternary) Operator</sup>

자바스크립트의 유일한 3항 연산자이다.

|연산자|수행되는 연산|결합방향|피연산자 개수|피연산자 타입|반환|
|:---:|---|:---:|:---:|---|---|
|`?:`|조건부 연산자|`R->L`|3|Boolean, 타입 무방, 타입 무방|타입 무방|

> `condition ? expr1 : expr2`

첫 번째 피연산자는 'true' 혹은 'false'로 평가되는 표현식을 사용할 수 있다.  
이 값이 'true'로 평가되면 두 번째 피연산자가 평가되고 그 값을 반환하고, 'false'로 평가되면 세 번째 파연산자가 평가되고 그 값을 반환한다.  

```js
var condition = true;
var result = condition ? 'true' : 'false'; //true
```
if문을 사용해서 비슷한 결과를 얻을 수 있지만 좀 더 편리하고 간결한 문법을 제공한다.

```js
// 조건부 연산자
greeting = "Hello " + (username ? nsername : "there");

// if문
greeting = "Hello ";
if(username) {
    greeting += username;
} else {
    greeting += "there";
}
```

`isMember`변수의 값을 기초로 다른 메시지를 보여주고자 한다면, 다음과 같이 표현할 수 있다.

```js
"The fee is " + (isMember ? "$2.00" : "$10.00");
```

조건에 따른 결과 값을 변수에 할당할 때도 사용할 수 있다.

```js
var elvisLives = Math.PI > 4 ? "Yep" : "Nope";
```

다중 삼항 평가도 가능하다.

```js
var firstCheck = false,
    secondCheck = false,
    access = firstCheck ? "Access denied" : secondCheck ? "Access denied" : "Access granted";
  
console.log( access ); // logs "Access granted"
```

다중 조건 if문과 같은 방식으로 여러 개의 조건을 사용할 수도 있다.

```js
var firstCheck = false,
    secondCheck = false,
    access = firstCheck ? "Access denied" : secondCheck ? "Access denied" : "Access granted";
  
console.log( access ); // logs "Access granted"
```

이 외에 다른 사용법들은 [Conditional (ternary) Operator - JavaScript | MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Conditional_Operator)를 참고하자.

## 2. typeof 연산자

`typeof`연산자는 피연산자의 데이터 타입 <sup>Data type</sup>을 가리키는 문자열을 반환한다.

|연산자|수행되는 연산|결합방향|피연산자 개수|피연산자 타입|반환|
|:---:|---|:---:|:---:|---|---|
|`typeof`|피연산자의 타입을 반환|`R->L`|1|타입 무방|String|

> typeof 피연산자

|x (type)| typeof x|
|---|---|
|Undefined|`"undefined"`|
|Null|`"object"`|
|Boolean (true or false)|`"boolean"`|
|Number (숫자 또는 NaN)|`"number"`|
|String (문자열)|`"string"`|
|Function object (함수)|`"function"`|
|Any other object (함수가 아닌 객체)|`"object"`|
|Host object (호스트 객체)|`"undefined"`, `"boolean"`, `"number"`, `"string"`을 제외한 구현부 정의 문자열|
|Symbol|`"symbol"`|

```js
// Numbers
typeof 37 === 'number';
typeof 3.14 === 'number';
typeof(42) === 'number';
typeof Math.LN2 === 'number';
typeof Infinity === 'number';
typeof NaN === 'number'; // Despite being "Not-A-Number"
typeof Number(1) === 'number'; // but never use this form!


// Strings
typeof '' === 'string';
typeof 'bla' === 'string';
typeof '1' === 'string'; // note that a number within a string is still typeof string
typeof (typeof 1) === 'string'; // typeof always returns a string
typeof String('abc') === 'string'; // but never use this form!


// Booleans
typeof true === 'boolean';
typeof false === 'boolean';
typeof Boolean(true) === 'boolean'; // but never use this form!


// Symbols
typeof Symbol() === 'symbol'
typeof Symbol('foo') === 'symbol'
typeof Symbol.iterator === 'symbol'


// Undefined
typeof undefined === 'undefined';
typeof declaredButUndefinedVariable === 'undefined';
typeof undeclaredVariable === 'undefined'; 


// Objects
typeof {a: 1} === 'object';

// use Array.isArray or Object.prototype.toString.call
// to differentiate regular objects from arrays
typeof [1, 2, 4] === 'object';

typeof new Date() === 'object';


// The following is confusing. Don't use!
typeof new Boolean(true) === 'object'; 
typeof new Number(1) === 'object'; 
typeof new String('abc') === 'object';

// This stands since the beginning of JavaScript
typeof null === 'object';


// Functions
typeof function() {} === 'function';
typeof class C {} === 'function';
typeof Math.sin === 'function';
```

## 3. delete 연산자

`delete`연산자는 단항 연산자이며, 피연산자로 지정된 객체 프로퍼티, 배열 원소 또는 변수의 삭제를 시도한다.  
피연산자가 좌변 값이 아니거나(이 때 연산자는 아무런 동작을 하지 않는다.) 삭제에 성공한다면 'true'를 반환, 아니면 'false'를 반환한다.

|연산자|수행되는 연산|결합방향|피연산자 개수|피연산자 타입|반환|
|:---:|---|:---:|:---:|---|---|
|`delete`|프로퍼티를 제거|`R->L`|1|좌변 값(lval)|Boolean|

> delete 피연산자

* 존재하지 않는 속성을 삭제하려고 하면 `delete`연산자는 어떠한 작업도 없이 'true'를 반환한다.
* 배열의 원소를 삭제하면 배열에 '빈 자리'가 생기고, 배열의 길이 자체는 달라지지 않는다.

```js
var o = { x: 1, y: 2}; // 변수를 정의하고 객체를 초기화
delete o.x             // true를 반환 (객체 프로퍼티 중 하나를 삭제)
delete o.z             // true를 반환 (객체에 존재하지 않는 프로퍼티를 삭제하려고 한다)
"x" in o               // false를 반환 (삭제한 프로퍼티는 존재하지 않는다)

var a = [1, 2, 3] // 배열을 정의하고 초기화
delete a[0];      // true (배열의 첫 번째 원소를 삭제)
0 in a            // false (첫 번째 원소는 존재하지 않는다)
a.length          // 3 (배열의 길이는 변하지 않는다)
a                 // [empty, 2, 3]
```

* 모든 변수나 프로퍼티를 삭제할 수는 없다.
    * 몇몇 내장 코어 프로퍼티나 클라이언트 측 프로퍼티는 삭제할 수 없다.
    * `var`문으로 선언한 사용자 정의 변수들도 삭제할 수 없다.
    * `function`문으로 정의한 함수와 함수 매개변수도 삭제할 수 없다.
* 단순히 객체와 속성과의 연결을 끊을 뿐 실제로 메모리에서 제거하는 것은 아니다.

```js
var o = {x:1, y:2} // 변수 정의 및 객체 초기화
delete o.x; // true (객체 프로퍼티 중 하나를 삭제)
typeof o.x; // "undefined" (존재하지 않은 프로퍼티)
delete o.x; // true (객체에 존재하지 않는 프로퍼티를 삭제하려고 한다)
delete o // false (선언된 변수는 삭제할 수 없다)
delete 1 // true (피연산자가 좌변 값이 아니면 삭제할 수 없다)

x = 1 // var 키워드를 사용하지 않고 암묵적으로 변수를 선언
delete x // true (이와 같은 변수는 삭제할수 있다)
x // 런타임 에러 (x는 삭제되었으므로 정의되지 않았다)

var y = 1
delete y // false
y // 1
```

## 4. void 연산자

`void`연산자는 피연산자를 무시하고 'undefined'를 반환한다.

|연산자|수행되는 연산|결합방향|피연산자 개수|피연산자 타입|반환|
|:---:|---|:---:|:---:|---|---|
|`void`|undefined 값을 반환|`R->L`|1|타입 무방|undefined|

> void 피연산자

표현식을 평가해야 하긴 하지만 반환 값이 'undefined'여야 하는 상황이 있다면 `void`연산자를 사용할 수 있겠지만, 실무에서 거의 사용되지 않는다.

다음 코드에서 `void`연산자를 사용한 이유는 바로 'undefined'를 얻기 위함이다. 즉 해당하는 링크가 정상적으로 동작하지 않게 만들기 위하여 이처럼 'undefined'를 사용한다고 보면 된다.

```html
<a href="javascript:void(0)">Do nothing.</a>
<a href="javascript:void window.open();">Open New Window</a>
```

## 5. 콤마 연산자 (,)

`,`연산자는 이항 연산자로 피연산자들은 어떤 타입도 될 수 있다.

|연산자|수행되는 연산|결합방향|피연산자 개수|피연산자 타입|반환|
|:---:|---|:---:|:---:|---|---|
|`,`|첫 번째 피연산자를 무시하고 두 번째 피연산자를 반환|`L->R`|2|타입 무방|타입 무방|

> expr1, expr2, expr3...

이 연산자는 왼쪽의 전달인자를 평가하고 오른쪽의 전달인자를 평가한 후, 오른쪽 전달인자의 값을 반환한다.

```js
i = 0, j = 1, k = 2;

//이는 다음 코드와 동일하다.
i = 0; j = 1; k = 2;
```

다음 예제를 보면, `a` 에 `b = 3` 의 값을 대입하고 있지만, `c = 4` 표현식은 또 다른 값을 대입하고 있기 떄문에 콘솔에서는 4를 반환한다.

```js
a = b = 3, c = 4; // 콘솔에는 4를 반환
console.log(a); // 3

x = (y = 5, z = 6); // 콘솔에는 6을 반환
console.log(x); // 6
```

`,`연산자는 for문의 루프 변수 선언부에서 보편적으로 쓰인다.  
아래 코드의 첫 번째 (,)는 var문 문법의 일부로 사용되었다.
두 번째 (,)는 콤마 연산자이다. 두 표현식 `i++`와 `j--`를 하나의 for 루프 구문으로 넣었다.

```js
for (var i = 0, j = 10; i < j; i++, j--) {
  console.log(i+j);
}

// 출력값
// 10
// 10
// 10
// 10
// 10
```