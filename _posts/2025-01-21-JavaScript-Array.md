---
title: 배열 (Array)
categories:
- 자바스크립트
feature_image: "https://picsum.photos/2560/600?image=872"
---

 1.   데이터를 **순서대로 저장**하는 **리스트**형 구조.
 2.   숫자 인덱스(0부터 시작)를 사용해 각 요소에 접근.
 3.   주로 **순서가 중요한 데이터**를 저장하는 데 사용.
 4.  사실, JavaScript에서 배열은 **객체**의 한 종류입니다. 배열의 인덱스는 객체의 속성처럼 취급됩니다.
 
----

    const numbers = [10, 20, 30, 40];
    console.log(numbers[1]); // 20
     
    const arr = [10, 20]; 
    console.log(arr[0]); // 10

#### 요소는 어떤 데이터 타입이든 저장 가능.

    const arr = ["apple", 42, true, { key: "value" }, [1, 2, 3]];

####  배열의 중첩 사용( 다차원배열 )

    const nestedArray = [[1, 2], [3, 4], [5, 6]];
    console.log(nestedArray[0]); // [1, 2]
    console.log(nestedArray[0][1]); // 2


####  배열의 요소 개수 _ length

    const fruits = ["apple", "banana", "cherry"];
    console.log(fruits.length); // 3


####  배열이 배열인지 확인 _ Array.isArray()

    console.log(Array.isArray(fruits)); // true
    console.log(Array.isArray({})); // false

#### ※ 주의사항
`delete` 키워드로 배열 요소를 삭제하면 **"빈 슬롯"**이 남습니다. 대신 `splice()`를 사용하는 것이 좋습니다.


### 1. 배열 리터럴 사용

#### `[]`를 사용해 생성

    const fruits = ["apple", "banana", "cherry"];
    console.log(fruits); // ["apple", "banana", "cherry"]

#### `new Array()` 생성자 사용

    const numbers = new Array(3, 5, 7);
    console.log(numbers); // [3, 5, 7]
    
    //하나의 숫자 인수를 전달하면 그 크기의 빈 배열을 생성합니다
    const emptyArray = new Array(5); 
    // 크기가 5인 빈 배열
    console.log(emptyArray); // [ <5 empty items> ]


### 2. 배열 불러오기
배열은 index(인덱스가 0부터 시작)로 값을 참조하여 불러온다.
이걸 인덱싱(indexing) 한다고 얘기한다.

    const fruits = ["apple", "banana", "cherry"];
    console.log(fruits[1]); // "banana"

### 3. 배열조작

#### 직접조작

    let fruits = ["apple", "banana"];
    
    fruits[1] = "cherry";
    console.log(fruits[1]); //"cherry"
    
    fruits[3] = "cherry";
    console.log(fruits); // ["apple", "banana","cherry"];
    
    fruits[4] = "cherry"; // ["apple", "banana", empty,"cherry"];

 

#### `push()`: 배열의 끝에 요소 추가

    const fruits = ["apple", "banana"];
    fruits.push("cherry");
    console.log(fruits); // ["apple", "banana", "cherry"]


#### `pop()`: 배열의 마지막 요소 제거

    const fruits = ["apple", "banana", "cherry"];
    const removed = fruits.pop();
    console.log(fruits); // ["apple", "banana"]
    console.log(removed); // "cherry"


#### `shift()`: 배열의 첫 번째 요소 제거

    const fruits = ["apple", "banana", "cherry"];
    const removed = fruits.shift();
    console.log(fruits); // ["banana", "cherry"]
    console.log(removed); // "apple"


#### `unshift()`: 배열의 시작에 요소 추가

    const fruits = ["banana", "cherry"];
    fruits.unshift("apple");
    console.log(fruits); // ["apple", "banana", "cherry"]


#### ★ `indexOf()`: 배열에서 특정 요소의 인덱스 찾기

    const fruits = ["apple", "banana", "cherry"];
    console.log(fruits.indexOf("banana")); // 1
    console.log(fruits.indexOf("grape")); // -1 (없으면 -1 반환)
    
#### ★ `lastindexOf()`: 배열에서 특정 요소의 뒤에서부터의 인덱스 찾기

    const fruits = ["apple", "banana", "cherry"];
    console.log(fruits.lastindexOf("apple")); // 3
    console.log(fruits.lastindexOf("grape")); // -1 (없으면 -1 반환)


#### ★ `splice()`: 배열에서 요소를 삭제하거나 추가 

    const fruits = ["apple", "banana", "cherry"];
    fruits.splice(1, 1); // 인덱스 1에서 1개의 요소 제거
    console.log(fruits); // ["apple", "cherry"]
    
    //새 요소를 추가할 수 있습니다.
    fruits.splice(1, 0, "orange"); 
    // 인덱스 1에 0개 삭제하면서 "orange" 추가
    console.log(fruits); // ["apple", "orange", "cherry"]

----

#### ★ `includes()`:  배열에서 특정 값이 있는지 확인하기

    const fruits = ["apple", "banana"];
    
    console.log(fruits.includes("banana")); // true
    console.log(fruits.includes("cherry")); //false

#### ★ `reverse()`:  배열 뒤집기

    let brands = ['Google', 'Kakao', 'Naver', 'Kakao'];
    console.log(brands);
    // (4) ["Google", "Kakao", "Naver", "Kakao"]
    
    brands.reverse();
    console.log(brands);
    // (4) ["Kakao", "Naver", "Kakao", "Google"]



#### `forEach()`: 배열의 각 요소에 대해 콜백 함수 실행

    const fruits = ["apple", "banana", "cherry"];
    fruits.forEach(fruit => console.log(fruit));
    // apple 
    // banana 
    // cherry


#### `map()`: 배열의 각 요소를 변환하여 새로운 배열 생성

    const numbers = [1, 2, 3, 4];
    const doubled = numbers.map(num => num * 2);
    console.log(doubled); // [2, 4, 6, 8]


#### `filter()`: 조건을 만족하는 요소들로 새로운 배열 생성

    const numbers = [1, 2, 3, 4, 5];
    const evenNumbers = numbers.filter(num => num % 2 === 0);
    console.log(evenNumbers); // [2, 4]


#### `reduce()`: 배열을 단일 값으로 축소

    const numbers = [1, 2, 3, 4];
    const sum = numbers.reduce((accumulator, currentValue) => accumulator + currentValue, 0);
    console.log(sum); // 10


#### `slice()`: 배열의 일부를 잘라내어 새로운 배열 반환

    const fruits = ["apple", "banana", "cherry", "date"];
    const slicedFruits = fruits.slice(1, 3); // 인덱스 1부터 3 직전까지
    console.log(slicedFruits); // ["banana", "cherry"]


#### `concat()`: 배열을 결합하여 새로운 배열 생성

    const fruits1 = ["apple", "banana"];
    const fruits2 = ["cherry", "date"];
    const combined = fruits1.concat(fruits2);
    console.log(combined); // ["apple", "banana", "cherry", "date"]


#### `join()`: 배열의 요소를 문자열로 결합

    const fruits = ["apple", "banana", "cherry"];
    const result = fruits.join(", ");
    console.log(result); // "apple, banana, cherry"



## 배열 메서드 요약

#### 1. 요소 추가 및 제거

-   **`push()`**: 배열 끝에 요소 추가.
-   **`pop()`**: 배열 끝에서 요소 제거.
-   **`unshift()`**: 배열 앞에 요소 추가.
-   **`shift()`**: 배열 앞에서 요소 제거.

#### 2. 배열 조작

-   **`splice()`**: 배열에서 요소를 추가, 제거, 교체.
-   **`slice()`**: 배열의 일부를 추출하여 새 배열 반환.

#### 3. 배열 병합 및 변환

-   **`concat()`**: 두 배열을 병합.
-   **`join()`**: 배열 요소를 문자열로 결합.
-   **`flat()`**: 중첩 배열을 평탄화.

#### 4. 검색 및 필터링

-   **`indexOf()`**: 요소의 첫 번째 인덱스 반환.
-   **`includes()`**: 요소 포함 여부 확인.
-   **`filter()`**: 조건을 만족하는 요소로 새 배열 생성.


#### 5. 순회

-   **`forEach()`**: 배열을 순회하며 함수 실행.
-   **`map()`**: 각 요소를 변환하여 새 배열 생성.

#### 6. 정렬

-   **`sort()`**: 배열 정렬.
-   **`reverse()`**: 배열 순서 반전.


## 배열 메서드 심화

#### 1. 고차 함수

-   배열 메서드는 함수를 인수로 받는 **고차 함수**를 자주 사용합니다.

----

    const nums = [1, 2, 3, 4];
    const doubled = nums.map((num) => num * 2); 
    // [2, 4, 6, 8]
    
----

#### 2. 구조 분해

-   배열을 쉽게 해체하여 변수에 할당.

----
    const arr = [1, 2, 3];
    const [a, b, c] = arr;
    console.log(a, b, c); // 1, 2, 3
----

#### 3. 스프레드 연산자

-   배열을 복사하거나 병합할 때 사용.

----


    const arr1 = [1, 2];
    const arr2 = [...arr1, 3, 4]; // [1, 2, 3, 4] 

----

[[기타 메소드 참고]](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array)

----



## 참고 문헌

 - [codeit](https://www.codeit.kr/) 
 - [chatgpt](https://chatgpt.com/) 