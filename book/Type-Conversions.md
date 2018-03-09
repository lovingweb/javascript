# Type conversions

<p class="sub-title">타입 변환</p>

자바스크립트는 타입에 대해 매우 유연한 언어라서, 필요에 따라 적절한 타입을 지정하게 된다.

## 1. 암시적 타입 변환 <sup>Implicit type conversion</sup>

자바스크립트는 특정 타입의 값을 기대하는 곳에 다른 타입의 값이 오면, 자동으로 타입을 변환하여 사용한다.  
만약에 의미 있는 변환을 할 수 없다면 `NaN`으로 변환될 것이다.

```js
10 + " objects"  // "10 objects"
"7" * "4"        // 28
5 + null         // 5
1 * ""           // 0
var n = 1 - "x"  // NaN
n + " objects"   // "NaN objects"
```

동치 연산자(`==`)도 유연하게 동작한다. 다음의 동등 비교 예제들은 모두 'true'값을 반환한다.  
(참고로 엄격한 동치 연산자(`===`)는 타입 변환을 수행하지 않는다.)

```js
null == undefined // 이 두 값은 같다고 판단된다.
"0" == 0          // 비교하기 전에 숫자로 변환한다.
0 == false        // 불리언은 비교하기 전에 숫자로 변환한다.
"0" == false      // 두 피연산자는 비교하기 전에 숫자로 변환한다.
```

## 2. 명시적 타입 변환 <sup>Explicit type conversion</sup>

명시적으로 타입 변환을 수행하는 가장 간단한 방법은 `Boolean()`, `Number()`, `String()`, `Object()`함수를 사용하는 것이다.

```js
Number("3")   // 3
String(false) // "false"
Boolean([])   // true
Object(3)     // Number {3}
```

몇몇 연산자는 암시적 타입 변환을 수행하므로 종종 타입 변환 목적으로 사용된다.  
그래서 나온 것이 다음과 같은 타입 변환 숙어들이다.
```js
x + "" // Stirng(x)와 같다.
+x     // Number(X)와 같다.
!!x    // Boolean(X)와 같다.
```

### 2.1 숫자로 변환

문자열을 숫자로 변환하는 가장 간단한 방법은 `Number()`함수(객체 생성자)를 사용하는 것이다.  
숫자로 바꿀 수 없는 문자열에서는 `NaN`이 반환된다.

```js
Number("3")       // 3
Number(true)      // 1
Number(false)     // 0
Number(undefined) // NaN
Number(null)      // 0
Number("a")       // NaN
```

`Number()`함수는 10진수 정수만 처리할 수 있고 그 뒤에 숫자 아닌 문자가 오는 것을 허용하지 않는다. 
이 때는 `parseInt()`와 `parseFloat()` 내장 함수를 사용하면 된다.

* `parseInt(string, radix)` : 문자열을 파싱하여 특정 진법의 정수를 반환한다.
* `parseFloat(value)` : 문자열을 파싱하여 부동 소수점 수를 반환한다.

```js
parseInt("123.456")     // 123
parseInt("3.14 meters") // 3
parseInt(-12.34)        // -12
parseInt(".1")          // NaN ("."으로 시작할 수 없다)
parseInt("0.1")         // 0
parseInt("$72.47")      // NaN ("$"으로 시작할 수 없다)
parseInt("0xFF")        // 255
parseInt("a12")         // NaN
parseInt("05")          // 5
parseInt("F")           // NaN
parseInt("F", 16)       // 15
parseInt("3*5")         // 3
```

```js
parseFloat("123.456")     // 123.456
parseFloat("3.14 meters") // 3.14
parseFloat("05")          // 5
parseFloat("0xFF")        // 255
parseFloat('314e-2')      // 3.14
parseFloat('0.0314E+2')   // 3.14

```

암시적 타입 변환을 이용하여 1을 곱하거나 0을 빼는 연산을 통해 숫자로 변환할 수 있다.

```js
var str = "2" // "string"
str *= 1      // 2
typeof str    // "number"

str = "2"     // "string"
str -= 0      // 2
typeof str    // "number"
```

단항 연산자  `+`, `-`를 사용하여 숫자로 변환할 수도 있다.
```js
var str = "2" // "string"
str = +str    // 2
typeof str    // "number"

-"3"   // -3 "number"
+true  // 1 "number"
+null  // 0 "number"
-null  // -0 "number"
```

Boolean값을 숫자 '1'이나 '0'으로 바꿔야 할 때는 조건 연산자(`A?B:C`)를 사용할 수 있다.

```js
var b = true
var n = b ? 1 : 0 // n의 값은 1로 반환된다
typeof n          // "number"
```

* [문자를 숫자로 바꾸는 가장 좋은 방법은 무엇일까?](http://programmingsummaries.tistory.com/355)
* [문자 ↔ 숫자 타입 변환 방법 / 성능 분석](http://itmining.tistory.com/71)

### 2.2 문자열로 변환

`String()`과 `toString()`함수를 사용하여 문자열로 타입 변환을 할 수 있다.

```js
String(2)         // "2"
String(true)      // "true"
String(undefined) // "undefined"
String(null)      // "null"
```

`toString()`함수는 다음 예제 코드처럼 인자로 기수 <sup>radix</sup>를 선택할 수 있다. 인자를 전달하지 않는다면 10으로 변환을 진행한다.

```js
(123).toString() // "123"
(100+23).toString() // "123"
(123).toString(2) // "1111011" (2진법으로 변환)
(123).toString(16) // "7b" (16진법으로 변환)
```

Number클래스는 소수점 이하 자릿수나 지수 표기법을 사용하고 싶을 때를 위해서 다음과 같은 메서드를 제공한다.

* `toFixed()` : 문자열의 소수점 이하 자릿 수 개수를 인자와 똑같이 맞춘 문자열을 반환한다.
* `toExponential()` : 지수 표기법을 사용하여 소수점 앞에 숫자 하나와 소수점 뒤에 인자로 지정한 만큼의 자릿수를 놓는 방식으로 문자열을 반환한다.
* `toPrecision()` : 사용자가 정의한 유효 자릿수로 숫자를 문자열로 반환한다.

```js
(123456.789).toFixed()        // "123457"
(123456.789).toFixed(0)       // "123457"
(123456.789).toFixed(2)       // "123456.79"
(123456.789).toFixed(5)       // "123456.78900"
(123456.789).toExponential()  // "1.23456789e+5"
(123456.789).toExponential(1) // "1.2e+5"
(123456.789).toExponential(3) // "1.235e+5"
(123456.789).toPrecision()    // "123456.789"
(123456.789).toPrecision(4)   // "1.235e+5"
(123456.789).toPrecision(7)   // "123456.8"
(123456.789).toPrecision(10)  // "123456.7890"
```

문자열 결합 연산자(`+`)와 빈문자("")를 사용해서 간단하게 문자열로 변환할 수 있다.

```js
var num = 2 // "number"
num += ""   // "2"
typeof num  // "string"
```

### 2.3 Boolean으로 변환

Boolean Data Type이 가장 요긴하게 사용되는 곳은 if문이다.  
다음은 기타 데이터 타입을 Boolean값으로 변환하는 규칙이다.

* `null`과 `undefined` 값은 `false`가 된다.
* 숫자 0(-0)과 `NaN`은 `false`가 된다.
* 빈 문자열''은 `false`가 된다.
* 그 외의 모든 값은 `true`가 된다.

그러므로 다음 코드에서 거짓으로 판정되는 6가지 값(`null`, `undefined`, `0`, `-0`, `NaN`, `""`)외에는 모두 'true'이다.

```js
Boolean(0)         // false
Boolean(-0)        // false
Boolean(NaN)       // false
Boolean("")        // false
Boolean(null)      // false
Boolean(undefined) // false
```

부정 연산자(`!`)를 써서 모든 값을 Boolean으로 변환할 수 있다.

## 3. 객체에서 원시 타입으로 변환

모든 객체는 두 개의 타입 변환 메서드를 상속한다.

* `toString()` : 객체를 문자열로 표현하여 반환한다.
* `valueOf()` : 기본적으로 원시 타입을 반환하지 않고 단순히 객체 그 자신을 반환한다.