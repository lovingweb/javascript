# Bitwise operators

<p class="sub-title">비트 연산자</p>

|연산자|수행되는 연산|결합방향|피연산자 개수|피연산자 타입|반환|
|:---:|---|:---:|:---:|---|---|
|`&`|비트 단위 AND <sup>Bitwise AND</sup>|`L->R`|2|정수|정수|
|&#x007C;|비트 단위 OR <sup>Bitwise OR</sup>|`L->R`|2|Number, Number|Number|
|`^`|비트 단위 XOR <sup>Bitwise XOR</sup>|`L->R`|2|정수|정수|
|`~`|비트 단위 NOT <sup>Bitwise NOT</sup>|`R->L`|1|정수|정수|
|`<<`|왼쪽으로 이동<sup>Left shift</sup>|`L->R`|2|정수|정수|
|`>>`|부호 비트를 확장하면서 오른쪽으로 이동<sup>Sign-propagating right shift</sup>|`L->R`|2|정수|정수|
|`>>>`|부호 비트 확장 없이 오른쪽으로 이동<sup>Zero-fill right shift</sup>|`L->R`|2|정수|정수|

> **비트 연산자를 사용하는 이유**  
>  비트 연산을 하는 가장 큰 이유는 연산속도다.  bit는 최소정보단위로 다른 추상화된 정보들과 다르게 즉시 해석되어 전달되므로 연산 속도가 매우 빠르다는 장점이 있다.
> 다음으로 제어에 뛰어난 성능을 발휘한다. 레지스터의 직접 접근을 통해 bit 레벨 조작이 가능하다. 
> 또한, 비트연산을 응용하면 복잡한 로직도 비교적 짧은 코드로 만들 수 있으며, 메모리의 최적화가 가능하다. 하지만 내공이 필요하다.