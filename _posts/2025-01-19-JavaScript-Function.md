---
title: 함수(Function)
categories:
- 자바스크립트
feature_image: "https://picsum.photos/2560/600?image=872"
---

> 특정 작업을 수행하거나 값을 계산하는 코드 블록입니다. 함수는 코드의 재사용, 유지보수, 모듈화를 가능하게 하는 기본 단위입니다.

### **함수의 특징**

1.  **재사용 가능**: 한 번 정의하면 여러 번 호출 가능.
2.  **매개변수(Parameter)와 반환값(Return Value)**: 입력값을 받아 특정 작업을 수행하고 결과를 반환할 수 있음.
3.  **다양한 선언 방식**: `function`, 화살표 함수(`=>`), 익명 함수 등 여러 방식으로 선언 가능.

### **1. 함수 선언(Declaration)**

> 가장 기본적인 함수 선언 방식

    function add(a, b) {
	    return a + b; // 두 수의 합을 반환
    }
    const result = add(5, 3); // 함수 호출
    console.log(result); // 8

### ** 2. 함수 표현식(Expression) **

> 함수를 변수에 저장하는 방식

    const multiply = function (a, b) { return a * b; }; 
    console.log(multiply(4, 5)); // 20

### ** 3. 화살표 함수 (Arrow Function)**

> 간결한 문법으로 작성할 수 있는 함수입니다. 주로 익명 함수나 간단한 작업에 사용

    const subtract = (a, b) => a - b; // 중괄호와 return 생략 가능
    console.log(subtract(10, 4)); // 6
    // 중괄호 사용 시 return 필요
    const square = (n) => {
      return n * n;
     };
     console.log(square(5)); // 25


### ** 4. 익명 함수 (Anonymous Function)**

> 이름이 없는 함수로, 보통 다른 함수의 인자로 사용됩니다.

    setTimeout(function () {
     console.log("This runs after 2 seconds.");
     }, 2000);


### ** 5. 함수는 일급 객체(First-Class Object)**

> 함수는 변수처럼 다룰 수 있습니다.

    // 함수를 변수에 저장
    const greet = function () {
        console.log("Hi there!");
    };
    // 함수를 다른 함수의 인자로 전달
    function executeFunction(fn) {
       fn();
       }
    executeFunction(greet); // Hi there!
    // 함수에서 함수를 반환
    function createMultiplier(multiplier) {
	       return function (value) {
		      return value * multiplier;
		  };
	  }
	  const double = createMultiplier(2);
	  console.log(double(5)); // 10
	        
### ** 6. 재귀 함수 (Recursive Function)**

> 함수가 자기 자신을 호출하는 함수입니다.

    function factorial(n) {
	    if (n === 1) return 1; // 종료 조건
	    return n * factorial(n - 1);
    }
    console.log(factorial(5)); // 120




## 함수의 파라미터 (Parameter)
-   **파라미터**는 함수를 호출할 때 전달받는 입력값을 저장하는 변수입니다.
-   함수 선언 시 `()` 안에 작성하며, 여러 개의 파라미터를 사용할 수 있습니다.
-   파라미터는 값이 없어도 기본값을 지정할 수 있습니다.

### **기본적인 파라미터 사용**

    function greet(name) {
	    console.log(`Hello, ${name}!`);
    }
    greet("Alice"); // Hello, Alice!
    greet("Bob");   // Hello, Bob!


### **여러 개의 파라미터 사용**

    function add(a, b) {
	    return a + b;
    }
    console.log(add(5, 3)); // 8


### **파라미터 기본값**

    function greet(name = "Guest") {
	    console.log(`Hello, ${name}!`);
    }
    greet();          // Hello, Guest!
    greet("Charlie"); // Hello, Charlie!

### **옵셔널 파라미터**

> 함수의 매개변수에 기본값을 직접 설정할 수 있습니다.

    function greet(name = "Guest") {
	     console.log("Hello, " + name);
     }
     greet();             // Hello, Guest
     greet("Alice");      // Hello, Alice
옵셔널 파라미터는 비어있는값에 적용이되기 때문에 마지막에 설정해주어야 순서를 인식할수있다.

#### **2개 이상 옵셔널 파라미터**

    function greet(firstName = "Guest", lastName = "User") {
    console.log(`Hello, ${firstName} ${lastName}!`);
    }
    greet();    // Hello, GuestUser!
    greet("John"); // Hello, John User!
    greet("John", "Doe");  // Hello, John Doe!

#### **나머지 파라미터와 함께 사용 _ 나머지 파라미터(...rest)**

    function displayInfo(firstName = "Guest", lastName = "User", ...hobbies) {
	    console.log(`Hello, ${firstName} ${lastName}!`);
	    if (hobbies.length > 0) {
	        console.log(`Your hobbies are: ${hobbies.join(", ")}`);
	    } else {
	        console.log("You have no hobbies listed.");
	    }
    }
    displayInfo();  
    // Hello,Guest User! You have no hobbies listed.
    displayInfo("John");                         
    // Hello, John User! You have no hobbies listed.
    displayInfo("John", "Doe", "Reading", "Swimming");
    // Hello, John Doe! Your hobbies are: Reading, Swimming



## 함수의 반환값 (Return Value)
-   함수는 `return` 키워드를 사용해 값을 반환할 수 있습니다.
-   반환값이 있는 함수는 결과를 호출한 위치로 전달하며, 이를 변수에 저장하거나 다른 연산에 사용할 수 있습니다.
-   반환값이 없는 경우 함수는 기본적으로 `undefined`를 반환합니다.

### **기본적인 Return 사용**

    function multiply(a, b) {
	    return a * b;
    }
    const result = multiply(4, 5);
    console.log(result); // 20


### **여러 값을 반환 (객체 사용)**

    function calculate(a, b) {
	    return {
	        sum: a + b,
	        difference: a - b,
	        product: a * b
	    };
    }
    const results = calculate(7, 3);
    console.log(results.sum);        // 10
    console.log(results.difference); // 4
    console.log(results.product);    // 21

### **return 이후 코드**

    function multiply(a, b) {
	    return a * b;
	    console.log(a);  // 작동하지않음
    }
return 이후에는 작동하지않고  return 에서 중단됨


### **화살표 함수와 반환값**

> 화살표 함수에서 `return`을 생략할 수 있는 경우도 있습니다.

    const add = (a, b) => a + b; // 단일 표현식에서는 return 생략 가능
    console.log(add(2, 3)); // 5


## 참고 문헌

 - [codeit](https://www.codeit.kr/) 
 - [chatgpt](https://chatgpt.com/) 