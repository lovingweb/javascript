# Conditionals

<p class="sub-title">조건문</p>

조건문이란 특정한 조건(표현식의 값)에 따라 문을 실행하거나 건너뛴다.

## 1. if

<pre class="syntax">
if(condition)
    statement
</pre>

`condition`은 '참' 또는 '거짓'으로 평가되는 표현식이며, 그 값이 '참'이면 `statement`가 실행되고 '거짓'이면 `statement`가 실행되지 않는다.  
거짓으로 판정되는 6가지 값(`null`, `undefined`, `0`, `-0`, `NaN`, `""`)외에는 '참'으로 판정되는 값이므로 실제 코드를 작성할 때 '거짓'이 아니라면 실행된다라고 생각하는 편이 좀 더 명확할 수도 있다. 

```js
if(username == null)      // username이 null 또는 undefined일 때
	username = "John Doe" // 값을 정의한다.
```

또는 이와 유사하게 다음과 같이 사용할 수도 있다.

```js
// // username이 null, undefined, false, 0, ''일 때 새 값을 정의한다.
if(!username)
	username = "John Doe"
```

<pre class="syntax">
if(condition)
    statement1
else
    statement2
</pre>



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