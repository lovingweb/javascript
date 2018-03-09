# Conditionals

<p class="sub-title">조건문</p>

조건문 <sup>Conditional statement</sup>이란 특정한 조건(표현식의 값)에 따라 문을 실행하거나 건너뛴다.  
정확하게는 조건을 따지기보다는 주어진 값의 상태 <sup>Condition</sup>를 판단하는 문 <sup>Statement</sup>이라고 할 수 있겠다. 


* if : 기본적인 조건문
* switch : 정교한 방향으로 구문을 분기하는 조건문

## 1. if, else

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

다음과 같이 논리 연산자를 이용한 코드로 바꿀 수는 있지만 `username`이 '참'일 때도 평가해야므로 위의 if문 보다는 덜 효율적이다.

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

<!-- Codepen -->
<p data-height="300" data-theme-id="32424" data-slug-hash="aYzZLV" data-default-tab="js,result" data-user="aroree" data-embed-version="2" data-pen-title="javascript : 홀수/짝수 판별" class="codepen">See the Pen <a href="https://codepen.io/aroree/pen/aYzZLV/">javascript : 홀수/짝수 판별</a> by aroree (<a href="https://codepen.io/aroree">@aroree</a>) on <a href="https://codepen.io">CodePen</a>.</p>
<script async src="https://static.codepen.io/assets/embed/ei.js"></script>

```js
if(a) b = a
else b = c

b = a? a : c

b = a || c
```



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

> if(식) 문1 else 문2
> 식이 '거짓'이 아니라면 문1을 실행하고, '거짓'이라면 문2를 실행한다. 







## 2. switch


label 


https://programmers.co.kr/learn/challenge_codes/122/solutions