---
title: "Design Pattern이란?"
excerpt: ""

categories: 
    - Design Pattern1
tags:
    - [Design Pattern]

toc: true
toc_label: "목차"
toc_icon: "indent"
toc_sticky: true

date: 2021-06-04
last_modified_at: 2021-06-04
---
## 1. Design Pattern이란?
저희가 컴퓨터 공학에서 이야기하는 Design Pattern은 프로그래밍 설계시 특정 문맥에 공통적으로 
발생하는 문제에 대해 제시된 해결법, 방법론입니다.   

즉 간단히 이야기하면 특정 문제들에 대해 좀 더 효율적인 코드를 짜기 위해 제시된 템플릿들입니다.   

여러가지 종류의 디자인패턴이 있지만 그 중 가장 유명하고 대표적인 케이스는 OOP 설계에서 자주 사용되는 
'Gang of Four'(4인방)의 27가지 디자인 패턴입니다.   

<br/>

## 2. Gang of Four의 디자인 패턴
Gang of Four가 책으로 정리했던 디자인 패턴은 다음처럼 크게 3가지 범주에서 27가지로 정리됩니다.   

생성 패턴 :   
객체 생성, 변동이 전체시스템에 미치는 영향을 최소화하여(결합도↓) 개발 유연성을 높이는 패턴입니다.
```
Singleton, Builder, Factory Method, Abstract Factory, Prototype 
```


구조 패턴 :   
객체를 조합하여 더 큰 구조를 만들어 복잡한 시스템 개발의 난이도를 낮추는 패턴입니다.
```
Adapter, Bridge, Composite, Decorator, Facade, Proxy, Flyweight
```


행위 패턴 :   
반복적으로 사용되는 객체의 상호작용을 패턴화하여 객체의 책임을 분산하고 재사용성을 높입니다.
```
Chain of Responsible, Command, Interpretor, Iterator, Mediator, Memento, Observer,
Strategy, State, Template Method, Visitor
```

<br/>

***
이 밖에도 다양한 디자인 패턴이 존재합니다. 대표적으로 Server를 설계할 때 자주 사용되는 MVC패턴도 
(Model-View-Controller) 위 27가지에는 포함되진 않지만 디자인 패턴의 하나입니다.   

이 'Design Patter1' 카테고리에서는 [얄코님의 정리영상을](https://www.youtube.com/watch?v=lJES5TQTTWE) 바탕으로 위 패턴의 절반정도를 빠르게 
살펴보겠습니다. 나머지 부분이나 조금 더 자세한 정리는 추후 학습하여 다른 카테고리에 정리하겠습니다.   

그밖에 자주 사용되는 Iterator(반복자), Builder 패턴은 이번 정리에 없지만 Java 컬렉션 프레임워크의 
`Iterator 인터페이스`와 Lombok 라이브러리에 `@Builder`로 잘 구현되어 있어 참고하시면 좋습니다.   

Iterator : 반복이 필요한 자료구조를 모두 동일한 인터페이스를 통해 접근하게 하는 패턴   
Builder : 객체생성을 생성자를 통한 직접생성이 아닌 내부클래스`Builder`를 통해 간접생성하는 패턴   
{: .notice--primary}

위 두개는 추후 Java 정리를 할때도 언급할 예정이며 Observer 패턴의 경우 RxJS 수업내용을 정리할 때 
간단히 설명하도록 하겠습니다.   

Observer : 외부의 상태변화를 Observer객체를 상속한 객체들에 전달하고 상속된 기능을 수행시키는 패턴
{: .notice--primary}

   
<br/>

언제나 읽어주셔서 감사합니다.^^  

***

```
개인 공부용 블로그입니다.
잘못된 부분에 언제든지 댓글이나 메일로 지적해주시면 감사하겠습니다.
```