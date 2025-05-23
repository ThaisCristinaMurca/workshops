---
title: "자리 표시자"
date: 2020-07-23T00:00:00Z
weight: 15
draft: true
hidden: true
---

## 읽기 및 처리 입력

Java에서 사용자 입력을 효율적으로 받는 방법은 java.util 패키지의 Scanner 클래스를 사용하는 것입니다. 이 클래스를 사용하고 모든 메서드를 활용하기 위해서는 파일의 맨 위에 다음과 같은 import 문을 추가해야 합니다.

```java
import java.util.Scanner;
```

## 오류 처리

Java에서는 잠재적인 오류를 처리하기 위해 오류가 발생할 수 있는 코드를 `try-catch`  블록에 넣습니다.

`try` 블록에는 오류를 일으킬 수 있는 코드 블록을 넣습니다.

 `catch` 블록에는 `try` 블록을 실행할 때 오류가 발생할 경우 수행할 지침을 넣습니다. 이렇게 하면 프로그램이 충돌하는 것을 방지할 수 있습니다. 예를 들어:

```java
try{
   //  Block of code to try
} catch(Exception e){
   //  Block of code to handle errors
}
```

프로그램을 실행하고 숫자가 아닌 입력을 입력하세요. 프로그램이 지금 실패해서는 안 됩니다!

## `try` 블록

`try` 블록에서는 사용자로부터 숫자 입력을 받습니다. 그러나 모든 입력이 유효한 것은 아니며, 보드에서 사용 가능한 자리만 허용해야 합니다.

 if 문을 사용하여 숫자 입력이 유효한지 확인하세요. (힌트: 입력의 유효성을 확인하기 위해 `board` 배열에 접근하세요).

유효하지 않은 경우, 다음 문장을 출력하세요: 잘못된 위치입니다; 다시 입력하세요 (1-9):.

{{% notice hint %}}
#### 두 문자열이 같은지 어떻게 확인하나요?

두 문자열이 같은 내용을 포함하는지 확인하려면`equals()` 메서드를 호출합니다. 예를 들어:

```java
String s1 = "hi";
boolean b1 = s1.equals("hi"); // this is true
boolean b2 = s1.equals("HI"); // this is false
```

{{% /notice %}}

## Catch 블록

`catch` 블록에서는 플레이어가 숫자가 아닌 입력을 했다는 것을 알고 있습니다.

 먼저, Scanner에서 이 잘못된 입력을 무시해야 하며, 이를 위해 우리가 생성한 Scanner 객체에서 next() 메서드를 호출합니다.
 
  그 후, 플레이어에게 다시 입력하라는 메시지를 출력해야 합니다: 잘못된 위치입니다; 다시 입력하세요 (1-9):.



## 프로그램 실행하기(선택사항)

프로그램을 테스트하려면 `Run` 버튼을 클릭하세요. 숫자가 아닌 입력이나 1에서 9 사이가 아닌 숫자를 입력하면 잘못된 위치입니다; 다시 입력하세요 (1-9):라는 메시지가 표시되어야 합니다.

## 다중 입력

이제 하나의 입력을 받아 유효성을 평가하는 프로그램이 있습니다. 게임이 끝날 때까지 플레이어에게 계속 입력을 요청하고자 합니다.

사용자에게 다음 이동을 입력하도록 계속 요청하기 위해, 전체 try-catch 블록을 while 루프 안에 넣습니다. 이 while 루프는 true라는 인자를 받아 프로그램이 중지하라는 지시가 있을 때까지 계속 반복됩니다.

각 반복의 끝에서 printBoard(board)를 호출하고 사용자에게 프롬프트를 표시하는 점에 유의하세요. 아래에 표시되어 있습니다:

```java
while(true){
    // insert the try-catch block here

    printBoard(board);
    System.out.print("Enter your move (1-9): "); 
}
```

## 잘못된 입력 처리

사용자가 잘못된 입력을 할 경우, 프로그램이 `printBoard(board)`를 호출하고 `Enter your move (1-9): ` 를 출력하지 않도록 하고 싶습니다.

즉, 프로그램이 `while` 루프의 다음 반복으로 넘어가도록 하고 싶습니다.

코드에 `continue;`를 넣어 컴퓨터가 루프의 맨 위로 다시 실행하도록 건너뛰라는 것을 나타냅니다.

이 연습이 끝날 때쯤이면, 잘못된 입력에 대해 다시 입력하라는 메시지를 표시하고, 유효한 입력에 대해 빈 보드를 출력하며 `Enter your move (1-9): ` 라는 프롬프트를 표시하는 프로그램을 갖게 될 것입니다!

```
<<<~ 틱택토~>>
* 1번 - 9번을 선택하여 이동합니다
* 플레이어: 'X' 컴퓨터: 'O'

1 | 2 | 3
---+---+---
4 | 5 | 6
---+---+---
7 | 8 | 9
당신의 이동을 입력하세요 (1-9): 1
| |
---+---+---
| | <--------------------- 보드에 플레이어/컴퓨터 이동이 없습니다
---+---+---
| |
당신의 이동을 입력하세요 (1-9): d
잘못된 입력; 이동을 다시 입력합니다 (1-9): 3
| |
---+---+---
| | <--------------------- 보드에 플레이어/컴퓨터 이동이 없습니다
---+---+---
| |
당신의 이동을 입력하세요 (1-9):
```

워크숍을 계속 진행하여 게임 보드를 업데이트하는 방법을 알아보겠습니다!
