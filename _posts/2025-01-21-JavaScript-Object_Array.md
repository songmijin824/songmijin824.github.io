---
title: 객체와 배열의 차이 비교
categories:
- 자바스크립트
feature_image: "https://picsum.photos/2560/600?image=872"
---

객체는 **데이터의 관계를 나타내는 구조화된 정보**를 다룰 때 적합하고, 배열은 **순서가 중요한 데이터**를 다룰 때 유용합니다.

| 특징 | 객체 (Object) | 배열 (Array) |
|--|--|--|
| 구조 | 키-값 쌍으로 저장 | 순서대로 요소 저장 |
| 접근 방식 | 키(`key`)를 사용 | 인덱스(`index`)를 사용 |
| 순서 | 순서가 없음 | 순서가 중요 |
| 사용 목적 | 구조화된 데이터 표현 | 리스트나 순차적 데이터 표현 |
| 사용 예시 | 사용자 정보, 설정 | 숫자 목록, 문자열 리스트 |

#### 동적 길이

| 특징 | 객체 (Object) | 배열 (Array) |
|--|--|--|
| 길이 변경 | 속성을 동적으로 추가/삭제 가능 | 요소를 동적으로 추가/삭제 가능 |
| 길이 확인 | `Object.keys(obj).length` | `arr.length` |


### 유연성 및 사용 사례

----

#### 객체 (Object)
   -   사용자 정보 관리.
   -   설정값 저장.
   -   복잡한 데이터 구조 표현.

-----
    const user = { 
	    id: 123,
	    name: "John",
	    email: "john@example.com",
    };
    
----
#### 배열 (Array)
-   목록 처리(예: 숫자, 이름).
-   반복 작업이 필요한 데이터.

----

    const fruits = ["apple", "banana", "cherry"];

----



## 참고 문헌

 - [codeit](https://www.codeit.kr/) 
 - [chatgpt](https://chatgpt.com/) 