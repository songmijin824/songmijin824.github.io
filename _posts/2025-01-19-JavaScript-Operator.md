---
title: 연산자(Operator)
categories:
- 자바스크립트
feature_image: "https://picsum.photos/2560/600?image=872"
---

> 값을 연산하거나 조작하는 데 사용됩니다. 연산자는 크게 **산술 연산자**, **할당 연산자**, **비교 연산자**, **논리 연산자**, **비트 연산자**, **타입 연산자** 등으로 나뉩니다.

### 1. 산술 연산자 (Arithmetic Operators)

| 연산자 | 설명 | 예제 | 결과 |
|--|--|--|--|
| + | 덧셈 | 5 + 3 | 8 |
| - | 뺄셈 | 5 - 3 | 2 |
| * | 곱셈 | 5 * 3 | 15 |
| / | 나눗셈 | 6 / 3 | 2 |
| % | 나머지(모듈로) | 5 % 3 | 2 |
| ** | 거듭제곱 (ES6) | 2 ** 3 | 8 |

    console.log(5 + 3); // 8 
    console.log(5 - 3); // 2 
    console.log(5 * 3); // 15 
    console.log(5 / 3); // 1.6666666666666667
    console.log(5 % 3); // 2 
    console.log(2 ** 3); // 8

### 2. 복합 할당 연산자 (Assignment Operators)
| 연산자 | 설명 | 예제 | 결과 |
|--|--|--|--|
| = | 값 할당 | x = 10 | 10 |
| += | 더한 값을 할당 | x += 5 | x = x + 5 |
| -= | 뺀 값을 할당 | x -= 5 | x = x - 5 |
| *= | 곱한 값을 할당 | x *= 5 | x = x * 5 |
| /= | 나눈 값을 할당 | x /= 5 | x = x / 5 |
| %= | 나머지를 할당 | x %= 5 | x = x % 5 |
| **= | 거듭제곱 값을 할당 (ES6) | x **= 3 | x = x ** 3 |

    // 다음 두 줄은 같습니다
    x = x + 1;
    x += 1;
    
    // 다음 두 줄은 같습니다
    x = x + 2;
    x += 2;
    
    // 다음 두 줄은 같습니다
    x = x * 2;
    x *= 2;
    
    // 다음 두 줄은 같습니다
    x = x - 3;
    x -= 3;
    
    // 다음 두 줄은 같습니다
    x = x / 2;
    x /= 2;
    
    // 다음 두 줄은 같습니다
    x = x % 7;
    x %= 7;


### 3. 비교 연산자 (Comparison Operators)
| 연산자 | 설명 | 예제 | 결과 |
|--|--|--|--|
| == | 값이 같음 | 5 == "5" | true |
| === | 값과 타입이 모두 같음 | 5 === "5" | false |
| != | 값이 다름 | 5 != "5" | false |
| !== | 값 또는 타입이 다름 | 5 !== "5" | true |
| > | 크다 | 5 > 3 | true |
| < | 작다 | 5 < 3 | false |
| >= | 크거나 같다 | 5 >= 5 | true |
| <= | 작거나 같다 | 5 <= 4 | false |

### 4. 논리 연산자 (Logical Operators)
| 연산자 | 설명 | 예제 | 결과 |
|--|--|--|--|
| `&&`| AND (그리고) | true `&&` false | false |
| `||` | OR (또는) | true `||` false | true |
| `!` | NOT (부정) | `!`true | false |

    let a = true, b = false;
    console.log(a && b);  // false
    console.log(a || b);  // true
    console.log(!a);      // false

### 5. 비트 연산자 (Bitwise Operators)

> 비트 연산자는 숫자를 2진수로 변환하여 연산합니다.

| 연산자 | 설명 | 예제 | 결과 |
|--|--|--|--|
| `&` | AND | 5 & 1  | 1 |
| `|` | OR | 5`|`1 | 5 |
| `^` | XOR | 5 ^ 1 | 4 |
| `~` | NOT | ~5 | -6 |
| `<<` | 왼쪽 시프트 | 5 << 1 | 10 |
| `>>` | 오른쪽 시프트 | 5 >> 1 | 2 |

#### **비트 연산자 설명**

 `5 & 1` 을 계산할때

 1. 숫자를 이진수로 변환:
-   `5`는 이진수로 `0101`
-   `1`은 이진수로 `0001`
 2. 각 비트를 AND 연산:

         0101  (5)
         & 0001  (1)
         0001  (결과)

 3. 결과를 십진수로 변환:
     `0001`은 십진수로 `1`  >> 답은 1
     
    console.log(5 & 1); // 1

### 6. 타입 연산자 (Type Operators)

| 연산자 | 설명 | 예제 | 결과 |
|--|--|--|--|
| typeof | 데이터 타입 확인 | typeof "hello" | "string" |
| instanceof | 객체가 특정 클래스의 인스턴스인지 확인 | arr instanceof Array | true |

### 7. 삼항 연산자 (Ternary Operator)

> 삼항 연산자는 조건에 따라 값을 반환합니다.

    condition ? expr1 : expr2
    
    let age = 18;
    let status = (age >= 18) ? "성인" : "미성년자";
    console.log(status);  // "성인"

### 8. 기타 연산자

 - **쉼표 연산자 (Comma Operator)**: 여러 표현식을 평가한 후 마지막 값을 반환합니다

    let x = (1, 2, 3);
    console.log(x);  // 3

 - **전위/후위 증감 연산자 (`++`, `--`)**: 값을 1씩 증가 또는 감소시킵니다.
----
    // 다음 세 줄은 같은 의미입니다
    x = x + 1;
    x += 1;
    x++;
    
    // 다음 세 줄은 같은 의미입니다
    x = x - 1;
    x -= 1;
    x--;


## 연산자의 우선순위
링크참조 : [mozilla 연산자 우선순위](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Operators/Operator_precedence)


## 참고 문헌

 - [codeit](https://www.codeit.kr/) 
 - [chatgpt](https://chatgpt.com/) 