# 템플릿 메서드 패턴
---

> 상위 클래스의 견본 메서드에서 하위 클래스가 오버라이딩한 메서드를 호출하는 패턴

```java
public abstract class Animal {
    // 템플릿 메서드
    public void playWithOwner() {
        sout("이리와!");
        play();
        runSomething();
    }

    // 추상 메서드
    abstract void play();

    // Hook 메서드
    void runSomething() {
        sout("꼬리 살랑 살랑");
    }
}
```

```java
public class Dog extends Animal {

    @Override
    // 추상 메서드 오버라이딩
    void play() {
        sout("멍 멍!");
    }
}
```

```java
public class Cat extends Animal {
    
    @Override
    void play() {
        sout("야옹!");
    }

    @Override
    void runSomething() {
        sout("꼬리 삐쭉!");
    }
}
```

-> 하위 클래스에서 알고리즘 구조의 변경없이 알고리즘을 재정의