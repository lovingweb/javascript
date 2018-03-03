# Comparison operators

<p class="sub-title">비교 연산자</p>

두 피연산자 값의 관계를 검사하여 관계가 성립하면 참(true)을, 그렇지 않으면 거짓(false)을 반환한다.
관계형 표현식<sup>Relational Expressions</sup>은 항상 불리언 값으로 평가되고, 이 값은 프로그램 실행의 흐름을 제어하기 위한 if문, while문, for 루프문에서 주로 사용된다.

## 1. 일치 연산자 <sup>Equality Operators</sup>

자바스크립트는 strict 비교나, abstract(type-converting) 비교가 가능하다.

<dl>
    <dt>**strict 비교**</dt>
    <dd>만약 두 피연자가 같은 타입이 아니라면, 자라바스크립트가 두 피연산자를 비교하기에 적당한 타입으로 바꾼다. 만약 두 피연자가 객체라면, 자바스크립트가 내부 내용을 비교하여 두 피연자가 메모리의 같은 객체를 가리킨다면 두 객체를 같다고 한다.</dd>
    <dt>**abstract(type-converting) 비교**</dt>
    <dd>같음을 정의하는 매우 엄격하게 정의하여, 타입 변환없이 두 피연산자가 '일치(identical)'하는지 확인한다.</dd>
</dl>

|연산자|수행되는 연산|결합방향|피연산자 개수|피연산자 타입|반환|
|:---:|---|:---:|:---:|---|---|
|`==`|동등 연산자|`L->R`|2|타입 무방|Boolean|
|`!=`|부등 연산자|`L->R`|2|타입 무방|Boolean|
|`===`|일치 연산자|`L->R`|2|타입 무방|Boolean|
|`!==`|불일치 연산자|`L->R`|2|타입 무방|Boolean|

### 1.1 동등(동치) 연산자 <sup>Equality</sup>

`==`연산자는 피연산자들이 같다면 참(true)을 반환한다.

```js
1 == 1            // true
"1" == 1          // true
1 == '1'          // true
0 == false        // true
0 == null         // false
0 == undefined    // false
null == undefined // true
"1" == true       // true
(1<2) == 1        // true
```

### 1.2 부등(부등치) 연산자 <sup>Inquality</sup>

`!=`연산자는 피연산자들이 같지 않다면 참(true)을 반환한다.

```js
1 != 2      // true
1 != "1"    // false
1 != true   // false
0 != false  // false
```

### 1.3 일치 연산자 <sup>Identity / strict equality</sup>

`===`연산자는 피연산자들이 타입 변환 없이 strictly equal일 때를 말한다.

```js
3 === 3               // true
3 === '3'             // false
0 === -0              // true
(1<2) === 1           // false
(3<4) === (true == 1) // true
null == undefined     // false
```

### 1.4 불일치 연산자 <sup>Non-identity / strict equality</sup>

`!==`연산자는 같은 타입에서 값이 다르거나 다른 타입인 경우 참을 반환한다.

```js
3 !== '3' // true
4 !== 3   // true
```

## 2. 비교 연산자 <sup>Comparison Operators</sup>

비교 연산자는 두 피연산자 값의 상대적인 순서를 판단하는 데 쓰인다.

|연산자|수행되는 연산|결합방향|피연산자 개수|피연산자 타입|반환|
|:---:|---|:---:|:---:|---|---|
|`>`|크다|`L->R`|2|String, String / Number, Number|Boolean|
|`>=`|크거나 같다|`L->R`|2|String, String / Number, Number|Boolean|
|`<`|작다|`L->R`|2|String, String / Number, Number|Boolean|
|`<=`|작거나 같다|`L->R`|2|String, String / Number, Number|Boolean|

### 2.1 크다 연산자 <sup>Greater than</sup>

`>` 연산자는 만일 왼쪽 피연산자가 오른쪽 피연산자보다 클 경우 참으로 반환한다.

```js
4 > 3      // true
"4" > 3    // true
"4" > "3"  // true
"four" > 3 // false ("four"가 NaN으로 반환)
"a" < "b"  // true
```

### 2.2 크거나 같다 연산자 <sup>Greater than or equal</sup>

`>=`연산자는 만일 왼쪽 피연산자가 오른쪽 피연산자보다 크거나 동일할 경우 참으로 반환한다.

```js
4 >= 3 // true
3 >= 3 // true
```

### 2.3 작다 연산자 <sup>Less than</sup>

`<` 연산자는 왼쪽 피연산자가 오른쪽 피연산자보다 작을 경우에 참을 반환한다.

```js
3 < 4 // true
```

### 2.4 작거나 같다 연산자 <sup>Less than or equal</sup>

`<=` 연산자는 왼쪽 피연산자가 오른쪽 피연산자보다 작거나 동일할 경우에 참을 반환한다.

```js
3 <= 4 // true
```

비교연산자 사용법 설명.....

## 3. in 연산자

`in` 연산자는 명시된 속성이 명시된 객체에 존재하면 true를 반환한다.

|연산자|수행되는 연산|결합방향|피연산자 개수|피연산자 타입|반환|
|:---:|---|:---:|:---:|---|---|
|`in`|프로퍼티가 존재하는지 확인|`L->R`|2|String, Object|Boolean|

> prop in object

* prop : 속성의 이름이나 배열의 인덱스를 뜻하는 문자열 또는 수 값이다.
* object : 객체의 이름

좌변의 피연산자로 문자열을 받고 우변의 피연산자로는 객체나 배열을 받는다.

```js
var point = { x: 1, y: 1} // 객체 정의 및 초기화
"x" in point              // true (프로퍼티 x가 있다)
"z" in point              // false (프로퍼티 z가 없다)
"toString" in point       // true (상속된 프로퍼티)

var data = [7, 8, 9] // 배열 정의 및 초기화
"0" in data          // true (배열의 0번째 원소가 있다)
1 in data            // true (배열의 1번째 원소가 있다)
3 in data            // false (배열의 3번째 원소가 없다)
```

## 4. instanceof 연산자

`instanceof`연산자는 좌변의 피연산자로 객체를, 우변의 피연산자로 객체 클래스의 이름을 식별자로 받아서 좌변에 오는 객체가 우변 클래스의 인스턴스일 경우 연산 결과를 'true'로 그렇지 않은 경우에는 'false'로 평가한다.

|연산자|수행되는 연산|결합방향|피연산자 개수|피연산자 타입|반환|
|:---:|---|:---:|:---:|---|---|
|`instanceof`|객체 타입 확인|`L->R`|2|Object, 생성자|Boolean|

> object instanceof constructor

* object : 테스트 대상인 오브젝트
* constructor : 테스트할 함수

```js
var d = new Date()  // Date() 생성자로 새로운 객체를 생성한다
d instanceof Date   // true (d는 Date()에 의해 생성되었다)
d instanceof Object // true (모든 객체는 Object의 인스턴스)
d instanceof Number // false (d는 Number 의 객체가 아니다)

var a = [1, 2, 3]   // 배열 리터럴 문법으로 새로운 배열을 생성한다
a instanceof Array  // true (a는 배열이다)
a instanceof Object // true (모든 배열은 객체이다)
a instanceof RegExp // false (배열은 정규 표현식이 아니다)
```