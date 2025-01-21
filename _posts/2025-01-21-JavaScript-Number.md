---
title: javascript 자료형 숫자 심화
categories:
- 자바스크립트
feature_image: "https://picsum.photos/2560/600?image=872"
---

### 1. 숫자표시법

#### 지수표기법

    let million = 1000000000; // 1000000000
    let myNumber = 1e9; // 1000000000
    >> 'e'를 이용해 0의 갯수를 표기
    
    console.log(million === myNumber);
    >> true
    
    console.log(25e5 === 2500000); // true
    console.log(5.3e3 === 5300); // true
    console.log(-6.1e8 === -610000000); // true
    
    console.log(16e-5 === 0.00016); // true
    console.log(3.5e-3 === 0.0035); // true
    console.log(-9.1e-5 === -0.000091); // true

#### 16진법 : 0x 를 이용해 표현 

    let hexNumber = 0xff; // 255
    let hexNumber = 0xFF; // 255
    

#### 8진법 : 0o 를 이용해 표현

    let octal = 0o377; // 255

#### 2진법 : 0b 를 이용해 표현

    let binary = 0b11111111; // 255

### 2. 숫자형 메소드

#### toFixed()
숫자를 고정된 소수점 자릿수로 반올림하여 **문자열로 반환**합니다. 자릿수 기본값은 `0`입니다.

    const num = 12.34567;
    
    console.log(num.toFixed(2)); // "12.35"
    console.log(num.toFixed(0)); // "12"
    console.log(num.toFixed(5)); // "12.34567"

####  toExponential()
숫자를 **지수 표기법**으로 변환하여 **문자열로 반환**합니다.

    const num = 123456;
    console.log(num.toExponential()); // "1.23456e+5"
    console.log(num.toExponential(2)); // "1.23e+5"

#### toString()
숫자를 지정된 **진법**으로 **문자열로 변환**합니다. 기본값은 10진법입니다.

    const num = 255;
    
    console.log(num.toString()); // "255" (기본 10진수)
    console.log(num.toString(16)); // "ff" (16진수)
    console.log(num.toString(2)); // "11111111" (2진수)

#### toPrecision()
숫자를 지정된 **전체 자릿수(유효 숫자)**로 반올림하여 **문자열로 반환**합니다.

    const num = 12.34567;
    
    console.log(num.toPrecision(3)); // "12.3"
    console.log(num.toPrecision(6)); // "12.3457"

### 3. Number 객체의 정적 메서드

#### Number.isFinite(value)
주어진 값이 **유한한 숫자**인지 확인합니다.

    console.log(Number.isFinite(100)); // true
    console.log(Number.isFinite(Infinity)); // false
    console.log(Number.isFinite("100")); // false


#### Number.isInteger(value)
주어진 값이 **정수**인지 확인합니다.

    console.log(Number.isInteger(100)); // true
    console.log(Number.isInteger(12.34)); // false
    console.log(Number.isInteger("100")); // false


#### Number.isNaN(value)
값이 **NaN**인지 확인합니다. 숫자가 아닌 값을 NaN으로 간주하지 않습니다.

    console.log(Number.isNaN(NaN)); // true
    console.log(Number.isNaN("NaN")); // false
    console.log(Number.isNaN(123)); // false


####  Number.parseFloat(string)
문자열을 부동소수점 숫자로 변환합니다.

    console.log(Number.parseFloat("123.45")); // 123.45
    console.log(Number.parseFloat("123.45px")); // 123.45
    console.log(Number.parseFloat("abc")); // NaN

#### Number.parseInt(string, radix)
문자열을 **정수**로 변환하며, 선택적으로 **진법(radix)**을 지정할 수 있습니다.

    console.log(Number.parseInt("123")); // 123
    console.log(Number.parseInt("123px")); // 123
    console.log(Number.parseInt("101", 2)); // 5 (2진법)

####  Number.isSafeInteger(value)
값이 안전한 정수(`-(2^53-1)`에서 `2^53-1` 범위)인지 확인합니다.

    console.log(Number.isSafeInteger(9007199254740991)); // true
    console.log(Number.isSafeInteger(9007199254740992)); // false


### 4. Math 객체 메서드

#### Math.round()
숫자를 반올림하여 가장 가까운 정수로 반환합니다.

    console.log(Math.round(4.5)); // 5
    console.log(Math.round(4.4)); // 4

#### Math.ceil()
숫자를 **올림**하여 가장 가까운 정수로 반환합니다.

    console.log(Math.ceil(4.1)); // 5
    console.log(Math.ceil(4.9)); // 5

#### Math.floor()
숫자를 **내림**하여 가장 가까운 정수로 반환합니다.

    console.log(Math.floor(4.9)); // 4
    console.log(Math.floor(4.1)); // 4

#### Math.abs()
숫자의 절댓값을 반환합니다.

    console.log(Math.abs(-10)); // 10
    console.log(Math.abs(10)); // 10

#### Math.max()와 Math.min()
전달된 숫자 중 가장 큰 값 또는 가장 작은 값을 반환합니다.

    console.log(Math.max(10, 20, 30)); // 30
    console.log(Math.min(10, 20, 30)); // 10

#### Math.pow()
거듭제곱 구해 값을 반환합니다.

    console.log(Math.pow(2, 3));  // 8
    console.log(Math.pow(5, 2)); // 25

#### Math.sqrt()
제곱근을 구해 값을 반환합니다.

    console.log(Math.sqrt(25)); // 5
    console.log(Math.sqrt(49)); // 7

#### Math.random()
0 이상 1 미만의 난수*를 반환합니다. 

    console.log(Math.random()); // 예: 0.3456789
    console.log(Math.random() * 100); // 0부터 100 사이의 난수
여기서 난수는 랜덤의 숫자를 의미하며 * 100 으로 지수를 올려주어 게임, 샘플링, 테스트 등에서 자주 사용됩니다.

####  자주 쓰이는 조합 예제

    // 소수점 둘째 자리까지 반올림 후 문자열로 반환
    const num = 12.34567;
    console.log(num.toFixed(2)); // "12.35"
    
    // 난수를 생성하고 반올림
    const randomInt = Math.floor(Math.random() * 100);
    console.log(randomInt); // 0부터 99 사이의 정수

[[기타 메소드 참고]](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Math)




## 참고 문헌

 - [codeit](https://www.codeit.kr/) 
 - [chatgpt](https://chatgpt.com/) 