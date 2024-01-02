---
title: C# 기초 문법 - 제어문
date: 2023-10-09 00:00:00 +0900
categories: [C#, control flow statements]
tags: [C#, Tutorial, Visual Studio 2022, control flow statements]
img_path: /assets/img/
---

이 게시물은 C# 공부과정을 정리해놓은 것입니다
사용하는 툴은 Visual Studio 2022 입니다.
해당 툴을 사용하는 이유는 추후에 다룰 Unity에서 연계하여 사용하기 위함입니다.

> C#에 대한 더 많은 포스팅은 `CATEGORIES`의 <a href ="https://ryutaeha.github.io/categories/c/">`C#`</a>을 확인하세요.
{: .prompt-tip }

## 제어문이란

제어문은 코드를 지정한 조건에 따라 실행하거나 반복 실행을 할때 사용됩니다.
<br>
<br>
일반적으로 위에서 아래로 실행되는 코드에 영향을 주고 경우에 따라 코드의 실행순서를 인위적으로 변경이 가능합니다.

> 제어문에 활용되는 조건들은 논리연산으로 계산됨 <br>
> 논리연산에 대한 내용은 <a href="https://ryutaeha.github.io/posts/cs-operator/#%EB%85%BC%EB%A6%AC-%EC%97%B0%EC%82%B0">여기</a>를 참조
{: .prompt-info }

![Desktop View](test.png)

## 조건문

조건문이란 어떠한 특정한 조건이 주어졌을 때 해당 조건의 만족 여부에 따라 코드를 선택적으로 실행할 때 사용하는 코드 입니다.

> 조건문에 활용되는 조건들은 조건부 논리연산을 사용할 수 있음 <br>
> 조건부 논리연산에 대한 내용은 <a href ="https://ryutaeha.github.io/posts/cs-operator/#%EC%A1%B0%EA%B1%B4%EB%B6%80-%EB%85%BC%EB%A6%AC-%EC%97%B0%EC%82%B0">여기</a>를 참조
{: .prompt-info }

![Desktop View](test.png)

### if

if문은 조건을 체크해서 만족하면 중괄호 `{}`안에 있는 코드를 실행합니다.
<br>
조건을 만족하지 않으면 실행되지 않습니다.

```
int x = 5;

if(x > 1)
{
    // x는 1보다 크기에 조건을 만족 - 실행
    Console.WriteLine("조건이 참이면 실행됩니다. 조건 : x > 1");
}

if(x > 10)
{
    // x는 10보다 작기에 조건을 만족하지 못함 - 실행 안됨
    Console.WriteLine("조건이 참이면 실행됩니다. 조건 : x > 10");
}
```

![Desktop View](test.png)

### else if

쉽게 생각하시면 if문의 연장선이라고 생각하시면 됩니다.
<br>
혼자서는 사용할수 없고 if문뒤에 따라 붙습니다.
<br>
if가 거짓이면 바로 아래의 else if문의 조건으로 다시 체크합니다.
<br>
else if문은 하나가 아닌 여러개가 올수 있습니다.
<br>
조건문의 위부터 체크하며 하나의 조건문이 실행될시 해당 조건문 아래의 조건문들은 전부 실행되지 않습니다.

```
int x = 5;

if(x > 10)
{
    // x는 10보다 작기에 조건을 만족하지 못함 - 실행 안됨
    Console.WriteLine("조건이 참이면 실행됩니다. 조건 : x > 10");
}else if(x > 1)
{
    // x는 1보다 크기에 조건을 만족 - 실행
    Console.WriteLine("조건이 참이면 실행됩니다. 조건 : x > 1");
}else if(x > 3)
{
    // 조건은 만족하나 위에 실행이 된 조건문이 있음 - 실행 안됨
    Console.WriteLine("조건이 참이면 실행됩니다. 조건 : x > 3");
}

```

![Desktop View](test.png)

### else

else if문과 비슷하지만 하나의 if에는 하나의 else만 올수 있습니다.
<br>
else if문은 조건이 있어야 하지만 else문은 조건이 따로 없습니다.
<br>
해당 조건문에 모든 조건이 맞지 않을 때 실행됩니다.

```
int x;
Console.Write("숫자를 입력해주세요 : ");
x = int.Parse(Console.ReadLine());

if (x < 10)
{
    Console.WriteLine("조건이 참이면 실행됩니다. x는 10보다 작습니다.");
}
else if (x < 50)
{

    Console.WriteLine("조건이 참이면 실행됩니다. x는 50보다 작습니다.");
}
else if (x < 100)
{

    Console.WriteLine("조건이 참이면 실행됩니다. x는 100보다 작습니다.");
}
else
{
    //if문과 모든 else if문이 거짓일 때 실행
    Console.WriteLine("이 수는 100을 넘습니다.");
}
```

해당 코드를 실행하면 이런 화면이 나옵니다.
![Desktop View](cs/control1.png)

100이하의 임의의 수를 입력해주면 조건문에 해당하는 코드가 실행됩니다.
<br>
저는 56을 입력해보겠습니다.

![Desktop View](cs/control2.png)

그럼 이제 100이상의 수를 입력하면 어떻게 될까요?

![Desktop View](cs/control3.png)

조건문이 다 맞지를 않으니 else문이 실행되었습니다.

### switch case

변수 한개를 가지고 변수가 무엇인지 확인하는 조건문입니다.
<br>
if문을 활용하여 대체 할수 있지만 같은 변수를 사용할 때에 가독성 측면과 속도 측면에서 더 좋은 편입니다.

- case에 들어가는 조건은 고정된 상수여야합니다.
  - 가능한 값
    1. 1,2,3 등: 고정된 값
  - 불가능한 값
    1. x > 10 : 변할수 있는 값
    2. int a등 새로 선언한 변수
- case에 들어가는 변수는 중복 사용이 안됩니다.

```
int x;
Console.Write("숫자를 입력해주세요 : ");
x = int.Parse(Console.ReadLine());

switch (x)
{
    case 0: //0을 입력했을 시 실행
        Console.WriteLine("0번입니다.");
        break;
    case 1: //1을 입력했을 시 실행
        Console.WriteLine("1번입니다.");
        break;
    case 2: //2를 입력했을 시 실행
        Console.WriteLine("2번입니다.");
        break;
    default: //그 외의 숫자를 입력했을 시 실행
        Console.WriteLine("0~2번을 입력해주세요!");
        break;
}
```

1을 입력했을 때 입니다.
![Desktop View](cs/control4.png)

0~2가 아닌 숫자를 입력했을 때입니다.
![Desktop View](cs/control5.png)

### switch case문에서의 break

각 구문을 종료할 때 `break`를 넣어서 사용합니다.
<br>
switch case문

```
int x;
Console.Write("숫자를 입력해주세요 : ");
x = int.Parse(Console.ReadLine());

switch (x)
{
    case 0: //0을 입력했을 시 실행
        Console.WriteLine("0번입니다.");
        break; // 구문 종료 break;

    case 1: //1을 입력했을 시 실행
        Console.WriteLine("1번입니다.");
        break; // 구문 종료 break;

    case 2: //2를 입력했을 시 실행
        Console.WriteLine("2번입니다.");
        break; // 구문 종료 break;

    default: //그 외의 숫자를 입력했을 시 실행
        Console.WriteLine("0~2번을 입력해주세요!");
        break; // 구문 종료 break;
}
```

![Desktop View](test.png)

## 반복문

어떠한 일들을 반복적으로 수행할 때 사용합니다.
<br>
해당 조건이 true(참)이면 수행됩니다.

![Desktop View](test.png)

### for

for(`초기화` : `조건` : `변화`)
{
`실행할 코드`
}로 구성됩니다.
<br>
<br>

```

// 0부터 시작 : 5보다 작을때만 : 1씩 증감

for (int i = 0; i < 5; i++)
{
    Console.WriteLine(i + "번째");
}

/*
 실행 결과
 0번째
 1번째
 2번째
 3번째
 4번째
 */

```

![Desktop View](test.png)

### while

while(`조건`)
{
`실행할 코드`
}로 구성됩니다.

for문에 비해 많이 간결해진것이 보일겁니다.
조건만 맞으면 무한 반복합니다.

- 초기화가 필요하면 while문밖에 별도로 합니다.
- 변화는 반복문 내부나 외부에서 가능합니다.

```
int i =0;

while( i < 5)
{
    Console.WriteLine(i + "번째");
    i++;
}

/*
 실행 결과
 0번째
 1번째
 2번째
 3번째
 4번째
 */

```

![Desktop View](test.png)

### do while

while문과 같지만 조건에 상관없이 한번은 실행합니다.
이후는 while문과 같습니다.

```
int i = 0;

do
{
    Console.WriteLine(i + "번째");
    i++;
}
while (i < 5);


/*
 실행 결과
 0번째
 1번째
 2번째
 3번째
 4번째
 */
```

```

int j = 10;

do
{
    Console.WriteLine(j + "번째");
    i++;
}
while (j < 5);

/*
 실행 결과
 10번째
 */

```

![Desktop View](test.png)

### 반복문에서의 break

해당 반복문을 종료하고 빠져나옵니다.
<br>

for문

```
// break 없는 for문
for (int i = 0; i < 5; i++)
{
    Console.WriteLine(i + "번째");
}

/*
 실행 결과
 0번째
 1번째
 2번째
 3번째
 4번째
 */


//break 있는 포문
for (int i = 0; i < 5; i++)
{
    if (i == 3)
    {
        break;
    }
    Console.WriteLine(i + "번째");
}

/*
 실행 결과
 0번째
 1번째
 2번째
 3번째(출력 안됨)//break를 만나 반복문 종료
 4번째(출력 안됨)//break를 만나 반복문 종료
 */
```

> break가 선언되더라도 break 전까지의 코드는 동작함<br>
> 만약 `Console.WriteLine(i + "번째");`가 if문 위에 있다면 `3번째`까지 출력됨
{: .prompt-info}

while 문

```
//break가 없는 while문
while (true)
{
int x;
Console.Write("숫자를 입력해주세요 : ");
x = int.Parse(Console.ReadLine());
}
//오류가 나기 전까지는 무한 반복

//break가 있는 while문
while (true)
{
int x;
Console.Write("숫자를 입력해주세요 : ");
x = int.Parse(Console.ReadLine());
    if (x == 0)
    {
        break;
    }
}
//0이 입력되기 전까지는 무한반복. 0이 입력되면 반복문 종료
```

![Desktop View](test.png)

### 반복문에서의 continue

반복문에서 continue를 만날 시 즉시 해당 반복을 넘기고 다음반복으로 넘어갑니다.

for문

```
//continue있는 포문
for (int i = 0; i < 5; i++)
{
    if (i == 3)
    {
        continue;
    }
    Console.WriteLine(i + "번째");
}

/*
 실행 결과
 0번째
 1번째
 2번째
 3번째(출력 안됨) //continue를 만나 동작 안함
 4번째
 */
```

while문

```
// continue있는 while문
while (true)
{
    int x;
    Console.Write("숫자를 입력해주세요 (종료는 '0') : ");
    x = int.Parse(Console.ReadLine());
    if (x == 0)
    {
        break;
    }
    if (x % 10 == 0)
    {
        Console.WriteLine("10배수입니다.");
        continue;
    }
    Console.WriteLine("10의 배수가 아닙니다.");
}
```

10의 배수를 만날시에는 `Console.WriteLine("10의 배수가 아닙니다.");`를 작동하지 않고 바로 다음 반복으로 넘어갑니다.

> `continue`도 `break` 와 같은 방식으로 동작함<br>
{: .prompt-info}

![Desktop View](test.png)

제어문에 대해 알아봤습니다.
<br>
다음 포스팅은 배열에 대해 알아보겠습니다.
