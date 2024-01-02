---
title: C# 기초 문법 - 클래스와 객체
date: 2023-10-12 00:00:00 +0900
categories: [C#, class]
tags: [C#, Tutorial, Visual Studio 2022, object, class]
img_path: /assets/img/
---

이 게시물은 C# 공부과정을 정리해놓은 것입니다
사용하는 툴은 Visual Studio 2022 입니다.
해당 툴을 사용하는 이유는 추후에 다룰 Unity에서 연계하여 사용하기 위함입니다.

> C#에 대한 더 많은 포스팅은 `CATEGORIES`의 <a href ="https://ryutaeha.github.io/categories/c/">`C#`</a>을 확인하세요.
{: .prompt-tip }

## 클래스와 객체

![Desktop View](test.png)

### 객체지향이란?

하나가 아닌 여러개의 무언가(객체)가 서로 상호작용하면서 연결되서 실행되는 것입니다.

![Desktop View](test.png)

### 객체지향 특징

객체지향의 특징으로는 크게 4가지가 있습니다.

1. 캡슐화
   - 데이터와 코드를 외부에서 알 수 없게 감추는 것입니다.
   - 외부에서는 필요한 정보만 알면 됩니다.
2. 추상화
   - 객체들의 공통적인 특징은 추려내는 것입니다.
3. 상속

   - 하위 클래스가 상위 클래스의 모든 것을 활용가능합니다.
   - 클래스를 재사용하여 반복적인 코드를 줄일수 있습니다

4. 다형성

   - 프로그램 언어의 각 요소(상수, 변수, 식, 오브젝트, 함수, 메소드)들이 여러가지 타입을 가질수 있습니다.

이러한 특성들 덕에 장점이 많습니다.

- 코드 재사용이 용이합니다.
- 코드 생산성이 높아집니다.
- 유지보수에 용이합니다.

![Desktop View](test.png)

### 클래스란?

하나의 예를 들어보겠습니다

```
string name1 = "철수";
string class1 = "1학년;
int age1 = 8;

string name2 = "영희";
string class2 = "4학년;
int age2 = 11;

string name3 = "민수";
string class3 = "6학년;
int age3 = 13;

```

현재는 학생이 3명이지만 학생이 100명 아니 1000명이 넘어가면 코드 길이가 엄청 길어지고 가독성도 많이 떨어집니다.
<br>
<br>
하지만 class를 이용하면 이 데이터들의 공통된 부분을 추상화 할수 있습니다.

![Desktop View](test.png)

### 클래스 생성

```
class Student
{
    public string name;
    public string classNo;
    public int age;
}
```

클래스 영역안에서는 변수를 만들거나 함수를 만들 수 있습니다.
하지만 함수의 호출이나 계산 등의 동작은 할 수 없습니다.
이러한 경우 함수를 하나 더 만들어서 그 안에서 필요한 내용을 작성하면 됩니다.

```
class Student
{
    public string name;
    public string classNo;
    public int age;

    public void test()
    {
        Console.WriteLine("저는 "+name+"입니다");
    }
}
```

![Desktop View](test.png)

### 클래스의 활용

클래스를 사용하려면 새로운 객체를 만들어야합니다.

```
Student newStudent = new Student();

newStudent.name = "마이클";
newStudent.classNo = "5학년";
newStudent.age = 12;

newStudent.test();

class Student
{
    public string name;
    public string classNo;
    public int age;

    public void test()
    {
        Console.WriteLine("저는 " + name + "입니다");
    }
}
```

![Desktop View](test.png)

클래스와 객체에 대해 알아봤습니다.
<br>
다음 포스팅은 Unity 개발로 올거 같습니다.
