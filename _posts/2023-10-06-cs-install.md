---
title: C# 기초 문법 - 설치부터 프로젝트 만들기
date: 2023-10-06 00:00:00 +0900
categories: [C#, Install]
tags: [C#, Tutorial, Visual Studio 2022, Install]
img_path: /assets/img/cs/
pin: true
---

이 게시물은 C# 공부과정을 정리해놓은 것입니다
사용하는 툴은 Visual Studio 2022 입니다.
해당 툴을 사용하는 이유는 추후에 다룰 Unity에서 연계하여 사용하기 위함입니다.

> C#에 대한 더 많은 포스팅은 `CATEGORIES`의 <a href ="https://ryutaeha.github.io/categories/c/">`C#`</a>을 확인하세요.
 {: .prompt-tip }

## 사용하기에 앞서 C#이란?

C#이란 MS에서 개발한 객체지향프로그램으로서 Windows 플랫폼에서 강력한 위상을 가지고 입니다.
<br>
`.NET 프레임워크`와 같이 사용되는 오픈소스 프로그래밍 언어이며 현재에는 Windows에 국한된 언어가 아닌 다양한 분야에서 쓰이는 언어입니다.

## Visual Studio 2022 설치하기

> 상업적으로 사용이 아닌 공부 목적으로 사용할 것이기 때문에 Visual Studio 2022 Community 을 사용.
> <br>
> 또한 로그인은 건너뜀.
 {: .prompt-info }

<a href="https://visualstudio.microsoft.com/ko/vs/community/" target="_blank">Visual Studio 2022 Community 공식 다운로드</a>
<br>
해당 사이트에서 다운로드 후 설치까지 완료하면 `Visual Studio Installer`가 실행됩니다.

![Desktop View](vs_installer.png)
<br>
`Visual Studio Installer`에서 `.NET 데스크톱 개발`을 선택하고 설치합니다.

> 현재 작성자는 `.NET 데스크톱 개발`이 깔려있는 상태로 설치가 아닌 수정으로 나온다.
 {: .prompt-info }

## 프로젝트 만들기

이제 프로젝트를 만들어보겠습니다.

### Visual Studio 2022 Community 를 이용하여 프로젝트 생성

![Desktop View](newProject.png)

실행 후 새 프로젝트 만들기를 클릭합니다.

![Desktop View](newProjectMake.png)

맨 위에 있는 콘솔 앱을 선택하고 다음버튼 누르면 됩니다.

![Desktop View](newProjectRoot.png)

프로젝트 이름은 한글이 아닌 무조건 영어로 한다고 생각하시면 됩니다.
<br>
<br>
프로젝트가 위치할 위치 경로에도 한글이 들어가지 않게 해야합니다.
<br>
파일명과 경로상에 한글이 있을경우에는 프로그램이 제대로 작동하지 않을 경우가 있습니다.

> 컴퓨터 사용자명이 한글이 경우에도 안될수 있으므로 본인 컴퓨터 사용자명을 한번 더 꼭 확인 해볼 것!
 {: .prompt-warning }

그 후 설정은 건드릴게 없습니다.
다음 계속 누르시고 만들기까지 누르시면됩니다.

![Desktop View](newProjectMenu.png)

만들기까지 완료되면 해당화면이 나타납니다.
<br>
화면에 코드가 달라도 괜찮습니다, 처음에는 다 지우고 시작할겁니다.
<br>
그럼 다음시간에는 기초 문법과 변수를 알아보겠습니다.

