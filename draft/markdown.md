---
title: Title
description: This is a short description of my page
---

# Arithmetic Operators


<p class="sub-title">리터럴과 변수, 상수, 데이터타입</p>

## 1. 이항 산술 연산자
* 기본적인 사칙연산 및 산술 연산이나 기타 수치 조작을 하는 연산자
* 산술 연산자는 2개의 숫자값(리터럴 또는 변수)을 피연산자로 갖는 이항 연산자이며, 하나의 숫자 값을 반환한다.
* 피연산자들의 결합 방법은 왼쪽에서 오른쪽(L->R)이다.

|연산자|수행되는 연산|결합방향|피연산자 개수|피연산자 타입|반환|
|:---:|---|---|---|---|---|
|`+`|덧셈 <sup>Addition</sup>|L->R|2|number, number|number|
|`+`|결합 <sup>concatenation</sup>|L->R|2|string, string|string|
|`-`|뺄셈 <sup>Subtraction</sup>|L->R|2|number, number|number|
|`*`|곱셈 <sup>Multiplication</sup>|L->R|2|number, number|number|
|`/`|나눗셈 <sup>Division</sup>|L->R|2|number, number|number|
|`%`|나머지 <sup>Modulus</sup>|L->R|2|number, number|number|

### 1.1 덧셈 연산자 (+)

배열<sup>eng</sup>
데이터타입 변환

변수 선언과 메모리의 확보<sub>ddd</sub>
{: .desc-img}

*This text will be italic*
_This will also be italic_

**This text will be bold**
__This will also be bold__

~~This text will be crossed out.~~

_You **can** combine them_

선언 단계(Declaration phase)
: **변수 객체(Variable Object)**에 변수를 등록한다. 이 변수 객체 `html`는 스코프가 참조하는 대상이 된다.

초기화 단계(Initialization phase)
: 변수 객체(Variable Object)에 등록된 변수를 메모리에 할당한다. 이 단계에서 변수는 `undefined`로 초기화된다.

할당 단계(Assignment phase)
: undefined로 초기화된 변수에 실제값을 할당한다.

<dl>
    <dt>선언 단계(Declaration phase)</dt>
    <dd><strong>변수 객체(Variable Object)</strong>에 변수를 등록한다. 이 변수 객체 `html` 는 스코프가 참조하는 대상이 된다.</dd>
    <dt>초기화 단계(Initialization phase)</dt>
    <dd><code>undefined</code>로 초기화된 변수에 실제값을 할당한다.</dd>
</dl>  


This is [an example](http://example.com/ "Title") inline link with a title.

[This link](http://example.net/) has no title attribute.

This is [an example][id] reference-style link.

[id]: http://example.com/  "Optional Title Here"


As Kanye West said:

> We're living the future so
> the present is our past.


<div>
Markdown here will not be **parsed**
</div>



Text prior to footnote reference.[^2]

[^2]: Comment to include in footnote.



```js
var = 10;
var textarea = document.getElementById('editor');
var editor = CodeMirror.fromTextArea(textarea, {
    lineNumbers: true,
    lineWrapping: true,
    theme: "oceanic-next",
    val: textarea.value
});
if(a == 10) {
// comments
}
```

```html
<button type="button" style="width: 100px;" class="test">tets</button>
```

```css
.test {
    width: 100px;
    content: 'test';
    background: url('/test/test.png') no-repeat 100% 100%;
}
```