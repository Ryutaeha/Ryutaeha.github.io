---
title: C# 기초 문법 - 기본문법과 변수,자료형, 형변환
date: 2023-10-07 00:00:00 +0900
categories: [C#, variable]
tags: [C#, Tutorial, Visual Studio 2022, variable]
img_path: /assets/img/cs/
---

이 게시물은 C# 공부과정을 정리해놓은 것입니다
사용하는 툴은 Visual Studio 2022 입니다.
해당 툴을 사용하는 이유는 추후에 다룰 Unity에서 연계하여 사용하기 위함입니다.

> C#에 대한 더 많은 포스팅은 `CATEGORIES`의 <a href ="https://ryutaeha.github.io/categories/c/">`C#`</a>을 확인하세요.
 {: .prompt-tip }

 <br>
 오늘은 기본 문법에 대해 알아보겠습니다.
 <br> 
 제일 기초로 콘솔창에 `Hello, world!`를 출력해보겠습니다.
 <br>

> 많은 프로그래밍의 첫 예제는 보통 `Hello, world!`를 출력하는것이다.
> <br> `"The C Programming Language"`라는 책의 첫 예제가 `Hello, world!`를 출력하는 것으로 부터 유래되어서 하나의 암묵적인 룰이 되었다.
 {: .prompt-tip }

## 콘솔창에 출력하기

```
Console.Write("Hello, world!");

Console.WriteLine("Hello, world!");

```

이제 실행을 해줍시다.
<br>
아래 사진에 빨간 표시를 클릭해줍니다.

> 단축키는 키보드의 `F5`
 {: .prompt-tip }

![Desktop View](variable-1.png)

성공적으로 실행이 되었다면 콘솔창이 새로 뜹니다.
<br>

![Desktop View](variable-2.png)

눈치 빠르신 분들은 여기에서 무언가를 눈치 채실겁니다.
<br>
나는 분명 2줄로 적었는데 왜 한줄로 뜨지? 라고 말입니다.
<br>
<br>
그 이유는 `Console.Write()`뒤에 붙은 `Line`유무 차이입니다 `Line`을 뒤에 붙이면 해당 명령어 출력후 자동 줄바꿈이 실행됩니다.
<br>
`Console.WriteLine("Hello, world!");`를 위에 두고 출력을 하시면 두줄로 출력됩니다.

![Desktop View](variable-3.png)

> 만약 `Console.Write();`에서 줄바꿈을 원할때나 중간에 줄바꿈이 필요할 시 해당 문자열 뒤에 `\n`을 추가해주면 된다.
> <br> 예) `Console.Write("Hello, world!\n");`
 {: .prompt-tip }

## 변수와 자료형

### 변수란

변수란 하나의 값을 저장할수 있는 저장공간이라고 생각하시면 됩니다. 저장된 값을 한번이 아닌 여러번 사용하기 용이합니다
<br>
또한 각 변수별로 하나 이상의 변수는 저장할수 없습니다.
<br>
변수에는 `변수의 자료형`에 맞는 값을 넣어야 사용이 가능합니다.

> <a href="#변수의-자료형">변수의 자료형</a>에 대한 내용은 해당 포스트 하단에 서술할 예정
 {: .prompt-info }

### 변수의 선언

변수의 선언은 `변수의 자료형` `변수의 이름`;으로 합니다.

```
String testString;

int testInt;

```

이렇게 한다면 `testString`, `testInt`라는 변수가 생성이 된 겁니다.
<br>
<br>
하지만 이렇게만 사용한다면 해당 변수에는 쓰레기값(의미없는 값)이 들어가 있습니다.
<br>
해당 변수들을 사용하려면 값을 대입해 초기화를 해줘야 합니다.

### 변수 초기화

![Desktop View](variable-4.png){: width="972" height="589" }

사진과 같이 해당 문자열과 숫자는 빨간줄`(ERROR)`을 만들며 혼자서 사용할수 없습니다.
<br>
해당 문자열과 숫자를 사용하기 위해서는 변수에 대입해 변수를 초기화해 사용해야 합니다.
<br>
<br>
변수를 초기화 하는 방법에는 크게 2가지가 있습니다.

- 변수 선언 후 초기화

```
String testString;

int testInt;

testString = "Hello, world";

testInt = 2023;
```

- 변수 선언과 함께 초기화

```
String testString = "Hello, world";

int testInt = 2023;
```

> 변수의 이름을 선언할 때는 카멜표기법을 따른다.
> <br>카멜표기법이란 이름을 띄어쓰기 없이 짓기 위하여 따르는 관례인 네이밍컨벤션(Naming convention)
> <br> 단어 전체적으로 소문자를 사용하지만, 맨 첫 글자를 제외한 각 합성어의 첫 글자만 대문자로 표기한다.
 {: .prompt-danger }

### 변수의 활용과 수정

이제 한번 초기화한 변수를 활용해보고 수정해보겠습니다.
<br>
변경하는 부분에서 `Console.ReadLine();`를 같이 사용해서 해보겠습니다.
<br>
`Console.ReadLine();`는 사용자가 입력하는 값을 받는 명령어입니다.

```
String testString = "Hello, world"; //testString 선언과 초기화
int testInt = 2023; //testInt 선언과 초기화

//각 변수 변경전 값 출력
Console.WriteLine(testString);
Console.WriteLine(testInt);

//testString Console.ReadLine()를 사용하여 값 입력받아 변경
Console.Write("변경할 값을 입력하세요 : ");
testString= Console.ReadLine();

//testInt값을 2023에서 1234로 변경
testInt = 1234;

//변경된 각 변수를 출력
Console.WriteLine(testInt);
Console.WriteLine(testString);

```

위에 코드를 실행했을 경우 이런 콘솔창이 뜹니다.

![Desktop View](variable-5.png)

현재의 상태는 `변경할 값을 입력하세요 :` 뒤에 커서가 계속 깜빡이며 사용자의 입력을 기달리고 있는 상태입니다
<br>
<br>
여기에 저는 `안녕하세요`란 값을 주었습니다.

![Desktop View](variable-6.png)
분명 같은 `Console.WriteLine(testInt);` `Console.WriteLine(testString);` 출력문이지만 변수가 수정이 되어 값이 변하였습니다.
<br>
하지만 수정된 변수는 프로그램이 다시 시작할 때 코드는 첫줄부터 실행이 되므로 `String testString` 는 "Hello, world", `int testInt` 는 2023이 됩니다.

> `Console.WriteLine`과 `Console.ReadLine`이 헷갈린다면 컴퓨터=Console이라고 생각하면 쉽다.
> <br> `Console.WriteLine`는 컴퓨터가 쓴다.
> <br> `Console.ReadLine`는 컴퓨터가 읽는다.
 {: .prompt-tip }

### 변수의 자료형

| 자료형  | 범위                                                   | 크기               | 유의점                            |
| :------ | :----------------------------------------------------- | :----------------- | :-------------------------------- |
| sbyte   | -128 ~ 127                                             | 1 byte             | 정수형, 실수는 사용할수 없음      |
| byte    | 0 ~ 255                                                | 1 byte             | 정수형, 실수는 사용할수 없음      |
| short   | -32,768 ~ 32,767                                       | 2 byte             | 정수형, 실수는 사용할수 없음      |
| ushort  | 0 ~ 65,535                                             | 2 byte             | 정수형, 실수는 사용할수 없음      |
| int     | -2,147,483,648 ~ 2,147,483,647                         | 4 byte             | 정수형, 실수는 사용할수 없음      |
| uint    | 0 ~ 4,294,967,295                                      | 4 byte             | 정수형, 실수는 사용할수 없음      |
| long    | -9,223,372,036,854,775,808 ~ 9,223,372,036,854,775,808 | 8 byte             | 정수형, 실수는 사용할수 없음      |
| ulong   | 0 ~ 18,446,744,073,709,551,615                         | 8 byte             | 정수형, 실수는 사용할수 없음      |
| float   | ±1.5e-45 ~ ±3.4e38                                     | 4 byte             | 실수형, 값 뒤에 f를 붙여야합니다  |
| double  | ±5.0e-324 ~ ±1.7e308                                   | 8 byte             | 실수형, 갑 뒤에 b를 붙여야 합니다 |
| decimal | ±1.0 × 10−28 ±7.9 × 1028                               | 16 byte            | 실수형                            |
| char    | U+0000 ~ U+ffff                                        | 2 byte             | ''로 감싸야합니다                 |
| string  |                                                        | 크기가 수시로 변함 | ""로 감싸야합니다                 |
| bool    | true 또는 false                                        | 16 byte            |  보통 논리 연산의 결과로 얻게 됩니다                                 |

> double형은 뒤에 b를 붙이지 않아도 double로 인식한다.
  {: .prompt-info }

## 변수의 형변환

마지막으로 변수의 형변환에 대해 알아보겠습니다.

### 형변환이란?

형변환이란 변수의 자료형을 다른 형태의 자료형으로 변경하는 것을 말합니다.

### 형변환(숫자 -> 숫자)

예를 들어 `float` -> `int`, `int` -> `float`를 변경하는 걸로 예를 들어보겠습니다.

<h3 data-toc-skip>`float` -> `int`</h3>

```
int x = 10;
float y = 10.0f;

int z = x + (int)y; // 자료형이 다른 변수 앞에 사용할 자료형을 명시
```

<h3 data-toc-skip>`int` -> `float`</h3>

```
int x = 10;
float y = 10.0f;

float z = (float)x + y; // 자료형이 다른 변수 앞에 사용할 자료형을 명시
```

> 변경할 데이터의 손실이 없는 경우 자료형을 명시하지 않아도 캐스팅이 가능하다.
> 즉 변경할 자료형의 범위가 더 큰 경우에는 하지 않아도 된다.
> <br>
>
> <h3 data-toc-skip>예)</h3>
>
> ```
> int x = 10;
> float y = 10.0f;
> float z = x + y; // 가능
> ```
>
 {: .prompt-tip }

### 형변환(다른 자료형 -> 문자)

숫자나 bool타입을 문자로 바꾸는 방법입니다.
해당 변수 뒤에 .ToString()을 붙이면 변환이 됩니다.

```
int x = 10;
string xStr = x.ToString(); // "10"

float y = 10.5f;
string yStr = y.ToString(); // "10.5"

bool myBool = true;
string boolStr = myBool.ToString(); // "true"
```

### 형변환(문자 -> 다른 자료형)

문자를 다른 자료형으로 바꾸는 방식은 많은 방식이 있습니다.
하지만 이 포스팅에서는 2가지의 방법을 소개하겠습니다.

<h3>Convert 클래스</h3>
convert를 이용하여 상응하는 자료형으로 변환하는 방법입니다.

```
string iStr = "10";
int x;
x = Convert.ToInt32(iStr); // x : 10

string bStr = "true";
bool b;
b = Convert.ToBoolean(bStr); // b : true
```

<h3>Parse() 함수</h3>

```
string iStr = "10";
int x;
x = int.Parse(iStr); // x : 10

string bStr = "true";
bool b;
b = bool.Parse(bStr); // b : true
```

> 자료형을 변환할때는 변환되는 자료형에 맞지 않는 값이 들어가면 에러가 발생하게 된다.
 {: .prompt-warning }

<br>
<br>

기본 문법, 변수와 자료형과 형변환에 대해 알아봤습니다.
<br>
다음 포스팅은 연산자에 대해 알아보겠습니다.

