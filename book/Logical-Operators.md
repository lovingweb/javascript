# Logical operators

<p class="sub-title">논리 연산자</p>

논리 연산자는 불리언 대수 <sup>Boolean algebra</sup>를 수행한다. 비교 연산자와 함께 사용되어 둘 이상의 변수가 관계되는 복잡한 표현식을 표현하가도 한다.

`false`와 `false`로 변환되는 아래의 값들은 거짓으로 판정되는 <sup>falsy</sup> 값이라고 불리고, 그 밖의 모든 값들은 참<sup>truthy</sup> 으로 판정되는 값이라고 불린다.

* `undefined`
* `null`
* `NaN`
* `0`
* `-0`
* `""` : 빈 문자열 <sup>emppty string</sup>

|연산자|수행되는 연산|결합방향|피연산자 개수|피연산자 타입|반환|
|:---:|---|:---:|:---:|---|---|
|`&&`|논리 AND|L->R|2|타입 무방, 타입 무방|타입 무방|
|&#x007C;&#x007C;|논리 OR|L->R|2|타입 무방, 타입 무방|타입 무방|
|`!`|논리 NOT|R->L|1|Boolean|Boolean|

## 1. 논리 AND (A && B)

`&&`연산자는 첫 번째 피연산자와 두 번째 피연산자가 '모두' `true`일 경우에만 연산 결과로 `true`를 반환한다.  
적어도 하나 이상의 피연산자가 `false`라면 연산 결과로 `false`를 반환한다.

```js
true && true // true
true && false // false
false && true // false
false && 4 // false
true && 4 // 4
null && 3 // null
undefined && 3 // undefined
false && (3 == 4) // false
"Cat" && "Dog" // "Dog"
false && "Cat" // false
"Cat" && false // false
```

`&&` 연산자는 좌변에 있는 첫 번째 파연산자의 표현식을 먼저 평가하기 때문에 좌변의 값이 'falsy'이면 우변의 표현식은 평가하지 않는다.  
이를 단축 평가 <sup>Short-Circuit evaluation</sup>라고 부른다.

```js
var  o = {x : 3}
var p = null
o && o.x // 3 : o가 객체이기 때문에 o.x를 반환한다.
p && p.x // null : p가 null이기 때문에 p.x를 평가하지 않고 null을 반환한다.
```

다음은 이 같은 특성을 일부러 사용하는 코드의 예제이다.

```js
if (a == b) stop(); // a == b 를 만족할 때만 stop() 함수를 호출한다.
(a == b) && stop(); // 작동은 위와 같다.
```

## 2. 논리 OR (A || B)

`||`연산자는 두 피연산자가 '모두' `false`일 경우에만 연산 결과로 `false`를 반환한다.  
적어도 하나 이상의 피연산자가 `true`라면 연산 결과로 `true`를 반환한다.

```js
true || true // true
true || false // true
false || false // false
false || true // true
false || 3 // 3
false || (3 == 4) // false
"Cat" || "Dog" // "Cat"
"Cat" || false // "Cat"
```

`||`연산자는 좌변의 값이 `true`로 평가되는 값이면, 전체 표현식의 값은 바로 그 값이 된다.  
좌변의 값이 `false`로 평가되는 값이면, 연산자의 두 번째 피연산자를 평가하고, 이 값이 표현식의 값으로 반환된다.

```js
var max = max_width || preferences.max_width || 500;
```

1. `max_width`가 정의되어 있으면 이것을 사용한다.
2. 이 외의 경우 `preference`객체에 속한 값을 찾아본다.
3. 그것조차 정의되어 있지 않을 경우 하드 코딩된 상수를 사용한다. 

> * false && (anything) : false 단락으로 평가된다.
> * true || (anything) : true 단락으로 평가된다.

## 3. 논리 NOT (!A)

`!`연산자는 단항 연산자이며 단일 피연산자 앞에 놓인다.  
이 연산자의 목적은 피연산자의 불리언 값을 반전, 즉 반대로 바꾸는 것이다.

```js
!true // false
!false // true
!"Cat" // false
```

다음 두 표현식의 값은 동일하다. (불리언 대수)

```js
!(p && q) === !p || !q
!(p || q) === !p && !q
```

[Converting AND to OR 참고](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_Operators#Conversion_rules)