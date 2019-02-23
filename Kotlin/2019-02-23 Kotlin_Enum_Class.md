# 2019-02-23

## Kotlin의 Enum Class

* 사용목적
    - 정수형 변수 대신 사용하여 가독성을 높인다.

* 특징
    - 클래스 앞에 *enum* 키워드를 입력한다.
    - 열거된 순서에 따라 0부터 순서 값을 갖는다.

* 예시
    - 선언
    ```Kotlin
    enum class Seasons {
        SPRING, SUMMER, FALL, WINTER
    }
    ```

    - 순서대로 부여되는 값 대신 다른 값으로 초기화 할 수 있다.
    ```Kotlin
    enum class Seasons(val num: Int) {
        SPRING(3), SUMMER(6), FALL(9), WINTER(12)
    }
    ```