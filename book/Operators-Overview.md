# Operators overview

<p class="sub-title">연산자 개요</p>

> 연산자는 식<sup>Expressions</sup>의 일부로 항상 하나의 값<sup>Value</sup>으로 귀결된다.

## 1. 피연산자의 개수

연산자에 필요한 피연산자의 개수에 따라 연산자들을 분류할 수 있다.

* 단항 연산자(unary operator) : 연산자 피연산자 또는 피연산자 연산자 (`A+B`, `A==B`, `A||B`)
* 이항 연산자(binary operator) : 피연산자1 연산자 피연산자2 (`A=B`, `-A`, `typeof A`)
* 삼항 연산자(ternary operator) : 조건부 연산자 하나가 존재한다. (`A?B:C`)

## 2. 피연산자와 변환 타입

일부 연산자는 값의 타입과 무관하게 작동하지만 대부분의 경우에는 피연산자의 타입이 정해져 있다.  
그리고 자바스크립트는 필요할 때마다 피연산자 타입을 변환한다.

```js
'3' * '5' // 15 (문자열 "15"가 아니라 숫자 15로 반환)
3 < '5'   // true
'3' < '5' // true
```

일부 연산자들은 피연산자의 타입에 따라 다르게 작동한다.

```js
3 + 5     // 8
'3' + '5' // "35"
"a" < "b" // true (문자열 알파벳 순서대로 비교를 수행한다)
```

## 3. 좌변 값

좌변 값은 할당(assignment)의 대상이며 '할당 표현식의 좌변에 나타날 수 있는 표현식'에서 유래한 용어이다.  
할당 연산자를 비롯한 몇 가지 연산자의 피연산자 타입은 '좌변 값(lvalue)'이다.  
자바스크립트에서는 변수, 객체 프로퍼티, 배열 원소가 좌변 값이다.

## 4. 연산자 부수 효과 <sup>Side effect</sup>

## 5. 연산자 우선순위 <sup>Operator Precedence</sup>

연산자 우선순위는 연산이 수행되는 순서를 제어하는 기준이 된다.
우선 순위가 높은 연산자는 상대적으로 우선순위가 낮은 연산자보다 먼저 수행된다.

```js
w = x + y * z; // (*) -> (+) -> (=)
```

원래 정해진 연산자 우선순위를 바꾸라면 명시적으로 괄호()를 쓰면 된다.

```js
w = (x + y) * z; // (+) -> (*) -> (=)
```

프로퍼티 접근이나 호추 표현식은 다른 연산자들보다 항상 우선순위가 높다.  
다음 코드에서 비록 `typeof`연산자가 우선순위가 높은 연산자 중 하나지만, 프로퍼티 접근돠 함수 호출이 끝난 후에야 실행된다.

```js
typeof my.function[x](y)
```

연산자 우선순위에 좀 더 알아보려면 [3.9 Operator precedence table](/book/Operator-Precedence-Table.md)와 [Operator precedence - JavaScript | MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_Precedence)를 참고하자.

## 6. 연산자 결합 방향 <sup>Associativity<sup>

연산자 결합 방향이 지정하는 것은 동일 우선순위 연산자들 간의 수행 순서를 의미한다.

왼쪽에서 오른쪽으로의 결합 방향(`L->R`)의 예제 코드.

```js
w = x - y - z;
w = ((x - y) - z);
```

오른쪽에서 왼쪽으로의 결합 방향(`R->L`)의 예제 코드.

```js
x = ~-y;
x = ~(-y);

w = x = y = z;
w = (x = (y = z));

q = a?b:c?d:e?f:g;
q = a?b:(c?d:(e?f:g));
```

## 7. 평가 순서