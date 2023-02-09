---
layout: single
title: "직렬화(Serializable)"
categories: Coding
tag: Java
toc: true
---

# Serializable 

인터페이스를 공부하면서 마크 인터페이스를 알아보았는데 예시로 Serializable를 알게되어 정리해보려 한다.

개발을 하다 보면 아래와 같은 경우가 존재한다.  아래의 경우 필요한 것이 **Serializable** 이다.

- 생성한 객체를 파일로 저장할 일
- 저장한 객체를 읽을 일
- 다른 서버에서 생성한 객체를 받을 일

 즉 Serializable 인터페이스를 구현하면 JVM에서 해당 객체는 저장하거나 다른 서버로 전송 할 수 있도록 해준다.

```java
public calss Member implements Serializable{
  private String name;
  private String email;
  private int age;

  public Member(String name, String email, int age){
    this.name = name;
    this.email = email;
    this.age = age = age;
  }
  @Override
  public String toString(){
    return String.format("Member{name='%s', email='%s', age='%s'}", name,email)
  }
}
```



## 직렬화(Serialize)

- 자바 시스템 내부에서 사용되는 Object 또는 Data를 외부의 자바 시스템에서도 사용할 수 있도록 byte 형태로 데이터를 변환하는 기술 

- JVM(Jaava Virtual Machine 이하 JVM)의 메모리에 상주(힙 또는 스택)되어 있는 객체 데이터를 바이트 형태로 변환하는 기술

- 자바 직렬화 대상 객체는 동일한 **serialVersionUID** 를 가지고 있어야함.

- 자바의 직렬 화 말고 대표적인 직렬화 방법으로 문자열 기반(CSV,JSON), 이진 직렬화 방법(Protocool Buffer)등 이 있다.

- CSV, JSON, 프로토콜 버퍼 등은 시스템의 고유 특성과 상관없는 대부분의 시스템에서의 데이터 교환 시 많이 사용된다, 하지만 **"자바 **

  **직렬화 형태의 데이터 교환은 자바 시스템 간의 데이터 교환을 위해서 존재한다."**고 생각

​	



### 역직렬화(Deserialize)

- byte로 변환된 Data를 원래대로 Object나 Data로 변환하는 기술을 역직렬화(Deserialize)라고 부름.
- 직렬화된 바이트 형태의 데이터를 객체로 변환해서 JVM으로 상주시키는 형태



## transient

- `transient`는 Serialize하는 과정에 제외하고 싶은 경우 선언하는 키워드입니다.

- 패스워드와 같은 보안정보가 직렬화(Serialize) 과정에서 제외하고 싶은 경우에 적용합니다.
- 다양한 이유로 데이터를 전송을 하고 싶지 않을 때 선언할 수 있습니다.





참고 자료

 [https://techblog.woowahan.com/2550/)](https://techblog.woowahan.com/2550/)