# 싱글톤 패턴
---

> 인스턴스를 하나만 만들어 사용하기 위한 패턴

- 생성자에 private 접근 제어자를 지정
- 유일한 단일 객체를 반환할 수 있는 정적 메서드 필요
- 유일한 단일 객체를 참조할 수 있는 참조 변수 필요

```java
public class Singleton {
    static Singleton singletonObject;

    private Singleton() { };

    public static Singleton getInstance() {
        if (singletonObject == null) {
            singletonObject = new Singleton();
        }

        return singletonObject;
    }
}
```

-> 클래스의 인스턴스, 즉 객체를 하나만 만들어 사용하는 패턴