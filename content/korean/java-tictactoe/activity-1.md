---
title: "1. 게임판 설정하기!"
description: "인쇄 문을 사용하면 게임 규칙과 보드가 표시됩니다"
date: 2021-10-14T00:00:00Z
weight: 2
---

이 활동에서는 게임판과 게임 진행을 출력하는 프로그램을 작성합니다. 아래와 같은 출력이 나와야 합니다:

```
<<<~  틱택토  ~>>>
* 숫자 1 - 9를 선택하여 말을 놓으세요
* 플레이어: 'X' 컴퓨터: 'O'


 1 | 2 | 3 
---+---+---
 4 | 5 | 6 
---+---+---
 7 | 8 | 9 
말을 놓을 위치를 선택하세요 (1-9): 2
 O | X |   
---+---+---
   |   |   
---+---+---
   |   |   
말을 놓을 위치를 선택하세요 (1-9):
```

## 메인 클래스와 메인 메서드(method)

시작 코드에서 `main()`클래스와 `main()`메서드가 제공되어 있습니다. `main()` 메서드는 우리가 **Run** 버튼을 누르면 프로그램이 실행되는 시작점입니다.

```java
public class Main {
  public static void main(String[] args) {
  }
}
```

## 출력문

 main() 메서드 내에서 print 문을 사용하여 게임의 환영 메시지와 규칙을 출력하세요

```
<<<~  틱택토  ~>>>
* 숫자 1 - 9를 선택하여 말을 놓으세요
* 플레이어: 'X' 컴퓨터: 'O'


## 변수와 배열

이 게임에서는 현재 보드의 9가지 위치 각각에 있는 기호를 추적해야 한다는 점에 유의하세요.

따라서 프로그램에 9개의 데이터를 저장해야 합니다. 크기 9의 배열`array`(데이터 구조)를 사용하여 저장해 보겠습니다.

규칙에 명시된 바와 같이, 게임 보드에서 'X'는 플레이어의 움직임이고, 'O'는 컴퓨터 움직임이며, '"""는 사용 가능한 위치입니다.

이를 위해 9개의 모든 위치(즉, '{", "", "", "", "", "", "", "", "", "", "", "", "", "", "", "")에 값을 갖는 배열 '변수'를 선언해 보겠습니다.

## 게임판 출력하기

board 변수에 현재 게임 보드의 기호가 저장되어 있다고 가정합니다. 이제 아래에 표시된 출력처럼 빈 게임 보드를 출력하기 위해 print 문을 사용해 보겠습니다.

각 게임 보드는 5줄로 구성되어 있으므로, 각 줄을 출력하기 위해 5개의 print 문을 사용하는 것이 합리적입니다.

9개의 블록 각각은 길이가 3인 문자열(String)로 이루어져 있으며, 가운데 문자는 해당 위치의 board에 저장된 현재 기호입니다.

이 단계를 완료한 후 아래와 같은 출력을 가지는 프로그램을 작성해야 합니다.

```
<<<~  틱택토  ~>>>
* 숫자 1 - 9를 선택하여 말을 놓으세요
* 플레이어: 'X' 컴퓨터: 'O'

   |  |   
---+---+---
   |  |   
---+---+---
   |  |  

```

## 메서드(Methods)

게임 진행 중 현재 게임 보드를 여러 번 출력해야 할 것이므로, 4단계에서 작성한 코드를 메서드로 분리하는 것이 좋습니다.

이 메서드는 String[] 배열을 입력으로 받아 현재 보드를 출력하는 역할을 합니다. 이 메서드는 main() 메서드 외부에 작성되어야 한다는 점에 유의하세요.

다음과 같은 헤더를 가진 메서드를 작성해 보겠습니다:
```java
public static void printBoard(String[] curBoard);
```

## 메서드 호출하기

main() 메서드에서 printBoard() 메서드를 호출하여, 위치가 표시된 초기 게임 보드를 출력하도록 설정하세요. 이를 위해 "1", "2", ..., "9"의 내용을 가지는 또 다른 String 배열을 생성하면 됩니다.

그리고 Enter your move (1-9): 라는 텍스트를 출력하는 코드를 추가하세요.

출력은 아래와 같이 표시되어야 합니다:

<<<~  Tic  Tac  Toe  ~>>>
 1번 ~ 9번을 선택하여 이동합니다
* 플레이어: 'X' 컴퓨터: 'O'


 1 | 2 | 3 
---+---+---
 4 | 5 | 6 
---+---+---
 7 | 8 | 9 
Enter your move (1-9): 

프로그램 실행

프로그램을 실행했을 때 위와 같은 텍스트가 출력된다면, 다음 단계로 진행할 준비가 완료된 것입니다. 👍
