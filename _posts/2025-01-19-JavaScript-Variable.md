---
title: 변수선언
categories:
- 자바스크립트
feature_image: "https://picsum.photos/2560/600?image=872"
---

> 자바스크립트에서 변수를 선언하는 방법은 세 가지가 있습니다: `var`, `let`, `const`. 각 방법은 사용

| 선언 키워드 | 스코프 |재선언 가능|값 변경 가능|초기화 필수|
|--|--|--|--|--|
| var | 함수 스코프 | 가능 | 가능 | 아니요 |
| let | 블록 스코프* | 불가능 | 가능 | 아니요 |
| const | 블록 스코프* | 불가능 | 불가능 | 예 |


### **변수 선언은 언제 어떤 것을 사용해야 할까?**

1.  **`const`**: 기본적으로 항상 사용. 값이 변경되지 않는 변수를 선언할 때 적합.
2.  **`let`**: 값이 변경될 가능성이 있는 경우에 사용.
3.  **`var`**: 최신 코드에서는 가급적 사용하지 않음. (레거시 코드에서만 사용 권장)

### **변수선언의 룰**
-   JavaScript 식별자는 '문자(`a`-`z`,  `A`-`Z`)', '밑줄(`_`)' 혹은 '달러 기호(`$`)'로 시작해야 합니다. 두 번째 글자부터는 '숫자(`0`-`9`)'도 가능합니다.
-   '대문자'와 '소문자'는 구별합니다.  `myname`과  `myName`은 다른 이름입니다.
-------
    let a, b, c, d; // 좋지않음
    let name; // 너무 추상적인 이름
	let bad_variable_name; // 비추천 방식
	let goodVariableName; // 추천 방식 'camelCase' 
	const GOOD_VARIABLE_NAME // const 일때 대문자 추천

## 변수의 스코프(Scope)

> 변수가 접근하거나 사용할 수 있는 코드의 범위를 의미합니다. 스코프는 자바스크립트의 실행 환경에서 중요한 개념으로, 코드의 구조와 변수 사용 방식을 결정합니다.

### 1. **글로벌 스코프 (Global Scope) 전역 변수**
-   **전역 변수**는 프로그램 전체에서 접근 가능하며, 함수나 블록 밖에서 선언된 변수입니다.
-   어디에서든 접근할 수 있지만, 의도치 않은 충돌과 부작용이 발생할 가능성이 있습니다.
-------
    let globalVar = "I am global"; // 글로벌 변수
    function showGlobal() {
	   console.log(globalVar); // 함수 내부에서도 접근 가능
    }
     
     showGlobal(); // I am global
     console.log(globalVar); // I am global

### 2. **블록 스코프 (Block Scope) 지역변수**

-   `{}`로 둘러싸인 블록 내에서만 유효.
-   `let`과 `const`로 선언된 변수에 적용됩니다.
-   블록이 끝나면 변수는 메모리에서 제거됩니다.
 -------
    {
	    let blockScopedVar = "I am block scoped";
	    console.log(blockScopedVar); // I am block scoped
	    }
	    console.log(blockScopedVar); 
	    // ReferenceError: blockScopedVar is not defined


### **3. Block Scope가 없는 var**

블록 스코프를 무시하고, 선언된 변수를 함수 전체(혹은 전역)에서 사용할 수 있게 만듭니다. 이로 인해 의도치 않은 동작이 발생할 수 있습니다.

#### **`var`의 블록 스코프 예외**

    if (true) {
	    var notBlockScoped = "I am not block scoped";
    }
    console.log(notBlockScoped); // I am not block scoped

####  **Block Scope가 중요한 이유**

1.  **안정성**: 블록 외부에서 의도치 않게 변수를 참조하거나 수정하는 문제를 방지합니다.
2.  **메모리 효율성**: 블록이 끝나면 변수가 메모리에서 제거되어 효율적인 메모리 관리가 가능합니다.
3.  **가독성**: 변수의 사용 범위가 명확해져 코드 이해가 쉬워집니다.

결론적으로, `let`과 `const`를 사용하면 **Block Scope**를 활용하여 안전하고 유지보수성이 높은 코드를 작성할 수 있습니다!

### 4. 상수 (constant)  _ const 

 -  **값 변경 불가**:
    -   선언 후 값을 변경할 수 없습니다.
    -   값을 재할당하려고 하면 오류가 발생합니다.
 -  **블록 스코프**:
    -   `const`는 `let`과 마찬가지로 **블록 스코프**를 따릅니다.
 -  **선언 시 초기화 필수**:
    -   선언과 동시에 값을 할당해야 합니다.
    -   초기화를 생략하면 오류가 발생합니다.
    ----
       
         // 상수로 선언된 숫자와 문자열
         const TAX_RATE = 0.1; 
        const GREETING = "Welcome";
        
        // 상수로 객체나 배열 선언
          const CONFIG = { baseUrl: "https://api.example.com", timeout: 5000 };
          const COLORS = ["red", "green", "blue"];
          

### **const 주의사항**

1.  **변하지 않는 값만 상수로 사용**:
    -   예를 들어, 수학 상수(`PI`), 설정 값 등은 상수로 선언하는 것이 적합합니다.
2.  **객체와 배열의 내용 관리**:
    -   `const`로 선언된 객체와 배열은 내부의 내용이 변경될 수 있으므로, 불변성을 유지하려면 별도의 라이브러리(예: `Object.freeze`)를 사용해야 합니다.
3.  **선언 순서**:
    -   `const`는 선언 이전에 접근할 수 없으며, **호이스팅(hoisting)**은 되지만 초기화되지 않습니다.


## 참고 문헌

 - [codeit](https://www.codeit.kr/) 
 - [chatgpt](https://chatgpt.com/) 