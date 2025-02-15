---
layout: single
title: "어노테이션"
categories: Coding
tag: Java
toc: true
toc_sticky: true
---



# 어노테이션

자바 애너테이션(Java Annotation)은 자바 소스 코드에 추가하여 사용할 수 있는 메타데이터의 일종이다. 

- 프로그램을 구성하는 직접적인 코드가 아니다

- 프로그램 작성에 도움을 주거나 이에 필요한 도움을 제공
  - 컴파일러 기능 제공
  - 도구 기능 확장
  - 실시간 처리

- 관점 지향 프로그래밍의 Java 구현

  

# 어노테이션의 종류

- 표준(내장) 어노테이션 : 자바가 기본적으로 제공해주는 어노테이션
- 메타 어노테이션 : 어노테이션을 위한 어노테이션
- 사용자정의 어노테이션 : 사용자가 직접 정의하는 어노테이션



## 표준 어노테이션

- Override

  오버라이딩을 올바르게 했는지 컴파일러가 체크하는 기능

- Deprecated

  앞으로 사용하지 않을 것을 권장하는 필드나 메서드에  붙인다.

- SupressWarnings

  컴파일러의 경고메세지가 나타나지 않게 한다.

- SafeVarargs

  제네릭 같은 가변인인자의 매개변수를 사용할 때의 경고를 무시한다

- FunctionalInterface

  함수형 인터페이스에 붙이면, 컴파일러가 올바르게 작성했는지 체크

  

  ## 메타 어노테이션

- Target

  어노테이션이 적용할 위치를 선택

- Retention

  자바 컴파일러가 어노테이션을 다루는 방법을 기술하며, 특정 시점까지 영향을 미치는지를 결정

- Documented

  해당 어노테이션을 Javadoc에 포함 시킨다

- Inherited

  어노테이션도 상속이 가능하다. 어노테이션을 자손 클래스에 상속하고자 

  할 때, @Inherited를 붙인다.

- Repeatable

​		연속적으로 어노테이션을 선언할 수 있게  한다
