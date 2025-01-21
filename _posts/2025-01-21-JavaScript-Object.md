---
title: 객체 (Object)
categories:
- 자바스크립트
feature_image: "https://picsum.photos/2560/600?image=872"
---

-   데이터를 **키-값(key-value) 쌍**으로 저장하는 구조.
-   특정 **속성(property)**이나 **키(key)**를 기준으로 데이터를 저장하고 관리.
-   주로 **구조화된 데이터**를 표현하는 데 사용.
----

    const person = {
	    'property name: 'property value'
	     name: "John",
	     age: 30,
	     job: "Developer",
     };
     console.log(person.name); // "John"
     
     const obj = { a: 1, b: 2 }; 
     console.log(obj["a"]); // 1

----

### 1.객체 리터럴
#### 중괄호 `{}`를 사용해 생성

    const person = {
	    name: "Alice",
	    age: 30,
	    job: "Developer",
	    greet: function() {
		    console.log("Hello!");
	    },
    };
    console.log(person.name); // "Alice"
    person.greet(); // "Hello!"

#### `Object` 생성자
`new Object()`를 사용하여 객체를 생성

    const obj = new Object(); 
    obj.key = "value";
    console.log(obj.key); // "value"
    
#### 클래스 사용
클래스 문법으로 객체를 생성( ES6 ) _ 글쓴이 모르겠음..

    class Person {
	    constructor(name, age) {
		    this.name = name;
		    this.age = age;
	    }
	    greet() {
		    console.log(`Hi, I'm ${this.name}.`);
	    }
    }
    
    const person = new Person("Bob", 25);
    person.greet(); // "Hi, I'm Bob."
    
----
### 2. 객체 속성 접근
#### 점 표기법 : 키 이름을 직접 사용하여 접근

    console.log(person.name); // "Alice"

#### 대괄호 표기법 :  키 이름에 공백이나 특수 문자가 포함된 경우 사용

    console.log(person["name"]); // "Alice"
    
    // 변수를 사용한 방식
    const key = "age"; 
    console.log(person[key]); // 30
    
----
### 3. 객체 메서드
객체의 값이 함수인 경우, 이를 **메서드(method)**라고 합니다.

    const calculator = {
	    add: function(a, b) {
		    return a + b;
	    },
    };
    
    console.log(calculator.add(5, 3)); // 8

----
### 4. 객체 조작
#### 속성 추가

    person.hobby = "Reading";
    console.log(person.hobby); // "Reading"


#### 속성 수정

    person.age = 31;
    console.log(person.age); // 31


#### 속성 삭제

    delete person.job;
    console.log(person.job); // undefined

#### 변수에 객체를 할당했을때

    const obj1 = { a: 1 };
    const obj2 = obj1;
    
    obj2.a = 2;
    console.log(obj1.a); // 2 (같은 객체를 참조)

obj2 에서 obj1의 값을 변경해도 적용된다.

#### 기타 조작

    console.log(Object.keys(person)); 
    // ["name", "age", "hobby"]
    >> Object.keys() : 객체의 모든 키를 배열로 반환
    
    console.log(Object.values(person)); 
    // ["Alice", 31, "Reading"]
    >> Object.values() : 객체의 모든 값을 배열로 반환
    
    console.log(Object.entries(person));
    // [["name", "Alice"], ["age", 31], ["hobby", "Reading"]]
    >> Object.entries() : 키-값 쌍을 `[키, 값]` 형태의 배열로 반환
    
    const target = { a: 1 };
    const source = { b: 2, c: 3 };
    const result = Object.assign(target, source);
    console.log(result); 
    // { a: 1, b: 2, c: 3 }
    >> Object.assign() : 객체를 복사하거나 합칠 때 사용

    
----
####  property name 주의사항

 1. 첫번째 글자는 반드시 문자, 밑줄(_), 달러기호($) 중하나
 2. 띄어쓰기 금지 (  띄어쓰기시 'a b' '' 를 이용 )
 3. 하이픈 금지 ( 하이픈사용시 'a-b' '' 를 이용 )

#### property value는 문자열, 숫자, 배열, 함수, 객체 등 어떤 데이터 타입이든 저장 가능.

    const obj = { 
	    key1: "value", 
	    key2: 123, 
	    key3: [1, 2, 3], 
	    key4: { nestedKey: "nestedValue" }, 
    };

## 날짜(Date) 객체

날짜와 시간을 다루는 데 사용되는 내장 객체입니다. 이 객체는 **현재 날짜와 시간**을 가져오거나, 특정 날짜와 시간을 설정할 수 있는 메서드를 제공합니다. `Date` 객체는 **날짜 계산**, **형식 지정**, **날짜 비교** 등 여러 기능을 지원합니다.

#### 현재 날짜와 시간 생성

    const now = new Date(); 
    console.log(now); // 현재 날짜와 시간이 출력됩니다.

#### 특정 날짜와 시간 생성

    const date1 = new Date("2025-01-01"); 
    // 문자열로 날짜를 입력
    console.log(date1); 
    // 2025-01-01T00:00:00.000Z >> 여기서 T는 24시 표기형
    
    
    const date2 = new Date(2025, 0, 1, 12, 0, 0); 
    // 연도, 월, 일, 시간, 분, 초, 밀리초로 지정
    console.log(date2); 
    // 2025년 1월 1일, 12:00:00
    // 월은 0부터 시작합니다. 

#### 특정날짜와 현재시간 차이 구하기

    let date1 = new Date(2025, 0, 1, 12, 0, 0); //특정시간
    let date2 = new Date(); // 현재시간
    
    let timeDiff = date1.getTime() - date2.getTime();
    // 특정시간에서 현재기간 계산
    console.log(timeDiff + '초');
    console.log(timeDiff / 1000 / 60 + '분');
    console.log(timeDiff / 1000 / 60 / 60 + '시간');

new Date() 는 타임스탬프(밀리초 단위)*로 생성되기 때문에 분과 시간을 계산해줘야한다.

타임스탬프(밀리초 단위): 1970년 1월 1일 00:00:00 UTC 이후의 밀리초 단위

### 1. 객체 메서드

#### 현재 날짜와 시간 가져오기

 - `getFullYear()`: 4자리 연도 반환
 - `getMonth()`: 월을 반환 (0부터 11까지, 0은 1월)
 - `getDate()`: 날짜(일)를 반환 (1부터 31까지)  
 - `getDay()`: 요일을 반환 (0은 일요일, 1은
 - `getHours()`: 시간을 반환 (0부터 23까지) 
 - `getMinutes()`: 분을 반환 (0부터 59까지)  
 - `getSeconds()`: 초를 반환 (0부터 59까지) 
 - `getMilliseconds()`:밀리초를 반환 (0부터 999까지)  
 - `getTime()`: 타임스탬프(1970년 1월 1일 00:00:00 UTC 이후 밀리초)를 반환

----
    const now = new Date(); 
    console.log(now.getFullYear()); // 예: 2025

----
#### 날짜와 시간 설정하기

 - `setFullYear(year)`: 연도를 설정
 - `setMonth(month)`: 월을 설정 (0부터 11까지)
 - `setDate(day)`: 날짜(일)를 설정
 - `setHours(hours)`: 시간을 설정 (0부터 23까지)
 - `setMinutes(minutes)`: 분을 설정 (0부터 59까지)
 - `setSeconds(seconds)`: 초를 설정 (0부터 59까지)
 - `setMilliseconds(milliseconds)`: 밀리초를 설정 (0부터 999까지)

----

    const now = new Date(); 
    
    now.setFullYear(2023); 
    console.log(now.getFullYear()); // 2023
    
    now.setDate(15);
    console.log(now.getDate()); // 15

setFullYear(year) 해서 getFullYear() 으로 받아오는듯

----

#### 메서드를 사용하여 날짜를 문자열로 변환

 - `toLocaleDateString()`: 로케일에 맞는 날짜 형식으로 변환 // 예: 2025. 1. 20.
 - `toLocaleTimeString()`: 로케일에 맞는 시간 형식으로 변환 // 예: 10:30:00
 - `toISOString()`: ISO 8601 형식(UTC)으로 날짜와 시간 반환 // 예: 2025-01-20T10:30:00.500Z
 - `toString()`: 기본적인 날짜 문자열로 변환 // 예: Mon Jan 20 2025 10:30:00 GMT+0900 (Korean Standard Time)
 
----
    console.log(now.toLocaleDateString()); 
    // 예: 2025. 1. 20.



## 참고 문헌

 - [codeit](https://www.codeit.kr/) 
 - [chatgpt](https://chatgpt.com/) 