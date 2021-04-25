# 어댑터 패턴(Adapter Pattern)
---

> 클래스의 인터페이스를 사용자가 기대하는 다른 인터페이스로 변환하는 패턴으로, 호환성이 없는 인터페이스 때문에 함께 동작할 수 없는 클래스들이 함께 동작하도록 해준다.

## 기존 Math 클래스

```java
public class Math {

    public double twoTime(double n) {
        return n * 2;
    }

    public double halfTime(double n) {
        return n / 2;
    }
}
```

## AdapterInterface

```java
public interface Adapter {
    
    public int twoTime(int n);
    public int halfTime(int n);
}
```

## AdapterImpl

```java
public class AdapterImpl implements Adapter {

    final static Math math = new Math();

    @Override
    public int twoTime(int n) {
        return (int)math.twoTime(n);
    }

    @Override
    public int halfTime(int n) {
        return (int)math.halfTime(n);
    }
}
```

## Unit Test

```java
class AdapterImplTest {

    final static Adapter ad = new AdapterImpl();

    @Test
    void twoTime() {
        assertEquals(2, ad.twoTime(1));
    }

    @Test
    void halfTime() {
        assertEquals(1, ad.halfTime(2));
    }
}
```

-> double로 받고 반환하던 Math를 어댑터 패턴을 통해 int로 반환하도록 **변환**

-> 장점이 뭘까?...