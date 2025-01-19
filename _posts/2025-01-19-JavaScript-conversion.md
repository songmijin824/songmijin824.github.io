---
title: 자료형의 형변환
categories:
- 자바스크립트
feature_image: "https://picsum.photos/2560/600?image=872"
---



> **형변환(Type Conversion)**은 값의 타입을 다른 타입으로 변환하는 과정을 의미합니다. 자바스크립트는 **자동 형변환 (Implicit Type Conversion)**과 **명시적 형변환 (Explicit Type Conversion)**을 지원합니다.

### **1.명시적 형변환 (Explicit Type Conversion)**

#### **문자열로 변환 (String)**

    //`String()` 사용
    let num = 123;
    let bool = true;
    let result1 = String(num);   // 숫자를 문자열로 변환
    let result2 = String(bool);  // 불린값을 문자열로 변환
    console.log(result1);  // "123"
    console.log(result2);  // "true"
    
    //`toString()` 사용
    let num = 123; 
    let result = num.toString(); // 숫자를 문자열로 변
    console.log(result); // "123"

#### **숫자로 변환 (Number)**

    //`Number()` 사용
    let str = "123";
    let bool = true;
    let result1 = Number(str);   // 문자열을 숫자로 변환
    let result2 = Number(bool);  // 불린값을 숫자로 변환
    console.log(result1);  // 123
    console.log(result2);  // 1 (true는 1로 변환)
    
    //`parseInt()` 사용
    let str = "123.45";
    let result = parseInt(str);  // "123.45"에서 정수 부분만 반환
    console.log(result);  // 123
    
    //`parseFloat()` 사용
    let str = "123.45";
    let result = parseFloat(str);  // "123.45"를 실수로 변환
    console.log(result);  // 123.45


#### **불린형으로 변환 (Boolean)**
`Boolean()`을 사용하여 값을 불린형으로 변환할 수 있습니다. 값이 **진리값(Truthy)**이면 `true`, **거짓값(Falsy)**이면 `false`로 변환됩니다

    //`Boolean()` 사용
    let num = 1;
    let str = "";
    let result1 = Boolean(num);  // 1은 truthy이므로 true
    let result2 = Boolean(str);  // 빈 문자열은 falsy이므로 false
    console.log(result1);  // true
    console.log(result2);  // false

#### **객체로 변환 (Object)**

    //`Object()` 사용
    let num = 123;
    let result = Object(num);  // 숫자를 객체로 변환
    console.log(result);  // [Number: 123]

### **2.자동 형변환 (Implicit Type Conversion)**
연산을 수행할 때 **자동으로** 값을 적절한 타입으로 변환합니다. 예를 들어, **숫자**와 **문자열**을 결합하려면 자바스크립트가 숫자를 문자열로 자동 변환합니다.

#### **숫자 + 문자열**

    let num = 5;
    let str = " apples";
    let result = num + str;  // 숫자가 문자열로 변환되어 결합됨
    console.log(result);  // "5 apples"

#### **숫자 - 문자열**

    let num = 10;
    let str = "5";
    let result = num - str;  // 문자열 "5"가 숫자 5로 변환
    console.log(result);  // 5

#### **불린형과 숫자**

    let bool = true;
    let result = bool + 10;  // true는 1로 변환
    console.log(result);  // 11

#### **기타 자동 형변환의 예시**

    let x = 5 + "5";  // 숫자 5와 문자열 "5"는 문자열로 결합됨
    console.log(x);  // "55"
    let y = "10" - 5;  // 문자열 "10"은 숫자로 변환되어 연산됨
    console.log(y);  // 5

#### ** 자료형에 따른 ==와 ===의 차이 **
-   **`==`**: **타입 변환 후 비교**합니다. 즉, 다른 타입이라도 값을 비교할 때 타입을 자동으로 변환하여 비교합니다.
-   **`===`**: **타입과 값이 모두 같아야** `true`를 반환합니다.

         console.log(5 == "5");  // true (자동 형변환 후 값 비교)
         console.log(5 === "5"); // false (타입이 다르므로)
         
         console.log(null== undefined);  // true (자동 형변환 후 값 비교)
         console.log(null=== undefined); // false (타입이 다르므로)

### **3. 형변환의 특이사항**
-   **빈 문자열 (`""`)**은 불린형으로 변환 시 **`false`**가 됩니다.
-   **`null`**은 불린형으로 변환 시 **`false`**가 됩니다.
-   **`undefined`**도 불린형으로 변환 시 **`false`**가 됩니다.
-   **`NaN`**은 숫자로 변환하면 **`NaN`**이 됩니다.
-   **`true`**는 숫자로 변환하면 **`1`**, **`false`**는 숫자로 변환하면 **`0`**이 됩니다.



## 참고 문헌

 - [codeit](https://www.codeit.kr/) 
 - [chatgpt](https://chatgpt.com/) 