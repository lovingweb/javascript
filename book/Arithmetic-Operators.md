# Arithmetic operators

<p class="sub-title">산술 연산자</p>

## 1. 이항 산술 연산자

* 기본적인 사칙연산 및 산술 연산이나 기타 수치 조작을 하는 연산자
* 산술 연산자는 2개의 숫자값(리터럴 또는 변수)을 피연산자로 갖는 이항 연산자이며, 하나의 숫자 값을 반환한다.
* 피연산자들의 결합 방법은 왼쪽에서 오른쪽(L->R)이다.

|연산자|수행되는 연산|결합방향|피연산자 개수|피연산자 타입|반환|
|:---:|---|:---:|:---:|---|---|
|`+`|덧셈|L->R|2|number, number|number|
|`+`|결합|L->R|2|string, string|string|
|`-`|뺄셈|L->R|2|number, number|number|
|`*`|곱셈|L->R|2|number, number|number|
|`/`|나눗셈|L->R|2|number, number|number|
|`%`|나머지|L->R|2|number, number|number|

### 1.1 덧셈 연산자 (+) <sup>Addition / Concatenation</sup>

`+`연산자가 이항 연산자로 사용될 때는 파연산자 숫자 값을 더하거나 문자열을 합친 값을 반환한다.  
두 피연산자 값이 모두 숫자거나 문자열인 경우에는 `+`연산자가 하는 일이 명확하다.

```js
// Number + Number -> addition
1 + 2 // 3

// String + String -> concatenation
"foo" + "bar" // "foobar"
```

하지만 이 외의 경우에는 타입 변환이 이루어져야 하고, 연산은 타입 변환이 이루어진 후에 수행된다.  
피연산자 중 하나가 문자열이거나 문자열로 바꿀 수 있는 객체라면 다른 피연산자를 문자열로 변환한 후 두 문자열을 이어 붙인다.  

```js
// String + Number -> concatenation
"1" + 2 // "12"

// Number + String -> concatenation
5 + "foo" // "5foo"

// Boolean + Number -> addition
true + 1 // 2

// Boolean + Boolean -> addition
false + false // 0

// String + Boolean -> concatenation
"foo" + false // "foofalse"

// Number + object -> Number
2 + null // 2

// Number + undefined -> NaN
2 + undefined // NaN
```

`+`연산자는 여러 문자열과 여러 숫자를 함께 사용할 때 실행된 순서에 따라 연산 결과가 달라질 수 있다. (결합법칙이 적용되지 않는다.)

```js
1 + 2 + "장 주세요"   // "3장 주세요"
1 + (2 + "장 주세요") // "12장 주세요"
```

### 1.2 뺄셈 연산자 (-) <sup>Subtraction</sup>

`-` 연산자는 두 개의 피연산자를 뺀 값을 반환한다.

```js
5 - 3       // 2
3 - 5       // -2
"foo" - "f" // NaN
"foo" - 3   // NaN
```

### 1.3 곱셈 연산자 (*) <sup>Multiplication</sup>

`*` 연산자는 두 개의 피연산자를 곱한 값을 반환한다.

```js
2 * 2               // 4
-2 * 2              // -4
"3" * 4             // 12
"foo" * 2           // NaN
Infinity * 0        // NaN
Infinity * 2        // Infinity
Infinity * Infinity // Infinity

```

### 1.4 나눗셈 연산자 (/) <sup>Division</sup>

`/` 연산자는 왼쪽 피연산자의 값을 오른쪽 피연산자의 값으로 나눈 몫을 반환한다.

```js
1 / 2      // 0.5
1.0 / 2.0  // 0.5

2.0 / 0    // returns Infinity in JavaScript
2.0 / 0.0  // returns Infinity too
2.0 / -0.0 // returns -Infinity in JavaScript
```

### 1.5 나머지 연산자 (%) <sup>Modulus</sup>

`%` 연산자는 하나의 피연산자가 두 번째 피연산자로 나누어질 때 남은 부분값을 반환한다.

```js
8 % 5 // 3
-1 % 2 // -1
NaN % 2 // NaN
-4 % 2 // -0
5.5 % 2 // 1.5
```

## 2. 단항 산술 연산자

|연산자|수행되는 연산|결합방향|피연산자 개수|피연산자 타입|반환|
|:---:|---|:---:|:---:|---|---|
|`+`|숫자화 연산자|R->L|1|number|number|
|`-`|단항 부정 연산자|R->L|1|number|number|
|`x++`|후치 증가|없음|1|좌변 값(lval)|number|
|`x--`|후치 감소|없음|1|좌변 값(lval)|number|
|`++x`|전치 증가|R->L|1|좌변 값(lval)|number|
|`--x`|전치 감소|R->L|1|좌변 값(lval)|number|

### 2.1 단항 덧셈 연산자 (+) <sup>Unary plus</sup>

단항 덧셈 연산자는 피연산자를 숫자(또는 NaN)로 바꾼 후 값을 반환한다.  
만일 피연산자가 숫자인 경우에는 아무 일도 하지 않는다.

```js
+3     // 3
+"3"   // 3
+true  // 1
+false // 0
+null  // 0
```

### 2.2 단항 뺄셈 연산자 (-) <sup>Unary negation</sup>

단항 부정 연산자는 그것의 피연산자보다 앞에 위치하여 음수로 만든다.

```js
var x = 3;
y = -x; // y = -3, x = 3
```

### 2.3 증가 연산자 (++) <sup>Increment</sup>

`++`연산자는 단항 피연산자에 대해 증가 연산을 한다. (즉, 1을 더한다.)  
이때 피연산자는 반드시 좌변 값(변수, 배열 원소 또는 객체 프로퍼티 중 하나)이어야 한다.  

* `++x` : 먼저 피연산자의 값을 1 증가시킨 후에 해당 연산을 수행한다. (피연산자에 1을 더한 값을 반환)
* `x++` : 먼저 해당 연산을 수행하고 나서, 피연산자의 값을 1 증가시킨다. (피연산자에 1을 더하기 전 값을 반환)

좌변 값이 숫자가 아닐 경우는 일단 이를 숫자 타입으로 변환하고, 거기에 1을 더한 다음, 원래 변수나 원소, 프로퍼티에 대입한다.

```js
// Prefix
var a = 2;
b = ++a; // a = 3, b = 3

// Postfix 
var x = 3;
y = x++; // y = 3, x = 4
```

표현식 `++X`는 `x=x+1`의 의미가 아니다.

```js
a = "1";
b = a + 1; // b = "11"

x = "1";
y = ++x; // y = 2
```

### 2.4 감소 연산자 (--) <sup>Decrement</sup>

* `--x` : 먼저 피연산자의 값을 1 감소시킨 후에 해당 연산을 수행한다. (피연산자에 1을 뺀 값을 반환)
* `x--` : 먼저 해당 연산을 수행하고 나서, 피연산자의 값을 1 감소시킨다. (피연산자에 1을 빼기 전 값을 반환)

```js
// Prefix
var a = 2;
b = --a; // a = 1, b = 1

// Postfix 
var x = 3;
y = x--; // y = 3, x = 2
```

증감 연산자는 해당 연산자가 피연산자의 어느 쪽에 위치하는가에 따라 연산의 순서 및 결과가 달라진다.

```js
var x = 10;
var y = x-- + 5 + --x;
```