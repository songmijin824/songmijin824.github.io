---
title:  javascript 자료형 문자 심화
categories:
- 자바스크립트
feature_image: "https://picsum.photos/2560/600?image=872"
---

### 1. 문자열 활용

#### 문자의 길이 length

    const str = "banana";
    console.log(str.length); // 6
    
----
#### 문자열 검색 관련 메서드
문자열은 배열과 같은 방식으로 접근할 수 있다. 

 - ★ indexOf() : 특정 문자열이 처음 등장하는 **인덱스**를 반환합니다. 찾지 못하면 `-1`을 반환
 - ★ lastIndexOf() : 특정 문자열이 **마지막으로 등장**하는 인덱스를 반환
 - includes() : 특정 문자열이 포함되어 있는지 **불리언 값**을 반환
 - startsWith(): 문자열이 특정 값으로 **시작**하는지 확인
 - endsWith(): 문자열이 특정 값으로 **끝나는지** 확인

----
    /////////////////  indexOf()
    const str = "Hello, world!";
    console.log(str.indexOf("world")); // 7
    console.log(str.indexOf("JavaScript")); // -1
    
    ///////////////// lastIndexOf()
    const str = "banana";
    console.log(str.lastIndexOf("a")); // 5
    console.log(str.lastIndexOf("z")); // -1
    
    ///////////////// includes()
    const str = "JavaScript is fun!";
    console.log(str.includes("fun")); // true
    console.log(str.includes("hard")); // false
    
    /////////////////  startsWith()
    const str = "Hello, world!";
    console.log(str.startsWith("Hello")); // true
    console.log(str.startsWith("world")); // false
    
    ///////////////// endsWith()
    const str = "JavaScript is fun!";
    console.log(str.endsWith("fun!")); // true
    console.log(str.endsWith("JavaScript")); // false


----

#### 문자열 추출 및 조작 메서드

 - slice(): 문자열의 일부를 **추출**하여 반환
 - substring() : 문자열의 일부를 **추출**합니다. `slice()`와 유사하지만, 음수 인덱스를 사용할 수 없습니다.
- substr() : 문자열에서 지정한 **길이만큼** 추출
- replace() : 특정 부분을 다른 문자열로 **대체**기본적으로 첫 번째 등장만 대체합니다.
- replaceAll() : 모든 매칭되는 문자열을 대체

----

    ///////////////// slice()
    const str = "JavaScript";
    console.log(str.slice(0, 4)); // "Java"
    console.log(str.slice(4)); // "Script"
    console.log(str.slice(-6)); // "Script" (음수는 끝에서부터 시작)
    
    ///////////////// substring()
    const str = "JavaScript";
    console.log(str.substring(0, 4)); // "Java"
    console.log(str.substring(4)); // "Script"
    
    ///////////////// substr()
    const str = "JavaScript";
    console.log(str.substr(0, 4)); // "Java"
    console.log(str.substr(4, 6)); // "Script"
    
    ///////////////// replace()
    const str = "Hello, world!";
    console.log(str.replace("world", "JavaScript")); // "Hello, JavaScript!"
    
    const str = "apples, bananas, cherries";
    console.log(str.replace(/a/g, "A")); // "Apples, bAnAnAs, cherries"
    
    /////////////////  replaceAll()
    const str = "apples, apples, apples";
    console.log(str.replaceAll("apples", "oranges")); // "oranges, oranges, oranges"

----
#### 문자열 변환 메서드

 - ★ toUpperCase() : 문자열을 **대문자**로 변환
 - ★ toLowerCase() : 문자열을 **소문자**로 변환

 ----

    ///////////////// toUpperCase()
    const str = "hello";
    console.log(str.toUpperCase()); // "HELLO"
    
    ///////////////// toLowerCase()
    const str = "HELLO";
    console.log(str.toLowerCase()); // "hello"

----
#### 문자열 분리 및 결합 메서드

 - split() : 문자열을 특정 구분자로 **나눠서 배열**로 반환
 - concat() : 문자열을 **연결**합니다.

----
    ///////////////// split()
    const str = "apple, banana, cherry";
    console.log(str.split(", ")); // ["apple", "banana", "cherry"]
    
    ///////////////// concat()
    const str1 = "Hello";
    const str2 = "World";
    console.log(str1.concat(", ", str2, "!")); // "Hello, World!"


#### 문자열 공백 처리 메서드

 - trim() : 문자열의 **양쪽 공백**을 제거
 - trimStart() : 문자열의 **앞쪽 공백**을 제거
 - trimEnd() : 문자열의 **뒤쪽 공백**을 제거

----
    ///////////////// trim()
    const str = "   Hello, world!   ";
    console.log(str.trim()); // "Hello, world!"
    
    ///////////////// trimStart()
    const str = "   Hello!";
    console.log(str.trimStart()); // "Hello!"
    
    ///////////////// trimEnd()
    const str = "Hello!   ";
    console.log(str.trimEnd()); // "Hello!"


#### 기타 유용한 메서드

 - ★ charAt() : 주어진 인덱스에 해당하는 문자를 반환
 - charCodeAt() :  특정 인덱스의 문자의 유니코드(코드 포인트)를 반환
 - repeat() : 문자열을 지정된 횟수만큼 반복하여 연결한 결과를 반환
 - padStart() : 문자열의 앞쪽을 지정된 길이만큼 채웁니다.
 - padEnd() : 문자열의 뒤쪽을 지정된 길이만큼 채웁니다.


----
      ///////////////// charAt()
      const str = "JavaScript";
      console.log(str.charAt(4)); // "S"
      
      //인덱스를 활용하면 아래와같이 간단히 표현할 수 있다.
      console.log(str[4]); // "S"
      
      ///////////////// charCodeAt()
      const str = "A";
      console.log(str.charCodeAt(0)); // 65
      
      ///////////////// repeat()
      const str = "Hi ";
      console.log(str.repeat(3)); // "Hi Hi Hi "
      
      ///////////////// padStart()
      const str = "5";
      console.log(str.padStart(3, "0")); // "005"
      
      ///////////////// padEnd()
      const str = "5";
      console.log(str.padEnd(3, "0")); // "500"




## 참고 문헌

 - [codeit](https://www.codeit.kr/) 
 - [chatgpt](https://chatgpt.com/) 