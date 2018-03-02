# Overview

<p class="sub-title">연산자 개요</p>

## 연산자 개요

연산자(Operators)는 하나 혹은 그 이상의 값을 하나의 값으로 만들 때 사용한다.
연산자<sup>Opearate</sup>는 식<sup>Expressions</sup>의 일부로 항상 하나의 값<sup>Value</sup>으로 귀결된다.

### 피연산자의 개수

연산자에 필요한 피연산자의 개수에 따라 연산자들을 분류할 수 있다.
* 단항 연산자(unary operator) : 연산자 피연산자 또는 피연산자 연산자 (A+B, A==B, A||B)
* 이항 연산자(binary operator) : 피연산자1 연산자 피연산자2 (A=B, -A, typeof A)
* 삼항 연산자(ternary operator) : 조건부 연산자 하나가 존재한다. A?B:C

### 좌변 값

좌변값은 할당(assignment)의 대상입니다.
할당 연산자를 비롯한 몇 가지 연산자의 피연산자 타입은 '좌변 값(lvalue)'이다.
좌변 값이란 '할당 표현식의 좌변에 나타날 수 있는 표현식'에서 유래한 용어이다.
자바스크립트에서는 변수, 객체 프로퍼티, 배열 원소가 좌변 값이다.

### 연산자 부수 효과 Side effect

### 연산자 우선순위 Operator Precedence

연산자 우선순위는 연산이 수행되는 순서를 제어하는 기준이 된다.
우선 순위가 높은 연산자는 상대적으로 우선순위가 낮은 연산자보다 먼저 수행된다.

```js
w = x + y * z;
```

원래 정해진 연산자 우선순위를 바꾸라면 명시적으로 괄호를 쓰면 된다.

```js
w = (x + y) * z;
```

프로퍼티 접근이나 호추 표현식은 연산자들보다 항상 우선순위가 높다.

```js
typeof my.function[x](y)
```

https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Operators/%EC%97%B0%EC%82%B0%EC%9E%90_%EC%9A%B0%EC%84%A0%EC%88%9C%EC%9C%84

### 연산자 결합 방향 Associativity

연산자 결합 방향이 지정하는 것은 동일 우선순위 연산자들 간의 수행 순서를 의미한다.

결합방향이 왼쪽에서 오른쪽으로 (L)

```js
w = x - y - z;
w = ((x - y) - z);
```

결합방향이 오른쪽에서 왼쪽으로 (R)

```js
x = ~-y;
x = ~(-y);

w = x = y = z;
w = (x = (y = z));

q = a?b:c?d:e?f:g;
q = a?b:(c?d:(e?f:g));
```

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_Precedence






### 평가 순서