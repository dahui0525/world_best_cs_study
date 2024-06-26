# 싱글톤 패턴

- 특정 클래스의 인스턴스가 오직 하나만 생성되도록 보장하는 디자인 패턴이다.
- 인스턴스가 두 개 이상이 생성되었을 때 발생하는 프로그램의 비정상적인 동작이나 불필요한 자원 소모를 방지할 수 있다.
- 자원 공유, 설정 관리, 로그 작성 등과 같이 전역적으로 하나의 인스턴스만 필요한 경우에 유용하다.

### 구현 방법
1. 프라이빗 생성자(private constructor): 클래스의 생성자를 private으로 선언하여 외부에서 인스턴스를 생성하지 못하게 합니다.
2. 정적 메서드(static method): 유일한 인스턴스에 접근할 수 있는 정적 메서드를 제공합니다.
3. 정적 변수(static variable): 유일한 인스턴스를 저장하기 위한 정적 변수를 선언합니다.

```
public class Singleton {
    // 유일한 인스턴스를 저장하기 위한 정적 변수
    private static Singleton instance;
    
    // 생성자를 private으로 선언하여 외부에서 인스턴스를 생성하지 못하도록 함
    private Singleton() {
        // 생성자 내용
    }
    
    // 유일한 인스턴스에 접근할 수 있는 정적 메서드
    public static Singleton getInstance() {
        // 인스턴스가 없는 경우에만 인스턴스 생성
        if (instance == null) {
            instance = new Singleton();
        }
        return instance;
    }
}
```

### 면접 질문
- **싱글톤 디자인을 활용하는 경우를 예를 들어 설명해주세요.** <br>
싱글톤 패턴은 특정 용도로 인스턴스를 하나만 생성하여 전역으로 이용하고 싶을 때 사용합니다.
예를 들어 설정 정보를 관리하는 클래스가 있을 때 여러 모듈에서 인스턴스를 생성하게 되면 각 모듈마다 설정 정보가 달라져 일관성을 해칠 수 있습니다.
이러한 경우 싱글톤 패턴을 이용하여 인스턴스를 한 번만 생성하고 전역으로 공유하여 사용한다면
문제의 발생과 불필요한 메모리 낭비를 방지할 수 있습니다.


- **싱글톤 디자인 패턴의 장단점을 설명해주세요.** <br>
싱글톤 패턴의 장점으로는 불필요한 메모리 낭비를 방지하고 전역 인스턴스를 통해 쉽게 자원공유를 할 수 있다는 점이 있습니다.
반면에 단점으로는 전역으로 접근을 허용하기 때문에 해당 인스턴스에 의존하는 경우 결합도가 증가할 수 있습니다.
이 경우 의존성 주입을 통해 결합도를 느슨하게 만들어줄 수 있습니다.
