---
title: C# 기초 문법 - 함수
date: 2023-10-11 00:00:00 +0900
categories: [C#, function]
tags: [C#, Tutorial, Visual Studio 2022, function]
img_path: /assets/img/
---

이 게시물은 C# 공부과정을 정리해놓은 것입니다
사용하는 툴은 Visual Studio 2022 입니다.
해당 툴을 사용하는 이유는 추후에 다룰 Unity에서 연계하여 사용하기 위함입니다.

> C#에 대한 더 많은 포스팅은 `CATEGORIES`의 <a href ="https://ryutaeha.github.io/categories/c/">`C#`</a>을 확인하세요.
 {: .prompt-tip }

## 함수란?

미리 만들어놓은 코드를 불러와 실행하는 기능입니다.
<br>
중복되는 코드를 막을 수 있고 여러번 사용이 가능합니다.

```
//대표적인 함수 ()안의 문자열을 출력해준다.
Console.WriteLine("Hello, World!");
```

`함수명`()으로 표기합니다.

![Desktop View](test.png)

## 함수

함수는 이미 있는 것을 사용할 수 있습니다. 대표적으론 `Console.WriteLine();`이 있습니다.
<br>
하지만 이미 있는 것중에서 필요한 함수가 없을 수도 있습니다.

![Desktop View](test.png)

### 함수 생성

함수는 필요에 따라 생성을 할 수 있습니다.

```
//TestFunction() 생성
void TestFunction()
    {
        Console.WriteLine("함수테스트!");
    }
```

위에 만든`TestFunction()`를 하나씩 봐보겠습니다.

| `void`   | `TestFunction` | `()`                    | `{}`        | `Console.WriteLine("함수테스트!");` |
| :------- | :------------- | :---------------------- | :---------- | :---------------------------------- |
| 반환타입 | 함수명         | 함수기능 실행(매개변수) | 함수의 영역 | 실행코드                            |

반환타입 : 함수의 결과가 어떤 식으로 나오는지 알려주는 부분입니다. 자세한 내용은 하단을 <a>참조</a>하세요
<br>
<br>
함수명 : 변수이름과 마찬가지로 작성자가 지을 수 있는 함수명입니다.

> 함수명은 어떤 기능을 가지고 있는지 대략적으로 알수 있겠끔 직관적으로 지어야 한다.
> 함수는 파스칼 표기법을 따른다.
 {: .prompt-tip }

<br>
<br>
함수기능 실행 : 기능을 실행할 때는 `()`을 붙입니다. 
<br>
<br>
함수의 영역 : `{}`가 어디까지가 함수인지를 알려줍니다.
<br>
`TestFunction()`의 영역은{Console.WriteLine("함수테스트!");} 입니다.
<br>
<br>
실행코드 : 함수가 실행되면 실행하는 코드입니다. 함수의 영역안에 있는 코드가 실행됩니다.

![Desktop View](test.png)

### 함수 사용

함수는 만들어만 두면 사용을 할수 없습니다.
<br>
해당 함수를 사용하기 위해서는 `함수명();`을 쓰면 됩니다.

```
Console.WriteLine("테스트1");
Console.WriteLine("테스트2");
Console.WriteLine("테스트3");
Console.WriteLine("테스트4");
Console.WriteLine("테스트5");

void TestFunction()
{
    Console.WriteLine("함수테스트!");
}

//실행 결과
/*
테스트1
테스트2
테스트3
테스트4
테스트5
*/
```

![Desktop View](test.png)

해당 함수는 선언만 하면 효력이 없습니다.

```
Console.WriteLine("테스트1");
Console.WriteLine("테스트2");
TestFunction();
Console.WriteLine("테스트3");
Console.WriteLine("테스트4");
Console.WriteLine("테스트5");

void TestFunction()
{
    Console.WriteLine("함수테스트!");
}

//실행 결과
/*
테스트1
테스트2
함수테스트!
테스트3
테스트4
테스트5
*/
```

`TestFunction();`을 사용하면 `함수테스트!`가 중간에 출력이 되는 걸 볼수 있습니다.

> 가독성을 위해 로직 중간에 함수를 만들지는 않습니다. 보통 함수들은 코드의 시작이나 끝에 정리를 해 사용하는 편이 가독성이 좋습니다.
 {: .prompt-tip }

![Desktop View](test.png)

### 함수 return과 반환형식

void 타입의 함수들은 변수에 저장할수 없습니다.
<br>
그럼 함수는 변수에 저장할 수 없나요? 그건 아닙니다.
<br>
변환타입을 설정해주면 됩니다. 그럴 때 return을 사용해주면 됩니다.

```
int FuncReturn = TestFunc();

int TestFunc(){
    return 100;
}
Console.WriteLine(FuncReturn);
```

void는 반환을 하지 않겠다는 뜻으로 return을 할수 없습니다. 반환타입은 원하는 자료형을 사용할 수 있습니다.

> 함수의 return 값은 반환타입과 같아야한다.<br>
> void가 아닌 반환타입이라면 반드시 return해줘야 한다. <br>
> 리턴타입이랑 반환타입은 같아야한다.
 {: .prompt-warning }

![Desktop View](test.png)

### 함수의 매개변수

그렇다면 함수에게 값을 주고 그 값을 사용한 함수가 필요할 때도 있습니다.
<br>
그럴때는 매개변수를 사용해주면 됩니다.
<br>
매개변수는 함수 실행부분에 선언해주시면 됩니다.

```
int result = TestFunc(20);

Console.WriteLine(result);

int TestFunc(int x){
    return x*10;
}
```

`TestFunc(20)`의 20을 다른 수로 바꾸면 다른 값이 나옵니다.
<br>
단 매개변수가 있는 함수는 매개변수를 주지 않으면 에러가 일어납니다.
![Desktop View](test.png)

<br>
<br>
또한 매개변수는 하나가 아닌 여려가지를 줄수 있습니다.

```
string result = TestFunc(20, "학생");

Console.WriteLine(result);

string TestFunc(int age, string job)
{
    return age + "살인 " + job + "입니다.";
}
```

단 여러가지의 매개변수일 때는 들어가는 값을 순서와 타입에 맞게 넣어주어야합니다.

![Desktop View](test.png)

함수에 대해 알아봤습니다.
<br>
다음 포스팅은 클래스와 객체에 대해 알아보겠습니다.
