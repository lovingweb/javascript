# Conditionals

<p class="sub-title">조건문</p>

조건문 <sup>Conditional statement</sup>이란 특정한 조건(표현식의 값)에 따라 문을 실행하거나 건너뛴다.  
정확하게는 조건을 따지기보다는 주어진 값의 상태 <sup>Condition</sup>를 판단하는 문 <sup>Statement</sup>이라고 할 수 있겠다. 


* if : 기본적인 조건문
* switch : 정교한 방향으로 구문을 분기하는 조건문

## 1. if else

<pre class="syntax">
if(condition)
    statement
</pre>

`condition`은 '참' 또는 '거짓'으로 평가되는 표현식(한가지 값으로 수렴하는 식)이며, 그 값이 '참'이면 `statement`가 실행되고 '거짓'이면 `statement`가 실행되지 않는다.  
거짓으로 판정되는 6가지 값(`null`, `undefined`, `0`, `-0`, `NaN`, `""`)외에는 '참'으로 판정되는 값이므로 실제 코드를 작성할 때 '거짓'이 아니라면 실행된다라고 생각하는 편이 좀 더 명확할 수도 있다. 

```js
if(username == null)      // username이 null 또는 undefined일 때
	username = "John Doe" // 값을 정의한다.
```

또는 이와 유사하게 다음과 같이 사용할 수도 있다.

```js
// username이 null, undefined, false, 0, ''일 때 새 값을 정의한다.
if(!username)
	username = "John Doe"
```

다음과 같이 논리 연산자를 이용한 코드로 바꿀 수는 있지만 `username`이 '참'일 때도 평가해야므로 위의 `if`문 보다는 덜 효율적이다.

```js
username = username || "John Doe"
```

`if`문에는 `else`절<sup>clause</sup>을 포함할 수 있다. 이 절은 표현식의 값이 '거짓'일 때 실행된다.

<pre class="syntax">
if(condition)
    statement1
else
    statement2
</pre>

<p data-height="220" data-theme-id="32424" data-slug-hash="aYzZLV" data-default-tab="js,result" data-user="aroree" data-embed-version="2" data-pen-title="javascript : 홀수/짝수 판별" class="codepen">See the Pen <a href="https://codepen.io/aroree/pen/aYzZLV/">javascript : 홀수/짝수 판별</a> by aroree (<a href="https://codepen.io/aroree">@aroree</a>) on <a href="https://codepen.io">CodePen</a>.</p>
<script async src="https://static.codepen.io/assets/embed/ei.js"></script>

> `if`문은 식의 결과 값에 따라 실행을 안하는 경우도 있지만(선택적 <sup>Optional</sup>이지만) `if else`는 문 중에 하나는 무조건적 <sup>Mandatory</sup>으로 실행이 되기 때문에 각각 그 의도에 맞게 사용해야 한다. 

간단한 `if else`문은 다음과 같이 삼항 조건 연산자 또는 논리합 연산자를 사용해서 코드의 중복을 줄일 수도 있다. 

```js
// if문
if(a) b = a
else b = c

// 삼항 조건 연산자
b = a? a : c

// 논리합 연산자
b = a || c
```

<p data-height="200" data-theme-id="32424" data-slug-hash="mxyONK" data-default-tab="js,result" data-user="aroree" data-embed-version="2" data-pen-title="mxyONK" class="codepen">See the Pen <a href="https://codepen.io/aroree/pen/mxyONK/">mxyONK</a> by aroree (<a href="https://codepen.io/aroree">@aroree</a>) on <a href="https://codepen.io">CodePen</a>.</p>
<script async src="https://static.codepen.io/assets/embed/ei.js"></script>

`else`절은 기본적으로 가장 가까운 `if`문에 속하므로 잘못된 들여쓰기로 인한 오류에 주의해야 한다. (이를 방지하려면 중괄호를 사용하도록 하자)

```js
i = j = 1;
k = 2;

if(i == j)
  if(j == k)
    console.log("i와 k는 같다");
else
  console.log("i와 j는 같지 않다"); // i와 j는 같다!

// {}를 사용해서 혼란을 없애도록 한다.
if(i == j) {
  if(j == k)
    console.log("i와 k는 같다");
}
else {
  console.log("i와 j는 같지 않다"); // i와 j는 같다!
}
```

여러 조건(상태)을 분기할 때는 `else if`문을 사용할 수 있다.

<pre class="syntax">
if(condition1)
    statement1
else if(condition2)
    statement2
else if(condition3)
    statement3
...
else
    statementN
</pre>

사실 `if else`문과 들여쓰기의 차이일 뿐 자바스크립트에서 `else if`키워드는 존재하지 않는다.

<pre class="syntax">
if(condition1)
    statement1
else
    if(condition2)
        statement2
    else
        if(condition3)
            statement3
        else    
...
</pre>



> if(식) 문1 else 문2
> 식이 '거짓'이 아니라면 문1을 실행하고, '거짓'이라면 문2를 실행한다. 







## 2. switch


label 


https://programmers.co.kr/learn/challenge_codes/122/solutions