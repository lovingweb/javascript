# Operator precedence table

<p class="sub-title">연산자 우선순위 표</p>

<table>
    <colgroup>
        <col style="width: 8%;">
        <col style="width: 10%;">
        <col style="width: auto;">
        <col style="width: 12%;">
        <col style="width: 8%;">
        <col style="width: 15%;">
        <col style="width: 10%;">
    </colgroup>
    <thead>
        <tr>
            <th scope="col">우선순위</th>
            <th scope="col">연산자</th>
            <th scope="col">수행되는 연산</th>
            <th scope="col">결합방향</th>
            <th scope="col">피연산자 개수</th>
            <th scope="col">피연산자 타입</th>
            <th scope="col">반환</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td class="center">19</td>
            <td><code>()</code></td>
            <td>묶음(괄호)</td>
            <td class="center">없음</td>
            <td class="center"></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td class="center" rowspan="3">18</td>
            <td><code>.</code></td>
            <td>멤버 접근</td>
            <td class="center"><code>L->R</code></td>
            <td class="center"></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td><code>[]</code></td>
            <td>연산된 멤버 접근</td>
            <td class="center"><code>L->R</code></td>
            <td class="center"></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td><code>new ... ()</code></td>
            <td>객체 생성(인수 목록 있음)</td>
            <td class="center">없음</td>
            <td class="center"></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td class="center" rowspan="2">17</td>
            <td><code>...()</code></td>
            <td>함수 호출</td>
            <td class="center"><code>L->R</code></td>
            <td class="center"></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td><code>new</code></td>
            <td>객체 생성(인수 목록 없음)</td>
            <td class="center"><code>R->L</code></td>
            <td class="center"></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td class="center" rowspan="2">16</td>
            <td><code>x++</code></td>
            <td>후치 증가</td>
            <td class="center">없음</td>
            <td class="center">1</td>
            <td>좌변 값(lval)</td>
            <td>Number</td>
        </tr>
        <tr>
            <td><code>x--</code></td>
            <td>후치 감소</td>
            <td class="center">없음</td>
            <td class="center">1</td>
            <td>좌변 값(lval)</td>
            <td>Number</td>
        </tr>
        <tr>
            <td class="center" rowspan="9">15</td>
            <td><code>++x</code></td>
            <td>전치 증가</td>
            <td class="center"><code>R->L</code></td>
            <td class="center">1</td>
            <td>좌변 값(lval)</td>
            <td>Number</td>
        </tr>
        <tr>
            <td><code>--x</code></td>
            <td>전치 감소</td>
            <td class="center"><code>R->L</code></td>
            <td class="center">1</td>
            <td>좌변 값(lval)</td>
            <td>Number</td>
        </tr>
        <tr>
            <td><code>-</code></td>
            <td>단항 부정 연산자</td>
            <td class="center"><code>R->L</code></td>
            <td class="center">1</td>
            <td>Number</td>
            <td>Number</td>
        </tr>
        <tr>
            <td><code>+</code></td>
            <td>숫자화 연산자</td>
            <td class="center"><code>R->L</code></td>
            <td class="center">1</td>
            <td>Number</td>
            <td>Number</td>
        </tr>
        <tr>
            <td><code>~</code></td>
            <td>비트 단위 NOT</td>
            <td class="center"><code>R->L</code></td>
            <td class="center">1</td>
            <td>정수</td>
            <td>정수</td>
        </tr>
        <tr>
            <td><code>!</code></td>
            <td>논리 NOT</td>
            <td class="center"><code>R->L</code></td>
            <td class="center">1</td>
            <td>Boolean</td>
            <td>Boolean</td>
        </tr>
        <tr>
            <td><code>typeof</code></td>
            <td>피연산자의 타입을 반환</td>
            <td class="center"><code>R->L</code></td>
            <td class="center">1</td>
            <td>타입 무방</td>
            <td>String</td>
        </tr>
        <tr>
            <td><code>delete</code></td>
            <td>프로퍼티를 제거</td>
            <td class="center"><code>R->L</code></td>
            <td class="center">1</td>
            <td>좌변 값(lval)</td>
            <td>Boolean</td>
        </tr>
        <tr>
            <td><code>void</code></td>
            <td>undefined 값을 반환</td>
            <td class="center"><code>R->L</code></td>
            <td class="center">1</td>
            <td>타입 무방</td>
            <td>undefined</td>
        </tr>
        <tr>
            <td class="center" rowspan="3">14</td>
            <td><code>*</code></td>
            <td>곱셈</td>
            <td class="center"><code>L->R</code></td>
            <td class="center">2</td>
            <td>Number, Number</td>
            <td>Number</td>
        </tr>
        <tr>
            <td><code>/</code></td>
            <td>나눗셈</td>
            <td class="center"><code>L->R</code></td>
            <td class="center">2</td>
            <td>Number, Number</td>
            <td>Number</td>
        </tr>
        <tr>
            <td><code>%</code></td>
            <td>나머지</td>
            <td class="center"><code>L->R</code></td>
            <td class="center">2</td>
            <td>Number, Number</td>
            <td>Number</td>
        </tr>
        <tr>
            <td class="center" rowspan="3">13</td>
            <td><code>+</code></td>
            <td>덧셈</td>
            <td class="center"><code>L->R</code></td>
            <td class="center">2</td>
            <td>Number, Number</td>
            <td>Number</td>
        </tr>
        <tr>
            <td><code>+</code></td>
            <td>결합</td>
            <td class="center"><code>L->R</code></td>
            <td class="center">2</td>
            <td>String, String</td>
            <td>String</td>
        </tr>
        <tr>
            <td><code>-</code></td>
            <td>뺄셈</td>
            <td class="center"><code>L->R</code></td>
            <td class="center">2</td>
            <td>Number, Number</td>
            <td>Number</td>
        </tr>
        <tr>
            <td class="center" rowspan="3">12</td>
            <td><code><<</code></td>
            <td>왼쪽으로 이동</td>
            <td class="center"><code>L->R</code></td>
            <td class="center">2</td>
            <td>정수</td>
            <td>정수</td>
        </tr>
        <tr>
            <td><code>>></code></td>
            <td>부호 비트를 확장하면서 오른쪽으로 이동</td>
            <td class="center"><code>L->R</code></td>
            <td class="center">2</td>
            <td>정수</td>
            <td>정수</td>
        </tr>
        <tr>
            <td><code>>></code></td>
            <td>부호 비트 확장 없이 오른쪽으로 이동</td>
            <td class="center"><code>L->R</code></td>
            <td class="center">2</td>
            <td>정수</td>
            <td>정수</td>
        </tr>
        <tr>
            <td class="center" rowspan="4">11</td>
            <td><code>&lt;, &lt;=, &gt;, &gt;=</code></td>
            <td>숫자를 비교</td>
            <td class="center"><code>L->R</code></td>
            <td class="center">2</td>
            <td>Number, Number</td>
            <td>Boolean</td>
        </tr>
        <tr>
            <td><code>&lt;, &lt;=, &gt;, &gt;=</code></td>
            <td>문자열을 알파벳 순서로 비교</td>
            <td class="center"><code>L->R</code></td>
            <td class="center">2</td>
            <td>String, String</td>
            <td>Boolean</td>
        </tr>
        <tr>
            <td><code>instanceof</code></td>
            <td>객체 타입 확인</td>
            <td class="center"><code>L->R</code></td>
            <td class="center">2</td>
            <td>Object, 생성자</td>
            <td>Boolean</td>
        </tr>
        <tr>
            <td><code>in</code></td>
            <td>프로퍼티가 존재하는지 확인</td>
            <td class="center"><code>L->R</code></td>
            <td class="center">2</td>
            <td>String, Object</td>
            <td>Boolean</td>
        </tr>
        <tr>
            <td class="center" rowspan="4">10</td>
            <td><code>==</code></td>
            <td>동등 연산자</td>
            <td class="center"><code>L->R</code></td>
            <td class="center">2</td>
            <td>타입 무방</td>
            <td>Boolean</td>
        </tr>
        <tr>
            <td><code>!=</code></td>
            <td>부등 연산자</td>
            <td class="center"><code>L->R</code></td>
            <td class="center">2</td>
            <td>타입 무방</td>
            <td>Boolean</td>
        </tr>
        <tr>
            <td><code>===</code></td>
            <td>일치 연산자</td>
            <td class="center"><code>L->R</code></td>
            <td class="center">2</td>
            <td>타입 무방</td>
            <td>Boolean</td>
        </tr>
        <tr>
            <td><code>!==</code></td>
            <td>불일치 연산자</td>
            <td class="center"><code>L->R</code></td>
            <td class="center">2</td>
            <td>타입 무방</td>
            <td>Boolean</td>
        </tr>
        <tr>
            <td class="center">9</td>
            <td><code>&</code></td>
            <td>비트 단위 AND</td>
            <td class="center"><code>L->R</code></td>
            <td class="center">2</td>
            <td>정수</td>
            <td>정수</td>
        </tr>
        <tr>
            <td class="center">8</td>
            <td><code>^</code></td>
            <td>비트 단위 XOR</td>
            <td class="center"><code>L->R</code></td>
            <td class="center">2</td>
            <td>정수</td>
            <td>정수</td>
        </tr>
        <tr>
            <td class="center">7</td>
            <td><code>|</code></td>
            <td>비트 단위 OR</td>
            <td class="center"><code>L->R</code></td>
            <td class="center">2</td>
            <td>Number, Number</td>
            <td>Number</td>
        </tr>
        <tr>
            <td class="center">6</td>
            <td><code>&&</code></td>
            <td>논리 AND</td>
            <td class="center"><code>L->R</code></td>
            <td class="center">2</td>
            <td>타입 무방, 타입 무방</td>
            <td>타입 무방</td>
        </tr>
        <tr>
            <td class="center">5</td>
            <td><code>||</code></td>
            <td>논리 OR</td>
            <td class="center"><code>L->R</code></td>
            <td class="center">2</td>
            <td>타입 무방, 타입 무방</td>
            <td>타입 무방</td>
        </tr>
        <tr>
            <td class="center">4</td>
            <td><code>?:</code></td>
            <td>조건부 연산자</td>
            <td class="center"><code>R->L</code></td>
            <td class="center">3</td>
            <td>Boolean, 타입 무방, 타입 무방</td>
            <td>타입 무방</td>
        </tr>
        <tr>
            <td class="center">3</td>
            <td><code>=, *=, /=, %=, +=, -=, &=, ^=, |=, <<=, >>=, >>>=</code></td>
            <td>할당 연산자</td>
            <td class="center"><code>R->L</code></td>
            <td class="center">2</td>
            <td>좌변 값(lval), 타입 무방</td>
            <td>타입 무방</td>
        </tr>
        <tr>
            <td class="center">2</td>
            <td><code>yield</code></td>
            <td>넘김</td>
            <td class="center"><code>R->L</code></td>
            <td class="center"></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td class="center">1</td>
            <td><code>...</code></td>
            <td>전개</td>
            <td class="center">없음</td>
            <td class="center"></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td class="center">0</td>
            <td><code>,</code></td>
            <td>콤마 연산자(연속, 쉼표)</td>
            <td class="center"><code>L->R</code></td>
            <td class="center">2</td>
            <td>타입 무방</td>
            <td>타입 무방</td>
        </tr>
    </tbody>
</table>

* [Operator precedence - JavaScript | MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_Precedence)
* [자바스크립트 완벽가이드](http://www.stilson.net/documentation/javascript.pdf)