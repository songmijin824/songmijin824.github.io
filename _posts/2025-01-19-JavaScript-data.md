---
title: 자바스크립트의 기본 자료형
categories:
- ["자바스크립트", "기본 자료형"]
feature_image: "https://picsum.photos/2560/600?image=872"
---


## 자바스크립트의 기본 자료형

| 객체타입 | 값 | 설명 |
|--|--|--|
| **Number** | 1,-1,0,1.5 등 | 정수 및 부동소수점 숫자 |
|**String**|"Hello",'Hello' 등|문자열을 의미|
|**Boolean**| true, false |참과 거짓을 의미하는 논리적인 데이터 타입|
|**Null**|--|어떤 값이 의도적으로 비어있음을 표현|
|**Undefined**|--|값이 할당되지 않은 상태|
|**객체(Object)**|("Alice", 20, "A")|식별자로 참조할 수 있는 메모리에 있는 값|
| **BigInt** |2n,53n 등|Number의 안전 한계를 넘어서는 큰 정수도 안전하게 저장하고 연산, 정수 리터럴 끝에 n을 붙임|


### **1. 숫자형(Number)**

> **숫자형(Number)**은 숫자를 표현하는 기본 데이터 타입입니다. 숫자형은 정수와 실수를 모두 처리할 수 있으며, 수학적 계산 및 비교에 사용

**숫자형의 특징**

-   **정수**와 **실수**를 모두 포함합니다.
-   `Number` 타입은 부동소수점 방식으로 숫자를 처리합니다.
-   자바스크립트에서 숫자는 `number` 타입으로 하나의 타입만 존재하며, `int`, `float` 같은 구분은 없습니다.

**숫자형 기본**

    let num1 = 10; // 정수
    let num2 = 3.14; // 실수
    let num3 = -5; // 음수
    let num4 = 0; // 0
    
**숫자형 연산**

    let a = 5; 
    let b = 3; 
    console.log(a + b); // 8 (덧셈) 
    console.log(a - b); // 2 (뺄셈) 
    console.log(a * b); // 15 (곱셈) 
    console.log(a / b); // 1.666... (나눗셈) 
    console.log(a % b); // 2 (나머지) 
    console.log(a ** b); // 125 (거듭제곱)

**비교 연산자(`>`, `<`, `>=`, `<=`, `===`, `!==`)를 통해 비교**

    let x = 10; 
    let y = 5; 
    console.log(x > y); // true 
    console.log(x < y); // false 
    console.log(x === 10); // true 
    console.log(x !== 5); // true


### **2. 문자형(String)**

> **문자형(String)**은 텍스트 데이터를 다루는 기본 데이터 타입입니다. 문자열은 문자들의 집합으로, 텍스트를 표현할 때 사용됩니다. 문자열은 **작은따옴표('')**, **큰따옴표("")**, 또는 **백틱(``)**을 사용하여 생성할 수 있습니다.

**문자열 기본**

    let str1 = "Hello, World!";  // 큰따옴표 사용
    let str2 = 'Hello, World!';  // 작은따옴표 사용
    let str3 = `Hello, World!`;  // 백틱 사용

**문자열의 길이 (length)**

    let str = "JavaScript";
    console.log(str.length); // 10 (문자열의 길이)

**문자열 결합 (Concatenation)**

    let str1 = "Hello";
    let str2 = "World";
    let result = str1 + " " + str2; // 공백을 넣어 결합
    console.log(result);  // Hello World
    
    let str1 = "Hello";
    let str2 = "World";
    let result = `${str1} ${str2}`; // 템플릿 리터럴을 사용한 문자열 결합
    console.log(result);  // Hello World

**문자열 찾기**
-   **`indexOf()`**: 특정 문자열이 처음 나타나는 위치를 반환합니다. 찾지 못하면 `-1`을 반환합니다.
-   **`includes()`**: 특정 문자열이 포함되어 있는지 여부를 `true` 또는 `false`로 반환합니다.
    -------
    let str = "JavaScript is fun!";
    console.log(str.indexOf("is"));    // 11 (첫 번째 위치)
    console.log(str.includes("fun"));  // true
    console.log(str.includes("Python")); // false

**템플릿 리터럴 (Template Literals)**

> 템플릿 리터럴은 **백틱(``)**을 사용하여 문자열을 작성하는 방법입니다.

    let name = "Alice";
    let age = 25;
    let message = `My name is ${name} and I am ${age} years old.`;
    console.log(message);  // My name is Alice and I am 25 years old.
    

### **3. 불린형(Boolean)**

> **불린형(Boolean)**은 **`true`** 또는 **`false`** 두 값만을 가질 수 있는 데이터 타입입니다. 불린형은 주로 조건문에서 **참/거짓**을 판단할 때 사용되며, **논리 연산**을 수행할 때 중요합니다.

**불 대수**
 
 - And 연산자 (`&&`) : 두 값이 모두 `true`일 때만 `true`를 반환합니다.

| X | Y | X AND Y |
|--|--|--|
| True | True | True |
| True | False | False |
| False | True | False |
|False | False | False |

    let a = true;
    let b = false;
    console.log(a && b);  // false (하나라도 거짓이면 결과는 false)


 - OR 연산자 (`||`): 두 값 중 하나라도 `true`이면 `true`를 반환합니다.

| X | Y | X AND Y |
|--|--|--|
| True | True | True |
| True | False | True |
| False | True | True |
|False | False | False |

    let a = true;
    let b = false;
    console.log(a || b);  // true (하나라도 참이면 결과는 true)


 - NOT 연산자 (`!`) : **`true`는 `false`로**, **`false`는 `true`로** 반전

| X | NOT Y |
|--|--|
| True | False |
| False | True |

    let a = true;
    let b = false;
    console.log(!a);  // false
    console.log(!b);  // true


**불린형 기본**

    let isActive = true;  // 참
    let isFinished = false;  // 거짓
    let bool1 = Boolean(true); // true 
    let bool2 = Boolean(false); // false


**불린형 값의 자동 변환 (타입 강제 변환)**

> 자바스크립트에서는 다른 타입을 불린형으로 자동 변환할 수 있습니다.

 - **진리값 (Truthy)**: 조건문에서 **`true`**로 평가되는 값
	 `1`, `"hello"`, `[]`, `{}` 등이 있습니다.
 - **거짓값 (Falsy)**: 조건문에서 **`false`**로 평가되는 값
   `false`, `0`,`NaN`,`""` (빈 문자열), `null`,`undefined`
-------
    console.log(Boolean(0)); // false 
    console.log(Boolean(1)); // true 
    console.log(Boolean("hello")); // true 
    console.log(Boolean("")); // false 
    console.log(Boolean(null)); // false 
    console.log(Boolean({})); // true

**불린형 비교**

> 비교 연산자는 **`==`**, **`===`**, **`!=`**, **`!==`**, **`>`**, **`<`** 등을 사용할 수 있습니다.

    console.log(0 == false);   // true (0과 false는 동등, 자동 변환됨)
    console.log(0 === false);  // false (타입이 다르기 때문에 일치하지 않음)
   
    let isActive = true;
    let isLoggedIn = false;
    console.log(isActive === true);   // true
    console.log(isLoggedIn === false); // true


**if 문 사용**

    let isLoggedIn = true;
    if (isLoggedIn) {
	    console.log("You are logged in!");  // 출력됨
    } else {
	    console.log("Please log in.");
    }

**삼항 연산자 사용**

> 삼항 연산자는 조건문을 간단하게 표현하는 방법입니다. 불린형을 사용하여 `true` 또는 `false`일 때 실행할 내용을 지정할 수 있습니다.

    let isOnline = false;
    let status = isOnline ? "Online" : "Offline"; 
    // isOnline 값이 true/false 인지 구분해 ? 
    // 'true'일때 "Online" : 'false'일때 "Offline" 반환
    console.log(status);  // Offline

