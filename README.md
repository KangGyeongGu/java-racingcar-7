# java-racingcar-precourse

## 기능 요구 사항 분석

### 입력 분석

- **이름 입력**: 쉼표(,)로 구분된 n명의 이름이 각각 5자 이하로 입력되어야 한다. 또한, 몇 번의 이동을 할 것인지 입력받는다.
    - 한 줄의 텍스트 입력에서 쉼표로 구분된 이름들을 분할한다.
    - 각 이름이 5자 이하인지 검사한다.
    - 이동 횟수를 입력받는다.

  ⚠️ 잘못된 구분자가 입력될 경우 `IllegalArgumentException` 발생시킨다.

  ⚠️ 이름이 5자를 초과할 경우 `IllegalArgumentException` 발생시킨다.

### 동작 분석

- **자동차 동작**: 사용자가 n대의 자동차에 이름을 부여하고, 각 자동차는 전진 및 정지 기능을 갖는다.
    - 각 이동 단계에서 자동차들의 위치를 출력한다.
    - 공통 속성(탑승자 이름, 현재 위치)을 가진 추상 클래스 `Car`를 정의한다.
    - 전진 및 정지 기능을 인터페이스로 정의한다.
    - 추상 클래스와 인터페이스를 상속받은 경주용 자동차 클래스를 구현한다.

---

## 기능 구현 단계

1. **사용자 입력 구현**
    - n명의 이름을 입력받는다. ➡️ 구분자가 쉼표(,)가 아니면 예외 발생.
    - 유효한 구분자인 경우, 입력받은 이름들을 분할. ➡️ 이름이 5자를 초과하면 예외 발생.


2. **자동차 클래스 구현**
    - 탑승자 이름과 현재 위치 속성을 가진 추상 클래스 `Car` 정의.
    - 전진(`forward`) 및 정지(`stop`) 메소드를 가진 인터페이스 구현.
        - `forward`: 자동차 위치를 1 증가시킨다.
        - `stop`: 자동차 위치 변화 없음.


3. **게임 진행 클래스 구현**
    - 자동차 객체 리스트와 이동 횟수를 속성으로 가진 `RacingGame` 클래스를 정의.
    - 랜덤 난수에 따라 각 라운드마다 차량을 움직이는 메소드 구현.
    - 각 라운드 후 자동차들의 위치를 출력하는 메소드 구현.
    - 게임 종료 후 우승자를 출력하는 메소드 구현.