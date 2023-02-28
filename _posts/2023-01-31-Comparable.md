---
layout: single
title: "Comparable과 Comparator"
categories: Coding
tag: Java
toc: true
toc_sticky: true
---



# Comparable과 Comparator

Comparable과 Comparator의 공통점

- Comparable 과 Comparator는 모두 Interface이며, 인터페이스 내에 선언된 메소드를 '반드시 구현' 해야한다는 것이다.
- Comparable 인퍼페이스는 compareTo(T o) 메소드 , Comparator 인터페이스 compare(T o1, o2)로 나타낼수 있다.
- 이 두기능의 공통적인 기능은 "객체를 비교한다"라는 것이다.



Comparable의 특징

- 클래스가 상속받아서 compareTo 메소드를 구현함
- 해당 객체 배열은 기본적으로 compareTo 구현방식대로 정렬됨.
- 모든 값 클래스, 열거 타입은 Comparable이 구현되어져 있으므로 sort사용이 가능한것이다.
- 정렬기준을 바꾸는게 어렵다.
- Collections.reverseOrder() 사용이 가능하다.



Comparator의 특징

- sort마다 원하는 방식으로 자유롭게 정렬하기 좋다.

- 구현체를 선언해두고 재사용도 할 수 있다.

- sort에서 람다식으로 비교적 짧게 축약사용이 가능하다.

  

## Comparable 예제 코드

```java
class student implements Comparable<Student> {
    int age;
    int classNumber;
    
    Student(int agem int classNumber) {
        this.age = age;
        this.classNumber = classNumber;
    }
    
    @Overide
    public int compareTo(Student o) {
        return this.age - o.age;
    }
}
```



- 자기 자신과 매개변수를 비교한다
- compareTo 메소드를 반드시 구현해야한다.



## Comparator 예제 코드 

```java
class student implements Comparator<Student> {
    int age;
    int classNumber;
    
    Student(int agem int classNumber) {
        this.age = age;
        this.classNumber = classNumber;
    }
    
    @Overide
    public int compare(Student o1,Student o2) {
        return o1.age - o2.age;
    }
}
```



- 두 매개변수를 비교한다
- compare 메소드를 반드시 구현해야한다.

여기서 compareto를 비교할떄 두개의 변수가 필요한데 모든 객체를 따로 비교하기는 어렵다. 이럴때 익명 객체(클래스)를 이용한다.



### 익명 객체를 사용한 비교

```java
import java.util.Comparator;
 
public class Test {
	public static void main(String[] args) {
    
		Comparator<Student> comp1 = new Comparator<Student>() {
			@Override
			public int compare(Student o1, Student o2) {
				return o1.classNumber - o2.classNumber;
			}
		};
	}
 
	// 익명 객체 구현 2
	public static Comparator<Student> comp2 = new Comparator<Student>() {
		@Override
		public int compare(Student o1, Student o2) {
			return o1.classNumber - o2.classNumber;
		}
	};
}
 
 
// 외부에서 익명 객체로 Comparator가 생성되기 때문에 클래스에서 Comparator을 구현 할 필요가 없어진다.
class Student {
 
	int age;			// 나이
	int classNumber;	// 학급
	
	Student(int age, int classNumber) {
		this.age = age;
		this.classNumber = classNumber;
	}
 
}
```



## 정리

- Comparable / Comparator 는 모두 객체를 비교하기 위한 기능 의 인터페이스

- 두 인터페이스는 비교대상 이 다르다
  - Comparable :  호출한 자신 과 매개변수 객체 의 비교
  - Comparator : 매개변수 객체 2개 간 비교

- 정렬(`sort`)와 함께 사용 될 때
  - Comparable : 오름차순 정렬 할 때 주로 사용
  - Comparator : 내림차순이나 특별한 기준 에 따라 비교할 때 주로 사용
