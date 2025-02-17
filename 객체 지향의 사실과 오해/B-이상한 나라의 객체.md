# 이상한 나라의 객체
---

## 객체지향과 인지 능력
---

- 객체지향은 세상을 자율적이고 독립적인 객체들로 분해할 수 있는 인간의 기본적인 인지 능력에 기반을 두고 있다.
- 객체란 인간이 분명하게 인지하고 구별할 수 있는 물리적인 또는 개념적인 경계를 지닌 어떤 것이다.

객체지향 애플리케이션의 내부를 들여다볼 수 있다면 겉으로는 우리가 알고있는 세계와 유사해 보이지만 본질적으로는 매우 이질적인 모습을 지닌 세계와 마주치게 될 것이다.

## 객체, 그리고 이상한 나라
---

이상한 나라의 앨리스의 특징은 객체의 특징과 같다.

- 앨리스(객체)의 특징은 키(상태)가 변경이 가능하다.
- 앨리스의 키를 변경시키는 것은 엘리스의 행동이다.
    - 앨리스가 한 행동의 결과는 앨리스의 상태에 의존적이다.
    - 행동간의 순서는 결과에 영향을 미친다.
- 키가 작아지거나 커지더라도 앨리스는 앨리스다. (유일한 존재로 식별 가능)

## 객체, 그리고 소프트웨어 나라
---

> 객체란 식별 가능한 개체 또는 사물이다. 객체는 자동차처럼 만질 수 있는 구체적인 사물일 수도 있고, 시간처럼 추상적인 개념일 수도 있다. 객체는 구별 가능한 식별자, 특징적인 행동, 변경 가능한 상태를 가진다. 소프트웨어 안에서 객체는 저장된 상태와 실행 가능한 코드를 통해 구현된다.

### 상태
---

행동의 결과와 과정을 단순하게 기술하기 위한 개념, 과거의 모든 행동 이력을 몰라도 행동의 결과를 쉽게 예측가능

- 프로퍼티
    - 객체의 상태를 구성하는 모든 특징
    - 앨리스의 경우 키, 위치, 음료(다른 객체)
    - 정적
- 프로퍼티 값
    - 동적
    - 앨리스의 키는 음료를 마시면 작아진다.
    - 앨리스의 위치는 문을 통과하면 정원으로 바뀔것이다.
- 링크
    - 객체와 객체 사이의 의미 있는 연결
    - 앨리스와 음료 (객체가 다른 객체의 식별자를 알고 있어야 한다.)

> 객체는 자율적인 존재다. 객체지향의 세계에서 객체는 다른 객체의 상태를 직접적으로 접근할 수도, 상태를 변경할 수도 없다.

### 행동
---

> 객체의 행동은 객체의 상태를 변경시키지만 행동의 결과는 객체의 상태에 의존적이다.

- 앨리스가 음료를 마신 후의 키는 음료를 마시기 전의 키에 의존한다.
    - 객체의 행동은 상태에 영향을 받는다.
    - 객체의 행동은 상태를 변경시킨다.

### 식별자
---

> 객체를 서로 구별할 수 있는 특정한 프로퍼티가 객체 안에 존재, 이러한 프로퍼티를 식별자라고 칭함

- 값 : 식별자가 없음
    - 불변 상태
    - 동등성 (equality)
- 객체 : 식별자가 있음
    - 가변 상태
    - 동일성 (identical)

## 기계로서의 객체
---

> 객체의 상태를 조회하는 작업을 쿼리(query)라고 하고 객체의 상태를 변경하는 작업을 명령(command)라고 함
