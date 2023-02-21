---
layout: post
title: Programming Paradigm
---

# 프로그래밍 패러다임 이란?

프로그래밍 패러다임이 뭐냐고 물어보면 명확한 정의를 설명하기가 어려운 부분이 있다. 아래는 몇몇 글에서 말하는 프로그래밍 패러다임의 정의이다.

> Programming paradigms are different ways or styles in which a given program or programming language can be organized.

> Programming paradigms are a way to classify programming languages based on their features.

> A programming paradigm is the classification, style or way of programming. It is an approach to solve problems by using programming languages.

결국 프로그래밍 패러다임이란, 프로그래밍 방법론이나 전략/접근방식 을 말하는 것이고, 이는 프로그래밍 언어나 프로그램을 구성하고,특성에 따라 분류할 때 쓰이게 된다.

프로그래밍 언어가 구현될 때 어떤 전략을 따를 필요가 있고, 이 방법론/전략이 프로그래밍 패러다임이다.

특정 패러다임은 특정 유형의 문제에 더 적합하므로 다른 종류의 프로젝트에 다른 패러다임을 사용하는 것이 합리적일 수 있다.

또한, 각 패러다임을 구성하는 관행은 시간을 통해 발전해 왔다. 소프트웨어와 하드웨어의 발전 덕분에, 이전에는 존재하지 않았던 다양한 접근법이 등장했다. 우리가 프로그램을 작성하고 구조화할 때 선택할 수 있는 많은 옵션이 있다는 것이다.

프로그래밍 패러다임은 언어나 도구가 아니다. 패러다임으로는 어떤 것도 만들 수 없다. 프로그래밍 패러다임은 많은 사람들이 동의하고 따르고 확장해 온, 이상과 지침에 더 가깝다.

또한, 프로그래밍 패러다임은 상호 배타적인 것이 아니다. 프로그래밍 언어와 프로그램은 여러 패러다임을 특징으로 할 수 있다.

명령적, 절차적, 기능적, 선언적, 객체 지향적 패러다임은 오늘날 가장 대중적이고 널리 사용되는 패러다임 중 일부이다. 그리고 그것들에 대한 기초를 아는 것은 일반적인 지식과 코딩 세계의 다른 주제들을 더 잘 이해하는 데 도움이 된다.

## 명령형 프로그래밍 패러다임(Imperative Programming)

명령형 프로그래밍은 주어진 순서에 따라 실행되도록 컴퓨터에 주어진 일련의 상세한 명령어들로 구성된다. 프로그래머로서 우리는 컴퓨터가 해야 할 일을 매우 구체적인 방법으로 정확히 지시하기 때문에 이것을 "명령형"라고 부른다.

명령형 프로그래밍은 프로그램이 어떻게 작동하는지 단계별로 설명하는 데 초점을 맞춘다.

```javascript
const nums = [1, 4, 3, 6, 7, 8, 9, 2];
const result = [];

for (let i = 0; i < nums.length; i++) {
  if (nums[i] > 5) result.push(nums[i]);
}

console.log(result); // Output: [ 6, 7, 8, 9 ]
```

## 절차적 프로그래밍 패러다임(Procedural Programming)

절차적 프로그래밍은 명령형 프로그래밍에서 파생된 것으로, 여기에 함수의 기능을 추가한 것이다.

절차적 프로그래밍에서 프로그램 실행을 함수(프로시저 or 서브루틴)로 세분화하여 모듈화시켜 프로그램 구조를 개선한다.

```c++
#include <iostream> 
// function declaration 
int sum(int num1, int num2); 
 
int main () { 
   // local variable declaration: 
   int a = 10; 
   int b = 20; 
   int res; 
 
   // call to sum function 
   res = sum(a, b); 
   std::cout << a << "+" << b << "=" << res << std::endl; 
   return 0; 
} 
 
// function returning the sum of two numbers 
int sum(int num1, int num2) { 
   int result; 
   result = num1 + num2; 
   return result; 
} 
```

단순화 및 추상화는 절차적 프로그래밍의 이점 중 하나이다. 하지만 함수 안에는 여전히 명령형 코드가 존재한다.

## 선언형 프로그래밍(Declarative Programming)

선언형 프로그래밍은 명령형 프로그래밍과 대조적으로 프로그램이 어떻게(How) 실행되어야 하는지 보다는 프로그램이 무엇(What)을 달성하기를 원하는지를 설명한다.
제어 흐름을 설명하지 않고 프로그램에서 수행할 결과를 정의한다. 선언형 프로그래밍은 더 표현적이고 명시적인 코드를 개발하는 데 도움이 됩니다.

```javascript
let n = [-9, 87, 72, 452, 32, -9];
n.forEach((v) => console.log(v));
```

선언형 프로그래밍의 좋은 점은 읽고 이해하기 쉽고, 종종 더 짧게 쓸 수 있다는 것이다. 자바스크립트의 filter, map, reduce, sort 기능은 선언형 코드의 좋은 예이다.

React JSX 코드는 선언형의 좋은 예이다.

```javascript
<button onClick={() => console.log("You clicked me!")}>Click me</button>
```

선언형 프로그래밍에서 중요한 것은 어쨌든 컴퓨터가 이 정보를 명령형 코드로 처리한다는 것이다.
선언형 프로그래밍이 하는 일은 프로그래머의 직접적인 관점으로부터 그 복잡성을 숨기는 것이다.

## 함수형 프로그래밍 패러다임(Functional Programming Paradigm)

함수형 순수한 수학적 함수(Pure function)를 조합하고 적용함으로써 프로그램을 구성하는 방법으로 선언형 프로그래밍의 한 유형이다.

아래는 함수형 프로그래밍의 특성이다.

- 일급객체/고차함수
  함수형 프로그래밍에서 함수는 일급객체로 취급되며, 이는 변수에 할당되고 인수로 전달되며 다른 함수에서 반환될 수 있음을 의미한다. 다른 함수를 인수로 받고 함수를 반환하는 함수를 고차함수라고 한다.

- 순수함수
  순수함수는 동일한 입력에 항상 동일한 결과를 만들어낸다. 게다가, 순수함수는 side effect 를 일으키지 않는다(인수, 로컬/글로벌 변수, 입력/출력 스트림을 수정하지 않는다)
  순수함수의 유일한 결과는 반환되는 값이다.

- 재귀함수(Recursion)
  함수형 프로그래밍에서 "for" 또는 "while" 루프는 재귀함수를 통해 구현된다.

- 참조 투명성(Referential transparency)
  함수형 프로그래밍에서는 할당 문이 없고, 값을 저장해야 하는 경우 대신 새 변수를 정의함으로써 side effect를 없앤다.

함수형 프로그래밍은 이러한 함수의 개념을 염두에 두고, 주로 함수로 작성된 프로그램을 권장한다.

함수형 프로그래밍은 코드를 모듈화하고 side effect 를 없애는 것이, 코드베이스 내에서 책임을 식별하고 분리하는 것을 더 용이하게 한다는 사고를 지키고, 이는 코드 유지보수성을 향상시킨다.

statement(문) 대신 expression(표현식)을 사용한다. expression(표현식)은 값을 생성하기 위해 평가되는 반면, statement(문)은 변수를 할당하기 위해 실행됩니다.

```javascript
const nums = [1, 4, 3, 6, 7, 8, 9, 2];

function filterNums() {
  const result = []; // Internal variable

  for (let i = 0; i < nums.length; i++) {
    if (nums[i] > 5) result.push(nums[i]);
  }

  return result;
}

console.log(filterNums()); // Output: [ 6, 7, 8, 9 ]
```

위 함수는 함수의 범위 밖의 어떤 것도 수정하지 않는다는 것을 보장할 수 있다. 정보를 처리하기 위한 변수만 만들고, 실행이 끝나면 변수도 사라지게끔 만든다.

## 객체지향 프로그래밍(Object-Oriented Programming)

프로그램을 단순히 데이터와 처리 방법으로 나누는 것이 아니라, 프로그램을 수많은 '객체(object)'라는 기본 단위로 나누고 이들의 상호작용으로 서술하는 방식이다. 객체란 하나의 역할을 수행하는 '메소드와 변수(데이터)'의 묶음으로 봐야 한다.

OOP는 클래스 방법을 많이 사용한다(프로그래머가 설정하는 Blueprint나 Boilerplate에서 시작하여 새로운 객체를 만드는 방법).

클래스에서 생성된 객체를 인스턴스라고 합니다.

OOP의 첫 번째 단계는 프로그래머가 작업하고자 하는 모든 객체를 수집하고 그들의 관계를 결정하는 것이다.

OOP의 장점은 관심사와 책임을 명확하게 분리함으로써 프로그램에 대한 이해를 용이하게 한다는 것이다.

객체지향 프로그래밍의 주된 특성은 다음과 같다.

- 추상화
- 다형성
- 캡슐화
- 상속

## 출처

[https://www.freecodecamp.org/news/an-introduction-to-programming-paradigms](https://www.freecodecamp.org/news/an-introduction-to-programming-paradigms)

[https://www.geeksforgeeks.org/introduction-of-programming-paradigms](https://www.geeksforgeeks.org/introduction-of-programming-paradigms)

[https://en.wikipedia.org/wiki/Programming_paradigm](https://en.wikipedia.org/wiki/Programming_paradigm)
