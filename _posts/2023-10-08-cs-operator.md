---
title: C# 기초 문법 - 연산자
date: 2023-10-08 00:00:00 +0900
categories: [C#, variable]
tags: [C#, Tutorial, Visual Studio 2022, variable]
img_path: /assets/img/
---

이 게시물은 C# 공부과정을 정리해놓은 것입니다
사용하는 툴은 Visual Studio 2022 입니다.
해당 툴을 사용하는 이유는 추후에 다룰 Unity에서 연계하여 사용하기 위함입니다.

> C#에 대한 더 많은 포스팅은 `CATEGORIES`의 <a href ="https://ryutaeha.github.io/categories/c/">`C#`</a>을 확인하세요.
 {: .prompt-tip }

## 산술 연산

산술연산에는 몇가지가 있습니다.

### `+`(더하기) 연산

```
int x = 1;
int y;
y = x + 1;

Console.WriteLine(y); //2를 출력
```

![Desktop View](test.png)

### `-`(빼기) 연산

```
int x = 10;
int y;
y = x - 5;

Console.WriteLine(y); //5를 출력
```

![Desktop View](test.png)

### `*`(곱하기) 연산

```
int x = 2;
int y;
y = x * 5;

Console.WriteLine(y); //10를 출력
```

![Desktop View](test.png)

### `/`(몫), `%`(나머지) 연산

나눗셈은 해당 하는 변수의 범위로 계산이 됩니다.
<br>
`int x = 10` 일 때
<br>
x / 3 은 3.333333...이 아닌 3과 나머지 1로 계산되며 몫 계산시 나머지는 나오지 않습니다.
<br>
나머지 계산시에도 마찬가지로 몫은 나오지 않습니다.

```
// 몫 연산
int x = 10;
int y;
y = x / 3;

Console.WriteLine(y); //3를 출력
```

```
// 나머지 연산
int x = 10;
int y;
y = x % 3;

Console.WriteLine(y); //1를 출력
```

![Desktop View](test.png)

### (`++`,`--`)증감 연산

해당 연산자는 1씩 증가, 감소를 합니다.

<br>
<br>
해당 코드를 예시로 설명해보겠습니다.

```
int x = 1;
x = x+1;
Console.WriteLine(x); //2를 출력
```

해당 코드를 `++`연산자로 바꿔보겠습니다.

```
int x = 1;
x++;

Console.WriteLine(x); //2를 출력
```

`++` 연산자는 `x = x + 1`이라고 생각하시면 됩니다.
<br>
또한 해당 값을 변수에 할당하지 않아도 해당 값이 유지됩니다.

```
int x = 1;

Console.WriteLine(x+1); //2를 출력
Console.WriteLine(x); //1를 출력

x++;
Console.WriteLine(x); //2를 출력
```

![Desktop View](test.png)

### 전위연산 후위 연산

증감 연산은 변수 앞 또는 뒤에 붙일 수 있습니다.

```
int x = 5;

x++;
++x;
```

그에 따른 작업이 다릅니다.

앞에 붙으면 `;`(세미콜론)을 기준으로 각 라인을 실행할 때 값이 증가 후 실행됩니다.

뒤에 붙으면 `;`(세미콜론)을 기준으로 각 라인이 실행 된 후 값이 증가됩니다.

```
int x = 5;
Console.WriteLine(x); //5를 출력
Console.WriteLine(++x); //6를 출력

int y = 5;

Console.WriteLine(y++); //5를 출력
Console.WriteLine(y); //6를 출력
```

![Desktop View](test.png)

### 문자열 연산

문자열 연산은 `+` 사용이 가능합니다.

문자열 변수와 문자열 변수의 연산

```
string str1 = "Hello";
string str2 = "world!";

string str3 = str1+str2;
Console.WriteLine(str3); //Helloworld! 출력
```

문자열 변수와 문자열데이터의 연산

```
string str1 = "Hello";

string str3 = str1+"world!";
Console.WriteLine(str3); //Helloworld! 출력
```

문자열과 숫자 연산

```
string year = 2023;

Console.WriteLine("Hello!"+year); //Hello!2023 출력
```

> 숫자와 문자열이 연산되면 해당 숫자는 문자열 취급으로 바뀜
 {: .prompt-info }
> ![Desktop View](test.png)

## 논리 연산

논리 연산이란 논리적 판단을 하는 연산자 입니다.
결과값은 bool 타입으로 true, false 타입으로만 반환됩니다.
![Desktop View](test.png)

### 같음 연산자

서로의 값이 같은지 다른지 체크하는 연산자입니다.
<br>
보통 같이 같은지 다른지 는 `=`, `≠`이 두가지를 씁니다.
<br>
하지만 `=`은 값을 대입할 때 사용하는 기호입니다. 또한 `≠`은 타이핑하기가 힘듭니다.
<br>
그래서 C#에서는 `=`는 `==`, `≠`= `!=`으로 표현합니다.

```
int x = 10;

bool result1 = x==10;
// result = true

bool result2 = x!=10;
// result = false
```

![Desktop View](test.png)

### 비교 연산자

비교 연산자는 서로의 값이 큰지 작은지를 비교하는 연산자 입니다.
<br>
크다의 부호는 `<` 크거나 같다의 부호는 `≤`입니다.
<br>
크다의 부호는 입력하기 쉽지만 크거나 같다의 부호는 `≠`와 마찬가지로 타이핑하기가 쉽지 않습니다.
<br>
그래서 C#에서는 `<` 는 같게 `<`, `≤`는 `<=`로 작성합니다.
<br>
반대의 경우도 같습니다 `>`,`>=`로 작성합니다.

```
int x = 10;

bool result1 = x<=15;
// result = true

bool result2 = x<7;
// result = false
```

![Desktop View](test.png)

## 조건부 논리 연산

같음, 비교 연산자와 비슷하지만 조건을 비교하는 연산자 입니다.
![Desktop View](test.png)

### `&&`연산자(AND 연산자)

`조건1` && `조건2`라고 했을 때 해당 조건들이 true면 true를 반환합니다.

```
int x = 10;
int y = 20;

bool result1 = x==10 && y==20;
// 조건 1 true, 조건 2 true, result1 = true

bool result2 = x==1 && y==20;
// 조건 1 false,조건 2 true, result2 = false

bool result3 = x==1 && y==2;
// 조건 1 false,조건 2 false, result2 = false
```

![Desktop View](test.png)

### `||`연산자(or 연산자)

`조건1` \|\| `조건2`라고 했을 때 해당 조건들중 하나라도 true면 true를 반환합니다.

```
int x = 10;
int y = 20;

bool result1 = x==10 || y==20;
// 조건 1 true, 조건 2 true, result1 = true

bool result2 = x==1 || y==20;
// 조건 1 false,조건 2 true, result2 = true

bool result3 = x==1 || y==2;
// 조건 1 false,조건 2 false, result2 = false
```

![Desktop View](test.png)

## 비트 연산

컴퓨터란 0과 1로 이루어진 것은 대부분이 아실겁니다.
<br>
0 또는 1 이걸 비트라고 합니다.
<br>
이걸 사용하여 연산을 하는 것이 비트 연산입니다.
<br>
비트가 너무 많으면 보기에 불편하므로 10과 3을 8 비트로 바꿔 설멍하겠습니다.
![Desktop View](test.png)

### `&`(AND 연산자)

조건부 논리연산에 적어놓은 `&&`와 같습니다.

| 값  | 비트        |                                                |
| :-- | :---------- | :--------------------------------------------- |
| 10  | `0000 1010` |                                                |
| 3   | `0000 0011` |                                                |
| 2   | `0000 0010` | 두 비트의 같은 위치의 값이 둘다 1인것만 1 반환 |

![Desktop View](test.png)

### `|`(OR 연산자)

조건부 논리연산에 적어놓은 `||`와 같습니다.

| 값  | 비트        |                                                       |
| :-- | :---------- | :---------------------------------------------------- |
| 10  | `0000 1010` |                                                       |
| 3   | `0000 0011` |                                                       |
| 11  | `0000 1011` | 두 비트의 같은 위치의 값이 둘중 하나라도 1이면 1 반환 |

![Desktop View](test.png)

### `^`(XOR 연산자)

| 값  | 비트        |                                          |
| :-- | :---------- | :--------------------------------------- |
| 10  | `0000 1010` |                                          |
| 3   | `0000 0011` |                                          |
| 9   | `0000 1001` | 두 비트의 같은 위치의 값이 다르면 1 반환 |

![Desktop View](test.png)

### `<<`(SHIFT 연산자)

`<<`연산자는 `비트의 값`<<`이동할 수`로 적으며 1인 비트만 `이동할 수`만큼 `<<`방향을 이동합니다
<br>
물론 반대도 가능합니다.

| 값  | 비트        | SHIFT 연산자 | 변경된 값 | 변경된 비트 |
| :-- | :---------- | :----------- | --------- | ----------- |
| 10  | `0000 1010` | 10<<2        | 40        | `0010 1000` |
| 10  | `0000 1010` | 10>>1        | 5         | `0000 0101` |
| 10  | `0000 1010` | 10>>2        | 2         | `0000 0010` |

> 비트 연산을 하다 비트가 범위를 벗어나 넘어가 버린다면 넘어간 데이터는 그대로 사라짐
 {: .prompt-warning }

연산자에 대해 알아봤습니다.
<br>
다음 포스팅은 제어문에 대해 알아보겠습니다.
