# 프록시 패턴
---

> 대리자, 대변인이라는 뜻을 가지고 있음. 실제 클래스에 바로 접근하는 것이 아닌 대리수행 역할을 하는 프록시 클래스를 사용

- 실제 로직은 실제 클래스를 호출하여 진행
- 선처리나, 사용하지 않는 메서드를 알려주거나 혹은 실제로 해당 클래스가 사용될 때까지 객체 생성을 미뤄 Lazy Loading 할 때 사용할 수 있음

예시 HTTP Proxy

- 하나하나 원격지에 있는 웹 서버에 액세스해서 가져오는 것이 아닌 HTTP Proxy가 캐쉬해서 어떤 페이지를 대신해서 취득
- 최신 정보가 필요하거나 페이지 유효기간이 지났을 때 실제 웹 서버에 웹 페이지를 가지러감

-> 제어 흐름을 조정하기 위한 목적으로 중간에 대리자를 두는 패턴

```java
package proxypattern;

public interface IComputer {
    public void setOs(String os);
    public String getOs();
}
```

```java
package proxypattern;

public class Computer implements IComputer {

    private String os;

    public Computer() {
        job("컴퓨터 인스턴스 생성 중");
    }

    public Computer(String os) {
        this.os = os;
        job("os 설치중 " + os);
    }

    @Override
    public void setOs(String os) {
        this.os = os;
    }

    @Override
    public String getOs() {
        return os;
    }

    private void job(String msg) {
        System.out.println(msg);

        for (int i = 0; i < 5; i++) {
            try {
                Thread.sleep(1000);
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
            System.out.print(".");
        }
        System.out.println("완료");
    }
}
```

```java
package proxypattern;

public class ProxyComputer implements IComputer {

    private String os;
    private Computer real;

    public ProxyComputer() {}

    public ProxyComputer(String os) {
        this.os = os;
    }

    @Override
    public synchronized void setOs(String os) {
        if (real == null) {
            realize();
            real.setOs(os);
        }
        this.os = os;
    }

    @Override
    public String getOs() {
        if (real == null) {
            realize();
        }
        return real.getOs();
    }

    public synchronized void realize() {
        if (this.real == null) {
            real = new Computer(os);
        }
    }
}
```