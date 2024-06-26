## 객체지향 프로그래밍
- 객체지향 프로그래밍
  - OOP(object-oriented programming)은 객체들의 집합을로 프로그램의 상호작용을 표현하여 데이터를 객체로 취급하여 객체내부에 선언된 메서드를 활용하는 방식
  - 단점은 설계에 많은 시간이 소요되며 처리속도가 다른 프로그래밍 패러다임에 비해 상대적으로 느림
- 객체지향 프로그래밍 특징
  1. 추상화
     1. 복잡한 시스템으로부터 핵심적인 개념또는 기능을 간추리는것
  2. 캡슐화
     1. 객체의 속성과 메서드를 하나로 묶고 일부를 외부에 감추어 은닉하는것
     2. 객체의 속성(Variable)을 보호하기 위해 사용
  3. 상속
     1. 상위 클래스의 특성을 하위 클래스가 이어받아 재사용하거나 추가, 확장 하는것(계층적인 관계 생성, 유지 보수성 측면에서 중요)
     2. 상위클래스에서 하위 클래스로 내려갈 수록 **구체화** 되는 것이 중요하다.
  4. 다형성
     1. 하나의 메서드나 클래스가 다양한 방법으로 동작하는 것
     - 오버로딩
       - 같은 이름을 가진 메서드를 여러개 두는것
       - 메서드 타입, 매개변수 유형, 개수 등으로 여러개를 둘 수 있다
       - 컴파일 중에 발생하는 정적 다형성
         ![Untitled](assets/overloading.png)
     - 오버라이딩
       - 상위 클래스로 부터 상속받은 메서드를 하위 클래스가 재정의 하는것
       - 런타임중에 발생하는 동적 다형성
       ![Untitled](assets/overriding.png)
- 객체지향 프로그래밍 설계원칙 - SOLID
  - **S(단일 책임 원칙)**
    - 모든 클래스는 각각 하나의 책임만 가져야한다.
    - 하나의 클래스는 하나의 기능 담당하여 하나의 책임을 수행하는데 집중되도록 클래스를 따로따로 여러개 설계하라는 원칙
  - **O(개방 폐쇄 원칙)**
    - 확장에 열려있어야 하며, 수정에는 닫혀있어야 한다
    - 기능 추가 요청이 오면 클래스를 확장을 통해 손쉽게 구현하면서, 확장에 따른 클래스 수정은 최소화 하도록 프로그램을 작성해야 하는 설계 기법
    - ex) 추상 클래스와 상속을 통환 클래스 관계 구축
  - **L(리스코프 치환 법칙)**
    - 프로그램의 정확성을 깨트리지 않으면서 하위 타입의 인스턴스로 바꿀 수 있어야 하는 것을 의미
    - 서브 타입은 언제나 기반(부모) 타입으로 교체 가능 해야 한다.
    - 다형성의 특징을 이용하기 위해 상위 클래스 타입으로 객체를 선언하여 하위 클래스의 인스턴스를 받으면, 업캐스팅된 상태에서 부모의 메서드를 사용해도 동작이 의도대로 흘러가야 하는 것을 의미
    - ex) - Collection 인터페이스, 자료형을 LinkedList에서 전혀 다른 자료형 HashSet으로 바꿔도add() 메서드를 실행하는데 있어 원래 의도대로 작동되기 때문
  - **I(인터페이스 분리 원칙)**
    - 하나의 일반적인 인터페이스보다 구체적인 여러 개의 인터페이스를 만들어야 하는 원칙
    - **인터페이스는 제약 없이 자유롭게 다중 상속(구현)이 가능하기 때문에, 분리할 수 있으면 분리하여 각 클래스 용도에 맞게 implements 하라는 설계 원칙**
  - D(의존 역전 원칙)
    - Class를 참조해서 사용해야하는 상황이 생긴다면, 그 Class를 직접 참조하는 것이 아니라 그대상의 상위 요소(추상 클래스 or 인터페이스)로 참조
    - 구현 클래스에 의존하지 말고, 인터페이스에 의존
    - 의존 역전 원칙의 지향점은 각 클래스간의 결합도(coupling)을 낮추는 것
