---
title: 제어문 if, switch, for, while문
categories:
- 자바스크립트
feature_image: "https://picsum.photos/2560/600?image=872"
---
`if` 문은 조건을 평가하여 프로그램의 흐름을 제어하는 기본적인 조건문입니다. 조건이 참(`True`)일 때 특정 블록의 코드를 실행하고, 그렇지 않을 경우 다른 코드를 실행하거나 아무것도 하지 않을 수 있습니다.

    if (조건) { 
    // 조건이 참일 때 실행되는 코드 
    } else if (다른_조건) { 
    // 첫 번째 조건이 거짓이고, 두 번째 조건이 참일 때 실행되는 코드 
    } else { 
    // 모든 조건이 거짓일 때 실행되는 코드 
    }

----

    let x = 10; if (x > 5) { 
	    console.log("x는 5보다 큽니다."); 
    } else if (x === 5) { 
	    console.log("x는 5와 같습니다."); 
    } else { 
	    console.log("x는 5보다 작습니다."); 
    }

### 주요 개념

1.  조건 표현식: `if` 문에서 사용되는 조건은 불리언 값(`True` 또는 `False`)으로 평가됩니다. 비교 연산자(`==`, `>`, `<`, `>=`, `<=`, `!=`) 또는 논리 연산자(`and`, `or`, `not`)를 사용하여 조건을 작성할 수 있습니다.
2.  `elif` 또는 `else if`: 여러 조건을 순차적으로 검사할 때 사용합니다.
3.  `else`: 모든 조건이 거짓일 경우 실행될 코드를 정의합니다.


## 제어문 switch문

여러 조건을 효율적으로 처리하기 위해 사용하는 조건문입니다. 주로 `if...else` 문이 길어질 때 사용되며, 하나의 값에 대해 여러 경우(case)를 비교합니다.

### 동작 원리

1.  `switch` 문은 `표현식`을 평가하고 그 결과를 각 `case` 값과 순서대로 비교,해당 블록의 코드를 실행합니다.
2.  `break` 키워드는 `switch` 문을 빠져나가도록 합니다. 만약 `break`가 없으면 다음 `case`의 코드도 연속으로 실행됩니다(이것을 "fall-through"라고 합니다).
4.  `default`는 일치하는 값이 없을 때 실행되는 코드입니다(필수는 아님).

---
    switch (표현식) {
	    case 값1:
	    // 값1일 때 실행되는 코드
	    break;
	    case 값2:
	    // 값2일 때 실행되는 코드
	    break;
	    default:
	    // 위의 어떤 경우에도 해당하지 않을 때 실행되는 코드
    }

---
### 일반적인 예시
    let day = 3;
    
    switch (day) {
	    case 1:
		    console.log("월요일");
		    break;
	    case 2:
		    console.log("화요일");
		    break;
	    case 3:
		    console.log("수요일");
		    break;
	    case 4:
		    console.log("목요일");
		    break;
	    case 5:
		    console.log("금요일");
		    break;
	    default:
		    console.log("주말 또는 잘못된 값");
    }  >> 결과 수요일

### 조건조합

    let score = 85;
    
    switch (true) {
	    case score >= 90:
		    console.log("A 학점");
		    break;
	    case score >= 80:
		    console.log("B 학점");
		    break;
	    case score >= 70:
		    console.log("C 학점");
		    break;
	    default:
		    console.log("F 학점");
    }  >> 결과 : B학점
    
### 장점

-   복잡한 `if...else` 문을 더 읽기 쉽고 깔끔하게 작성 가능.
-   특정 값에 따라 실행할 코드가 달라질 때 적합.

### 주의사항

1.  `break`를 빼먹지 않기:`break`를 생략하면 원치 않는 fall-through가 발생할 수 있습니다.
2.  `case` 값은 고유해야 함: 중복된 `case`는 허용되지 않습니다.
3.  데이터 타입 일치 필요: `switch`는 엄격한 비교(`===`)를 사용하므로 타입도 동일해야 합니다.

## 제어문 for문
JavaScript에서 반복 작업을 수행할 때 사용하는 기본적인 루프 구조입니다. 반복 횟수가 명확하거나 배열과 같은 자료구조를 순회할 때 자주 사용됩니다.

    for (초기화부분; 조건부분; 추가동작부분) {
	    // 반복 실행할 코드
    }

  ----  

    for (let i = 0; i < 5; i++) {
	    console.log(i);
    }
    >> 0,1,2,3,4 순서대로 출력
    
###  배열 `for` 문 예시
    let fruits = ["apple", "banana", "cherry"]; 
    for (let i = 0; i < fruits.length; i++) {
	     console.log(fruits[i]); 
    } 
    >> apple, banana, cherry 순서대로 출력
    
### 역순 `for` 문 예시
    for (let i = 5; i > 0; i--) { 
	    console.log(i); 
    }
    >> 5,4,3,2,1 순서대로 출력

### 중첩 `for` 문 예시

    let matrix = [
	     [1, 2, 3],
	     [4, 5, 6],
	     [7, 8, 9]
     ];
     
     for (let i = 0; i < matrix.length; i++) {
	     for (let j = 0; j < matrix[i].length; j++) {
		     console.log(matrix[i][j]);
	     }
     } >> 1, 2, 3, 4, 5, 6, 7, 8, 9 출력

## for in문과 for of문 

### for ... in 문

-   **용도**: 객체의 속성 키(프로퍼티 이름)를 반복(iterate)합니다.
-   **대상**: 모든 열거 가능한(enumerable) 속성.
-   **반복 값**: 속성의 키(문자열 형태).

---

    let person = { name: "John", age: 30, city: "New York" };
    
    for (let key in person) {
	    console.log(key + ": " + person[key]);
    }
    >> name: John, age: 30, city: New York 출력

**주의사항** : 속성 키(프로퍼티 이름)에서 정수형 프로퍼티 네임이 있을 때 정수형 프로퍼티 네임을 오름차순으로 먼저 정렬하고, 나머지 프로퍼티들은 추가한 순서대로 정렬하는 특징이 있다.
의도치 않은 결과를 가져올 수도 있기 때문에 주의하거나 사용하지 않는게 좋다.

### for ... of 문
-   **용도**: 반복 가능한(iterable) 객체(예: 배열, 문자열, Map, Set 등)의 값을 반복합니다.
-   **대상**: 반복 가능한 객체(iterables)만 사용 가능.
-   **반복 값**: 객체의 값(value).

----

    let colors = ["red", "green", "blue"];
    
    for (let color of colors) {
	    console.log(color);
    } >> red, green, blue 출력



### for in문과 for of문 차이점
JavaScript에서 반복(iteration)을 처리하는 두 가지 방법입니다. 하지만 **사용 목적**과 **동작 방식**이 다릅니다.

| 특징 | for...in | for...of |
|--|--|--|
| 대상 | 객체의 가능한 모든속성 | 반복 가능한 객체 |
| 반복 값 | 속성의 키 | 반복 가능한 객체의 값 |
| 주요 사용 사례 | 객체의 속성 탐색 | 배열, 문자열 등 반복 가능한 객체 탐색 |
| 사용 가능한 객체 | 모든 객체 | 반복 가능한 객체만 (배열, 문자열, Map, Set 등) |
| Symbol.iterator* 필요 | 필요 없음 | 필요 (반복 가능한 객체는 `Symbol.iterator`를 구현) |

Symbol.iterator : **반복 가능한 프로토콜**의 핵심입니다. 기본 내장 객체 외에도, 사용자 정의 객체를 반복 가능하게 만들 때 유용합니다. 이를 통해 데이터를 더 직관적이고 효율적으로 순회할 수 있습니다. 자세한 사항은 [참고링크](https://ko.javascript.info/iterable) 에서 확인할 수 있습니다.

#### for ... in 문 배열값 예시

    let person = ["red", "green", "blue"];
    
    for (let key in person) {
	    console.log(key + ": " + person[key]);
    }
    >> key 값 인덱스로 대체
    >> "0: red","1: green","2: blue" 인덱스값으로 대체
    

#### for ... of 문 object값 예시
     let colors = { name: "John", age: 30, city: "New York" };
    
    for (let color of colors) {
	    console.log(color);
    } 
    >> 요류 
    >> Uncaught TypeError: colors is not iterable


> for ... in 문 은 객체에  for ... of 문 배열과 반복 가능한 객체에 사용 된다




## 제어문 while문
JavaScript에서 조건이 **참(true)**인 동안 계속 반복 실행되는 제어 구조입니다. 반복 횟수가 명확하지 않거나 조건에 따라 반복을 종료해야 할 때 주로 사용됩니다.

    while (condition) {
	    // 조건이 true인 동안 실행되는 코드
    }

반복이 실행되는 동안 평가되는 조건식. 참일 경우 블록 코드가 실행되며, 조건이 거짓(false)이 되면 반복이 종료됩니다.

    let i = 0;
    
    while (i < 5) {
	    console.log(i);
	    i++; // 조건을 업데이트하여 반복 종료를 보장
    } 
    
    >> 0, 1, 2, 3, 4 출력

#### 원하는 조건에 결과물 가져오기

    let i = 30;
    
    while (i % 7 !== 0) { >> i를 7로 나누어서 떨어질때 정지 
	    i++;
    } 
    console.log(i); 
    >> 35

#### 사용자 입력에 따른 반복

    let input;
    while (input !== "exit") {
	    input = prompt("Type 'exit' to stop:");
	    >> 사용자 입력을 받는다. 여기서 "exit"가 입력되면 중지
	    console.log(`You typed: ${input}`);
    }



## `break`와 `continue`
-   `break`: 루프를 완전히 종료.
-  `continue`: 현재 반복만 건너뛰고 다음 반복으로 이동.

----
### break 예시
    for (let i = 0; i < 10; i++) {
	     if (i === 5) {
		     break; // i가 5일 때 루프 종료
	     }
	     console.log(i);
     } >> 0, 1, 2, 3, 4 출력

### continue 예시

    for (let i = 0; i < 10; i++) {
	    if (i % 2 === 0) {
		    continue; // 짝수는 건너뛰기
	    }
	    console.log(i);
    } >> 1, 3, 5, 7, 9 출력




## 참고 문헌

 - [codeit](https://www.codeit.kr/) 
 - [chatgpt](https://chatgpt.com/) 