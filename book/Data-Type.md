# Data type

<p class="sub-title">데이터 타입</p>

최신 [ECMAScript 표준](http://www.ecma-international.org/ecma-262/6.0/#sec-ecmascript-language-types)은 7가지 데이터 타입을 정의한다.



* 6가지 원시 데이터 타입primitive data type
    * Undefined
    * Null
    * Boolean
    * String
    * Symbol (ECMAScript 6에 도입)
    * Number
* Object
    * Function
    * Array
    * Date
    * RegExp


<!--

ECMAScript에서는 개발자가 데이터 타입을 정의할 수 없으므로 모든 데이터는 위에 나열한 여섯가지 타입중 하나에 속합니다.


정의되지 않은 변수 - undefined 불리언 - boolean 문자열 - string 숫자 - number 함수를 제외한 객체 또는 null - object 함수 - function



https://developer.mozilla.org/ko/docs/A_re-introduction_to_JavaScript


JavaScript는 유형 및 연산자, 표준 내장 객체 및 메소드가 있는 다중 패러다임, 동적 언어입니다. 구문은 Java 및 C 언어를 기반으로합니다. 이러한 언어의 많은 구조가 JavaScript에도 적용됩니다. JavaScript는 클래스 대신 객체 프로토 타입을 사용하여 객체 지향 프로그래밍을 지원합니다 (프로토 타입 상속 및 ES2015 Classes). JavaScript는 함수형 프로그래밍도 지원합니다. 함수는 객체이며, 함수는 실행 가능한 코드를 유지하고 다른 객체와 마찬가지로 전달 될 수 있습니다.

어떤 언어에서라도 기초가 되는 부분인 타입을 살펴보는 것부터 시작해봅시다. JavaScript 프로그램은 값을 다루고 해당 값은 모두 타입을 가지고 있습니다. JavaScript의 타입은 다음과 같습니다:

수 (Number)
문자열 (String)
부울 (Boolean)
함수 (Function)
객체 (Object)
기호 (Symbol) (ES2015에 새롭게 추가)
... 오, 그리고 약간 특별한 타입인 정의되지 않음(Undefined) 과 널(Null) 이 있습니다. 또한 객체의 특별한 종류인 배열(Array) 객체. 그리고 자유롭게 사용할 수 있는 날짜(Date) 객체 와 정규식(RegExp) 객체가 있습니다. 그리고 기술적으로 정확히 말해 함수(Function)는 단지 객체의 특별한 타입으로 취급됩니다. 따라서 타입 구조도를 정리해보면 다음과 같습니다:

수 (Number)
문자열 (String)
부울 (Boolean)
기호 (Symbol)
객체 (Object)
함수 (Function)
배열 (Array)
날짜 (Date)
정규식 (RegExp)
널 (Null)
정의되지 않음 (Undefined)
그리고 또 몇 가지 오류 타입이 내장되어 있습니다. 그렇지만 처음 구조도를 기억하고만 있으면 다른 것들도 아주 쉽게 이해할 수 있을 것입니다.

-->